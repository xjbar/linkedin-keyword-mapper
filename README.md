# LinkedIn Keyword Mapper

## Overview

LinkedIn Keyword Mapper is a command-line tool designed to help you organize and optimize your LinkedIn profile by extracting and sorting relevant keywords from job listings.

## Prerequisites

Before using this tool, make sure you have the following:

- LinkedIn Premium subscription
- Access to a terminal or PowerShell on Windows
- A text editor (e.g., Notepad)

## How to Use

1. Log in to LinkedIn and click "Jobs" at the top of the page.

2. In the search box, enter the job title you're interested in.

3. Click on a job listing that appeals to you.

4. Scroll to the bottom of the job listing to find the "PREMIUM: HOW YOU MATCH" section.

5. Click on the listed keywords to open the list, then copy the keywords. You can ignore the "+ ADD" buttons.

6. Paste the copied keywords into a Google Doc, ensuring you right-click and choose "Paste without formatting." Do not make any edits to the pasted content.

7. Repeat steps 3-6 for multiple job listings to compile a substantial list of keywords.

8. Save the document as a .txt file.

### Using Linux

If you're using Linux, open your terminal and use this command:

```bash
grep -v -e '^Add:$' -e '^[[:space:]]*$' yourfile.txt | grep -v '^Add$' | sort | uniq -c | sort -k1,1nr > sortedwords.txt
```

### Using Windows PowerShell

If you're using Windows PowerShell, enter the following command:

```powershell
Get-Content -Path yourfile.txt | Where-Object {$_ -notmatch '^Add:$' -and $_ -notmatch '^\s*$' -and $_ -ne 'Add'} | Sort-Object | Get-Unique -AsString | Sort-Object -Property Count -Descending | Out-File -FilePath sortedwords.txt
```
Replace [yourfile.txt] with the path to your .txt file that contains the collected keywords. Press Enter to execute the command, which will generate an organized list of keywords in a file called sortedwords.txt in the same directory.

Open the sortedwords.txt file to view your keywords, organized from most to least desired. You can now update your LinkedIn profile's skills list with the most relevant keywords!
