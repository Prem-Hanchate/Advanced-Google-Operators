# Google Dork Cheatsheet

> Advanced Google Search Operators for OSINT, Security Research, and Ethical Hacking

---

## Most Commonly Used Operators

| Filter | Description | Example |
| :-------------- |:---------------------------------------------------| :------------------------------------|
| `site:` | Search within a specific domain or website | `site:github.com python` |
| `filetype:` | Search for specific file types | `filetype:pdf cybersecurity` |
| `intitle:` | Search for pages with specific words in the title | `intitle:"admin panel"` |
| `inurl:` | Search for pages with specific terms in the URL | `inurl:admin` |
| `intext:` | Search for pages containing specific text in content | `intext:"password"` |
| `cache:` | View Google's cached version of a webpage | `cache:example.com` |
| `related:` | Find websites similar to a specified domain | `related:github.com` |
| `define:` | Get definitions of terms | `define:phishing` |
| `-` | Exclude terms from search results | `security -jobs` |
| `OR` | Search for either term | `(hacking OR security)` |
| `""` | Exact phrase match | `"SQL injection"` |
| `*` | Wildcard for any word | `"admin * panel"` |

---

## Operators for Security Research & Hacking

| Filter | Description | Example |
| :-------------- |:---------------------------------------------------| :------------------------------------|
| `intitle:"index of"` | Find exposed directories | `intitle:"index of" backup` |
| `filetype:sql` | Find SQL database files | `filetype:sql "INSERT INTO" password` |
| `filetype:log` | Find log files with sensitive data | `filetype:log intext:password` |
| `filetype:env` | Find environment configuration files | `filetype:env "DB_PASSWORD"` |
| `inurl:admin` | Find admin login pages | `inurl:admin intitle:login` |
| `inurl:wp-admin` | Find WordPress admin pages | `inurl:wp-admin site:target.com` |
| `inurl:phpMyAdmin` | Find phpMyAdmin login pages | `inurl:"/phpmyadmin/" intitle:"Welcome"` |
| `intitle:"Dashboard"` | Find dashboard pages | `intitle:"Dashboard" inurl:admin` |
| `filetype:config` | Find configuration files | `filetype:config inurl:web.config` |
| `filetype:bak` | Find backup files | `filetype:bak inurl:backup` |
| `intext:"sql syntax near"` | Find SQL error messages | `intext:"sql syntax near" site:target.com` |
| `intitle:"Apache Status"` | Find Apache server status pages | `intitle:"Apache Status" inurl:server-status` |
| `inurl:shell` | Find web shells | `inurl:shell OR inurl:backdoor` |
| `filetype:xls inurl:email` | Find spreadsheets with emails | `filetype:xls inurl:email.xls` |
| `intitle:"Dashboard" intext:"Grafana"` | Find Grafana monitoring dashboards | `intitle:"Dashboard" intext:"Grafana"` |

---

## All Google Dork Operators

| Filter | Description | Example |
| :-------------- |:---------------------------------------------------| :------------------------------------|
| `allintext` | Searches for all keywords in page content | `allintext:username password email` |
| `intext` | Searches for keyword occurrences in content | `intext:"keyword"` |
| `allinurl` | Searches for all keywords in URL | `allinurl:admin login php` |
| `inurl` | Searches for keyword in URL | `inurl:"keyword"` |
| `allintitle` | Searches for all keywords in page title | `allintitle:admin login secure` |
| `intitle` | Searches for keyword in page title | `intitle:"keyword"` |
| `site` | Search within specific domain | `site:"example.com"` |
| `filetype` | Search for specific file types | `filetype:"pdf"` |
| `ext` | Alternative to filetype | `ext:"docx"` |
| `link` | Find pages linking to a URL | `link:"example.com"` |
| `numrange` | Search within number ranges | `numrange:100-200` |
| `before` | Search content before a date | `before:2023-01-01` |
| `after` | Search content after a date | `after:2022-01-01` |
| `daterange` | Search within date range | `daterange:2023-01-01..2023-12-31` |
| `allinanchor` | Search keywords in anchor text of links | `allinanchor:keyword` |
| `inanchor` | Search keyword in anchor text | `inanchor:rat` |
| `allinpostauthor` | Search blog posts by specific author | `allinpostauthor:"John Doe"` |
| `inpostauthor` | Search posts by author | `inpostauthor:"keyword"` |
| `related` | Find similar websites | `related:example.com` |
| `cache` | Show Google's cached version | `cache:example.com` |
| `info` | Get information about a page | `info:example.com` |
| `stocks` | Get stock information | `stocks:GOOGL` |
| `map` | Show map results | `map:San Francisco` |
| `movie` | Get movie information | `movie:Inception` |
| `weather` | Get weather information | `weather:London` |
| `source` | Search news from specific source | `source:reuters` |
| `loc` | Search in specific location | `loc:"New York"` |
| `location` | Alternative for location search | `location:London` |

---

## ⚠️ Legal Disclaimer

**Educational Purpose Only** - This cheatsheet is provided for educational, research, and authorized security testing purposes only. Unauthorized access to computer systems is illegal. Always ensure you have proper authorization before conducting security research.

---

## 📝 Quick Tips

- **Combine operators** for powerful searches: `site:target.com filetype:pdf confidential`
- **Use quotes** for exact matches: `"admin login"`
- **Use parentheses** for grouping: `site:example.com (inurl:admin OR inurl:login)`
- **Exclude terms** with minus: `security -jobs -courses`
- **Use wildcards** for variations: `"admin * panel"`

---

Made with 🔍 for Security Researchers & OSINT Practitioners
