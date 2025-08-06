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


## inurl:
**`inurl:admin`** - Searches for a word or fragment of a URL in the address bar of the page

**Examples:**

**`inurl:login`** — pages whose URL contains “login”

**`site:example.com`** inurl:config — search for configuration files on example.com

- **Application in information security:**

Often used to search for control panels, login pages, open directories:

**`inurl:wp-admin`**

**`inurl:index.of`**


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


