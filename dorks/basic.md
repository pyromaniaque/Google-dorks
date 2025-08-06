## Basic Google Dorks Operators

1. ## site:

The “site:” operator limits the search to only one specific site or domain, including all of its subdomains.

**Syntax:** 

**`site:domain query`**

site: — the operator itself
domain — the website, zone, or subdomain to which the search is limited
search_query — what you are searching for within the specified domain

**`site:example.com`**

Shows all pages that Google has indexed on the example.com domain.

**Examples:**

**`site:gov.ru`** — searches only on .gov.ru domains

**`site:example.com login`** — searches for pages with the word “login” on the example.com website

**Search by domain zone**

**_.TLD_**

**`site:gov.ru`** 

Shows all websites ending in .gov.ru (e.g., minzdrav.gov.ru, kremlin.gov.ru, etc.)

**This is used, for example:**

to analyze only government websites,
to identify leaks, accessible documents, and reports.

**site: does not always include subdomains**

Although site:example.com may also return blog.example.com, if you only want the subdomain, write:

**`site:blog.example.com`**

- **Application in information security:**

We search for public documents or authorization panels only on the target website:

**`site:example.com`** 

**`inurl:admin`**


2. ## inurl:
**`inurl:admin`** - Searches for a word or fragment of a URL in the address bar of the page

**Examples:**

**`inurl:login`** — pages whose URL contains “login”

**`site:example.com`** inurl:config — search for configuration files on example.com

- **Application in information security:**

Often used to search for control panels, login pages, open directories:

**`inurl:wp-admin`** - searches for pages whose URL contains wp-admin. (https://example.com/wp-admin/)

**Application:**

This is used to find the administration panels of WordPress sites. Usually, wp-admin is the path to the administrative part of a WordPress site.

**What is is used for:**

Penetration testers and researchers — to identify WordPress sites.
Bots and attackers — to attempt brute force attacks or scan for vulnerabilities.
Administrators — to search for their own sites/panels.

**`inurl:index.of`** - Searches for pages whose URL contains index.of.

**What this means:**

This allows you to find open directories that are directly accessible via a browser. Such pages usually have a title like Index of /some/folder and represent a list of files and folders on the server.

**Examples of output:**

`Index of /movies`
`Index of /music`
`Index of /backups`

**What it is used for:**

To search for unprotected files that can be downloaded.
In OSINT or intelligence gathering — to find public (often accidentally accessible) directories.
By researchers — to find data leaks or interesting content.


**Additional information about "inurl" operator**

(inurl:wp-admin and inurl:index.of) are Google search operators used to find specific types of web pages. They are used, for example, in OSINT, information security, penetration testing, or even website administration.


3. ## intitle:

The operator **intitle:“...”** is used in search engines (mainly Google) to find pages where the specified words or phrases appear in the title of the web page.

**Syntax:**

**`intitle:"word"`**

What does it do?

The intitle: operator forces the search engine to search only in the HTML document title, rather than the entire page content.

The page title is what is inside the <title>...</title> tag and is usually displayed in the browser tab title and search results.

**Examples:**

- **Search for pages where the exact phrase is in the title:**

**`intitle:"single word"`**

will only find pages that contain the phrase single word in the title.

- **Can be combined with ordinary words:**

**`intitle:"using bash" cash`**

will find pages where the title contains the phrase “using bash” and the text of the page contains the word “cash”.

**`intitle:“index of”`** — searches for open directories

**`intitle:login site:example.com`** — searches for login pages on the specified website

- **Application in information security:**

Especially useful when searching for open directories and system panels

**Features:**

Without quotation marks **(intitle:network attacks)**, **only the word “network”** will be found in the title, while **“attacks” can be anywhere**.

To specify an exact phrase, always enclose it in quotation marks: intitle:“network attacks”.


4. ## filetype:
**`filetype:pdf`** - Limits search results to files of a specific type (extension).

**Examples:**

**`site:gov.ru filetype:pdf`** — searches for PDF documents on gov.ru domains

**`filetype:log password`** — searches for text log files containing the word “password”

- **Application in information security:**

Search for leaks in the form of .log, .txt, .csv, .xls, .conf, .sql:

**`filetype:sql "insert into"`**

**`filetype:conf site:example.com`**


5. ## cache:
**`cache:example.com`** - Allows you to view the cached (saved) Google version of the page.

**Examples:**

**`cache:example.com`** — shows what the site looked like when Google last cached it

**`cache:example.com/login`** — cache of the login page

- **Application in information security:**

Viewing deleted or temporarily unavailable information

Used when analyzing changes on a page (for example, when a vulnerability has been deleted but remains in the cache)

6. ## Combining operators
Examples:

```Dorks
site:example.com inurl:admin intitle:"login" filetype:php

site:*.edu filetype:xls password

inurl:".git" intitle:"index of"


