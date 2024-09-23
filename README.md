<h1>Create hash values</h1>


<h2>Description</h2>

As a security analyst, you’ll need to implement security controls to protect organizations against a range of threats.

That’s where hashing comes in. Previously, you learned that a hash function is an algorithm that produces a code that can’t be decrypted. Hash functions are used to uniquely identify the contents of a file so that you can check whether it has been modified. This code provides a unique identifier known as a hash value or digest.

For example, a malicious program may mimic an original program. If one code line is different from the original program, it produces a different hash value. Security teams can then identify the malicious program and work to mitigate the risk.

Many tools are available to compare hashes for various scenarios. But for a security analyst it’s important to know how to manually compare hashes.

In this lab activity, we’ll create hash values for two files and use Linux commands to manually examine the differences.

<h2>Environments Used </h2>

- <b>Linux</b>

<h2>Scenario:</h2>

In this scenario, we need to investigate whether two files are identical or different.

Here’s how you'll do this task: 

- First, you’ll display the contents of two files and create hashes for each file.
  
- Next, you’ll examine the hashes and compare them.

Let’s hash some files!

<h2>Tutorial walk-through:</h2>

<h3>Task 1. Generate hashes for files</h3>

The lab starts in your home directory, /home/analyst, as the current working directory. This directory contains two files file1.txt and file2.txt, which contain different data.

In this task, you need to display the contents of each of these files. You’ll then generate a hash value for each of these files and send the values to new files, which you’ll use to examine the differences in these values later.

1. Use the ls command to list the contents of the directory.
   
Two files, file1.txt and file2.txt, are listed.

<img src="https://i.imgur.com/HgompuG.png" height="80%" width="80%"/>

2. Use the cat command to display the contents of the file1.txt file:

3. Use the cat command to display the contents of the file2.txt file:

4. Review the output of the two file contents:

<img src="https://i.imgur.com/lAE3jJ7.png" height="80%" width="80%"/>

Although the contents of both files appear identical when you use the cat command, you need to generate the hash for each file to determine if the files are actually different.

5. Use the sha256sum command to generate the hash of the file1.txt file:
   
You now need to follow the same step for the file2.txt file.

6. Use the sha256sum command to generate the hash of the file2.txt file:

7. Review the generated hashes of the contents of the two files:

<img src="https://i.imgur.com/p8kdCvB.png" height="80%" width="80%"/>


<h3>Task 2. Compare hashes</h3>

In this task, you’ll write the hashes to two separate files and then compare them to find the difference.

1. Use the sha256sum command to generate the hash of the file1.txt file, and send the output to a new file called file1hash:
   
You now need to complete the same step for the file2.txt file.

2. Use the sha256sum command to generate the hash of the file2.txt file, and send the output to a new file called file2hash:

Now, you should have two hashes written to separate files. The first hash was written to the file1hash file, and the second hash was written to the file2hash file.

You can manually display and compare the differences.

3. Use the cat command to display the hash values in the file1hash and file2hash files.

4. Inspect the output and note the difference in the hash values.

<img src="https://i.imgur.com/vvQ241N.png" height="80%" width="80%"/>

Now, you can use the cmp command to compare the two files byte by byte. If a difference is found, the command reports the byte and line number where the first difference is found.

5. Use the cmp command to highlight the differences in the file1hash and file2hash files:

6. Review the output, which reports the first difference between the two files:

<img src="https://i.imgur.com/1EsLvWn.png" height="80%" width="80%"/>


<h2>Conclusion</h2>

You practiced how to

- compute hashes using sha256sum
- display hashes using the cat command
- compare hashes using the cmp command

