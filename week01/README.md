<h1>Week 1: Setting up the system; basic UNIX command line actions</h1>
<br>
<p><h3>Setting up in Windows</h3><br>
This is done with only one command:<br>
<pre><code><br>
wsl --install<br>
</code></pre></p>
<p><h3>Installing an AI-ready code editor</h3><br>
I have chosen to use VSCode.</p>
<p><h3>Assignment Questions</h3><br>
<h5>What version is your <code>samtools</code> command in the <code>bioinfo</code> environment?</h5><br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
bioinfo<br>
# Activating bioinfo ...<br>
(bioinfo)<br>
cjpauly@DESKTOP-7GB5OTF ~<br>
samtools<br>
<br>
Program: samtools (Tools for alignments in the SAM format)<br>
Version: 1.24 (using htslib 1.24)<br>
</code></pre><br>
<h5>Show commands needed to create a nested directory structure</h5><br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
mkdir -p ~/dir/subdir<br>
</code></pre><br>
This creates directories recursively.<br>
<h5>Show commands that create files in different directories</h5><br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
touch ~/dir/subdir/file.extension<br>
</code></pre><br>
This creates a file in the chosen directory.<br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
touch ~/otherdir/subdir/file.extension<br>
</code></pre><br>
This creates a file in a different directory.<br>
<h5>Show how to access these files using relative and absolute paths.</h5><br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
explorer.exe ~/dir/subdir/file.extension<br>
</code></pre><br>
This opens the chosen file using the default application. The file is chosen by the absolute path from the root directory.<br>
<pre><code><br>
cjpauly@DESKTOP-7GB5OTF ~<br>
cd ~/otherdir/subdir<br>
explorer.exe file.extension<br>
</code></pre><br>
This code changes directory into the file's location, then uses the relative file path to open the file using the default application.</p>
