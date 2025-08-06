## Basic Google Dorks Operators

## site:

Limits the search to only one site or domain.

**`site:example.com`**

**Examples:**

**`site:gov.ru`** — searches only on .gov.ru domains

**`site:example.com login`** — searches for pages with the word “login” on the example.com website

- **Application in information security:**

We search for public documents or authorization panels only on the target website:
site:example.com inurl:admin


## - inurl:
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


## intitle:
**`intitle:"index of"`** - Searches for a word in the page title (in the HTML <title> tag).

**Examples:**

**`intitle:“index of”`** — searches for open directories

**`intitle:login site:example.com`** — searches for login pages on the specified website

- **Application in information security:**

Especially useful when searching for open directories and system panels


## filetype:
**`filetype:pdf`** - Limits search results to files of a specific type (extension).

**Examples:**

**`site:gov.ru filetype:pdf`** — searches for PDF documents on gov.ru domains

**`filetype:log password`** — searches for text log files containing the word “password”

- **Application in information security:**

Search for leaks in the form of .log, .txt, .csv, .xls, .conf, .sql:

**`filetype:sql "insert into"`**

**`filetype:conf site:example.com`**


## cache:
**`cache:example.com`** - Allows you to view the cached (saved) Google version of the page.

**Examples:**

**`cache:example.com`** — shows what the site looked like when Google last cached it

**`cache:example.com/login`** — cache of the login page

- **Application in information security:**

Viewing deleted or temporarily unavailable information

Used when analyzing changes on a page (for example, when a vulnerability has been deleted but remains in the cache)

## Combining operators
Examples:

```Dorks
site:example.com inurl:admin intitle:"login" filetype:php

site:*.edu filetype:xls password

inurl:".git" intitle:"index of"


