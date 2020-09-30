# subcompare

A simple tool that can be scheduled to run in the background to track changes to target subdomains. Made this to run on a schedule to automate subdomain discovery.
New subdomains are pushed to a slack webhook.

## Usage
Syntax: subcompare.py masterfile.txt newfile.txt

masterfile is your existing subdomain list generated by tools such as sublist3r
newfile is your latest scan from a tool such as sublist3r

Subcompare checks for new entires in the latest file, triggers an alert for new entries, and adds them to the master file after execution.

How I run this:
Run an initial sublist3r scan and send the output to a master file.
Schedule sublist3r to scan a domain and output the results to a new file.
Schedule subcompare to run after the sublist3r scan.

Additionally, I've added the ability to launch sublist3r from within subcompare with the --domain flag. The sublist3r output goes to the newfile, then the main script runs.

