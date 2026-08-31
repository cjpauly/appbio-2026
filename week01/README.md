<h1>Week 1: Setting up the system; basic UNIX command line actions</h1>
<br>
<p><h2>Setting up in Windows</h2><br>
This is done with only one command:<br>
<pre><code>wsl --install<br>
</code></pre></p>
<p><h2>Installing an AI-ready code editor</h2><br>
I have chosen to use VSCode.</p>
<p><h2>Assignment Questions</h2><br>
<h4>What version is your <code>samtools</code> command in the <code>bioinfo</code> environment?</h4><br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
bioinfo<br>
# Activating bioinfo ...<br>
<br>
(bioinfo)<br>
cjpauly@DESKTOP-7GB5OTF ~<br>
samtools<br>
<br>
Program: samtools (Tools for alignments in the SAM format)<br>
Version: 1.24 (using htslib 1.24)<br>
</code></pre>
<h4>Show commands needed to create a nested directory structure</h4><br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
mkdir -p ~/dir/subdir<br>
</code></pre>
This creates directories recursively.<br>
<h4>Show commands that create files in different directories</h4><br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
touch ~/dir/subdir/file.extension<br>
</code></pre>
This creates a file in the chosen directory.<br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
touch ~/otherdir/subdir/file.extension<br>
</code></pre>
This creates a file in a different directory.<br>
<h4>Show how to access these files using relative and absolute paths.</h4><br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
explorer.exe ~/dir/subdir/file.extension<br>
</code></pre>
This opens the chosen file using the default application. The file is chosen by the absolute path from the root directory.<br>
<pre><code>cjpauly@DESKTOP-7GB5OTF ~<br>
cd ~/otherdir/subdir<br>
<br>
cjpauly@DESKTOP-7GB5OTF ~<br>
explorer.exe file.extension<br>
</code></pre>
This code changes directory into the file's location, then uses the relative file path to open the file using the default application.</p>
