SHELL := /bin/bash
.DELETE_ON_ERROR:

.SHELLFLAGS := -o pipefail -c

FASTA_URL := https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/900/157/325/GCF_900157325.1_3A1/GCF_900157325.1_3A1_genomic.fna.gz
GFF_URL := https://ftp.ncbi.nlm.nih.gov/genomes/all/GCF/900/157/325/GCF_900157325.1_3A1/GCF_900157325.1_3A1_genomic.gff.gz

FASTA := fasta/Porphyromonas_gingivalis.fna
GFF := gff/Porphyromonas_gingivalis.gff
GFF_GZ := $(GFF).gz

.PHONY: all download stats index igv clean

all: stats index

download: $(FASTA) $(GFF)

fasta:
	mkdir -p $@

gff:
	mkdir -p $@

$(FASTA): | fasta
	curl -L --fail --retry 3 $(FASTA_URL) | gzip -dc > $@

$(GFF): | gff
	curl -L --fail --retry 3 $(GFF_URL) | gzip -dc > $@

stats: download
	@echo "Genome size: $$(awk '!/^>/ {gsub(/[[:space:]]/, ""); n += length} END {print n+0}' $(FASTA)) bp"
	@echo "Number of annotations: $$(awk '!/^#/ && NF {n++} END {print n+0}' $(GFF))"

$(FASTA).fai: $(FASTA)
	samtools faidx $<

$(GFF_GZ): $(GFF)
	{ \
		awk '/^##FASTA/{exit} /^#/ {print}' $<; \
		awk '/^##FASTA/{exit} !/^#/ && NF {print}' $< | \
			LC_ALL=C sort -t $$'\t' -k1,1 -k4,4n; \
	} | bgzip -c > $@.tmp
	mv $@.tmp $@

$(GFF_GZ).tbi: $(GFF_GZ)
	tabix -f -p gff $<

index: $(FASTA).fai $(GFF_GZ).tbi

igv: index
	igv -g $(FASTA) $(GFF_GZ)

clean:
	rm -rf fasta gff
