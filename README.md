# 🔍 Advanced Google Search Operators
## Google Dorking & OSINT Intelligence Guide

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Purpose](https://img.shields.io/badge/purpose-Educational-green.svg)
![OSINT](https://img.shields.io/badge/OSINT-Research-orange.svg)

> A comprehensive guide to mastering Google Search Operators for Open-Source Intelligence (OSINT), cybersecurity reconnaissance, and ethical research.

---

## 📋 Table of Contents

- [Project Overview](#project-overview)
- [What Are Google Search Operators?](#what-are-google-search-operators)
- [Basic Google Operators](#basic-google-operators)
- [Advanced & Combined Operators](#advanced--combined-operators)
- [Google Dorking Examples (Ethical Use)](#google-dorking-examples-ethical-use)
- [OSINT Use Cases](#osint-use-cases)
- [Cybersecurity & Bug Bounty Angle](#cybersecurity--bug-bounty-angle)
- [Practical Search Cheat Sheet](#practical-search-cheat-sheet)
- [Limitations of Google Operators](#limitations-of-google-operators)
- [Tools That Enhance Google Dorking](#tools-that-enhance-google-dorking)
- [What More Can Be Added to This Project?](#what-more-can-be-added-to-this-project)
- [Disclaimer & Ethics](#disclaimer--ethics)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 Project Overview

This project serves as a comprehensive resource for security professionals, researchers, journalists, and anyone interested in leveraging Google's search capabilities for legitimate intelligence gathering and research purposes.

### What Are Google Search Operators?

**Google Search Operators** are special commands and characters that extend the capabilities of regular text searches. They allow you to filter, refine, and pinpoint specific information across billions of web pages with surgical precision.

### Why They Are Powerful

- **Precision**: Find exactly what you need without sifting through irrelevant results
- **Efficiency**: Save hours of manual research time
- **Discovery**: Uncover publicly available information that's hidden in plain sight
- **Intelligence**: Gather actionable data for security assessments, investigations, and research
- **Versatility**: Applicable across multiple domains (security, journalism, academia, business intelligence)

### Real-World Use Cases

- **Cybersecurity Reconnaissance**: Discovering exposed assets, misconfigurations, and potential vulnerabilities
- **OSINT Investigations**: Gathering publicly available intelligence on targets, organizations, or topics
- **Academic Research**: Finding specific papers, datasets, and scholarly resources
- **Competitive Intelligence**: Analyzing competitor infrastructure and digital footprint
- **Bug Bounty Hunting**: Identifying potential security issues in authorized scopes
- **Data Journalism**: Uncovering public records and government documents
- **Digital Forensics**: Locating cached or archived information

---

## 📚 Basic Google Operators

### `site:`
Restricts results to a specific domain or website.

**Syntax:**
```
site:domain.com search_term
```

**Examples:**
```
site:github.com machine learning
site:.gov cybersecurity policy
site:edu.in research papers
```

### `intitle:`
Finds pages with specific words in the title tag.

**Syntax:**
```
intitle:"search term"
```

**Examples:**
```
intitle:"index of" passwords
intitle:"dashboard" login
allintitle:admin panel secure
```

### `inurl:`
Searches for pages with specific terms in the URL.

**Syntax:**
```
inurl:search_term
```

**Examples:**
```
inurl:admin
inurl:login.php
allinurl:admin panel config
```

### `filetype:`
Filters results by specific file types.

**Syntax:**
```
filetype:extension search_term
```

**Examples:**
```
filetype:pdf cybersecurity framework
filetype:xlsx "email addresses"
filetype:docx confidential site:example.com
```

**Supported file types:** pdf, doc, docx, xls, xlsx, ppt, pptx, txt, csv, xml, json, sql, log, conf, bak

### `cache:`
Shows Google's cached version of a webpage.

**Syntax:**
```
cache:url.com
```

**Examples:**
```
cache:example.com
cache:target-site.com/deleted-page
```

**Use cases:** Viewing removed content, recovering deleted information, comparing current vs. cached versions

### `related:`
Finds websites similar to a specified domain.

**Syntax:**
```
related:domain.com
```

**Examples:**
```
related:github.com
related:stackoverflow.com
```

### `define:`
Provides definitions from various sources.

**Syntax:**
```
define:term
```

**Examples:**
```
define:reconnaissance
define:zero-day
```

---

## 🚀 Advanced & Combined Operators

### Combining Multiple Operators

The real power emerges when you chain operators together:

```
site:target.com filetype:pdf confidential
site:.gov inurl:admin intitle:login
site:example.com (inurl:admin OR inurl:login) -inurl:demo
```

### Logical Operators

#### AND (implicit)
```
cybersecurity framework NIST
```
Both terms must appear (space = AND)

#### OR
```
(penetration testing OR ethical hacking) site:edu
site:target.com (filetype:pdf OR filetype:docx)
```

#### NOT (-)
```
cybersecurity -certification
site:example.com -www
inurl:admin -demo -test
```

### Parentheses Usage

Use parentheses to group operators and create complex queries:

```
site:target.com (intitle:admin OR intitle:dashboard) (filetype:php OR filetype:asp)
(site:edu OR site:gov) filetype:pdf (cybersecurity OR infosec)
site:*.target.com -www (inurl:login OR inurl:admin)
```

### Wildcards (*)

The asterisk (*) acts as a placeholder for any word:

```
"cybersecurity * framework"
intitle:"index of" * passwords
"admin * panel" inurl:php
```

### Exact Match Quotes

Use quotes for exact phrase matching:

```
"SQL injection vulnerability"
intitle:"index of" "parent directory"
site:example.com "confidential document"
```

### Number Ranges

```
cybersecurity salary $50000..$150000
vulnerabilities 2020..2024
```

---

## 🎯 Google Dorking Examples (Ethical Use)

> ⚠️ **LEGAL NOTICE**: These examples are for educational purposes only. Always ensure you have proper authorization before conducting reconnaissance on any system. Unauthorized access is illegal.

### Public Documents Discovery

```
site:target.com filetype:pdf (confidential OR internal OR private)
site:*.gov filetype:xlsx budget 2024
intitle:"index of" "financial statements" filetype:xls
```

### Exposed Directories (Non-Intrusive)

```
intitle:"index of" "backup"
intitle:"index of" "database"
intitle:"Index of /" +.htaccess
intitle:"index of" "config.php"
```

### Login Pages

```
inurl:admin intitle:login
inurl:wp-admin site:target.com
intitle:"Dashboard" inurl:admin
inurl:"/phpmyadmin/" intitle:"Welcome to phpMyAdmin"
```

### Configuration Files (For Awareness)

```
filetype:env "DB_PASSWORD"
filetype:config inurl:web.config
intitle:"index of" "config.yml"
filetype:json "api_key"
```

### Database Files

```
filetype:sql "INSERT INTO" "VALUES"
filetype:sql intext:password
intitle:"index of" "database.sql"
```

### Log Files

```
filetype:log inurl:error.log
filetype:log "password" OR "username"
intitle:"index of" "access.log"
```

### Email Addresses & Contact Intelligence

```
site:target.com "@target.com" (intext:"email" OR intext:"contact")
site:*.target.com filetype:xlsx email
```

---

## 🕵️ OSINT Use Cases

### Finding Exposed Documents

**Corporate Intelligence:**
```
site:target.com filetype:pdf (annual report OR quarterly report)
site:target.com filetype:pptx (presentation OR roadmap OR strategy)
```

**Government Records:**
```
site:.gov filetype:pdf "freedom of information"
site:.mil filetype:pdf unclassified
```

**Academic Research:**
```
site:.edu filetype:pdf thesis OR dissertation
site:researchgate.net OR site:arxiv.org "deep learning"
```

### Company Infrastructure Discovery

```
site:*.target.com -www
site:target.com inurl:staging
site:target.com inurl:dev
site:target.com inurl:test
site:target.com (subdomain OR intranet)
```

### Email & Contact Intelligence

**Email Pattern Discovery:**
```
site:target.com "@target.com"
site:linkedin.com "at target.com"
"@target.com" (resume OR CV)
```

**Employee Information:**
```
site:linkedin.com "works at Target Company"
site:github.com "target.com"
```

### Social Media Footprint

```
site:twitter.com "from:targetcompany"
site:facebook.com intitle:target company
site:instagram.com target_company
```

### Technology Stack Discovery

```
site:target.com "powered by"
site:target.com inurl:"/wp-content/"
site:target.com "built with"
```

### Research & Journalism Use

**Public Records:**
```
site:.gov intitle:"court records"
site:.gov filetype:pdf "public record"
```

**Leaked Documents (Public Sources Only):**
```
intitle:"index of" wikileaks
site:documentcloud.org target_name
```

**Data Journalism:**
```
site:.gov filetype:csv dataset
site:data.gov "police incidents"
```

---

## 🛡️ Cybersecurity & Bug Bounty Angle

### How Security Professionals Use Operators

Security researchers and ethical hackers use Google operators to:

1. **Asset Discovery**: Identify all digital assets belonging to an organization
2. **Attack Surface Mapping**: Understand potential entry points
3. **Misconfiguration Detection**: Find exposed services, files, and directories
4. **Information Leakage**: Discover accidentally exposed sensitive data
5. **Reconnaissance**: Gather intelligence before authorized security assessments

### Safe Reconnaissance Methods

**In-Scope Asset Enumeration:**
```
site:*.target.com (authorized scope only)
site:target.com inurl:api
site:target.com filetype:js (api OR endpoint)
```

**Technology Fingerprinting:**
```
site:target.com "X-Powered-By:"
site:target.com inurl:"/wp-json/"
site:target.com "Server: nginx"
```

**Subdomain Discovery:**
```
site:*.target.com -www
site:target.com -site:www.target.com
```

### Bug Bounty Best Practices

✅ **DO:**
- Only test on domains explicitly listed in the program scope
- Use operators for passive reconnaissance first
- Document your findings professionally
- Report vulnerabilities responsibly
- Respect rate limits and robots.txt

❌ **DON'T:**
- Access systems without authorization
- Download large amounts of data
- Exploit vulnerabilities you discover
- Test out-of-scope domains
- Automate searches aggressively

### Difference Between Legal OSINT vs Illegal Hacking

| Legal OSINT | Illegal Activity |
|-------------|------------------|
| Viewing public information | Unauthorized access to systems |
| Reading robots.txt | Bypassing authentication |
| Viewing cached pages | Exploiting vulnerabilities |
| Analyzing public documents | Downloading private data without permission |
| Subdomain enumeration (passive) | Brute-forcing credentials |
| Technology fingerprinting | Denial of Service attacks |

**Key Principle**: If information is publicly accessible without authentication, viewing it is generally legal. Accessing anything requiring credentials or exploiting vulnerabilities is illegal without explicit authorization.

---

## 📊 Practical Search Cheat Sheet

| Operator | Description | Example |
|----------|-------------|---------|
| `site:` | Search within specific domain | `site:github.com python` |
| `intitle:` | Search in page title | `intitle:"admin panel"` |
| `allintitle:` | All terms must be in title | `allintitle:admin login secure` |
| `inurl:` | Search in URL | `inurl:admin` |
| `allinurl:` | All terms must be in URL | `allinurl:admin login php` |
| `filetype:` | Search specific file types | `filetype:pdf cybersecurity` |
| `ext:` | Alternative to filetype | `ext:docx resume` |
| `intext:` | Search in page content | `intext:"password" filetype:log` |
| `allintext:` | All terms in content | `allintext:username password email` |
| `cache:` | View cached version | `cache:example.com` |
| `related:` | Find similar websites | `related:github.com` |
| `info:` | Get info about page | `info:example.com` |
| `define:` | Get definitions | `define:phishing` |
| `stocks:` | Stock information | `stocks:GOOGL` |
| `map:` | Map results | `map:san francisco` |
| `movie:` | Movie information | `movie:inception` |
| `weather:` | Weather information | `weather:london` |
| `source:` | News from specific source | `cybersecurity source:reuters` |
| `-` | Exclude term | `security -jobs` |
| `OR` | Either term | `(hacking OR security)` |
| `*` | Wildcard | `"admin * panel"` |
| `""` | Exact match | `"exact phrase match"` |
| `..` | Number range | `laptop $500..$1000` |
| `@` | Social media search | `@username` |
| `#` | Hashtag search | `#cybersecurity` |

### Quick Combination Templates

```
# Find specific files on target
site:target.com filetype:pdf confidential

# Discover admin panels
site:target.com (inurl:admin OR inurl:login) -demo

# Find exposed directories
intitle:"index of" site:target.com

# Technology fingerprinting
site:target.com "powered by" OR "built with"

# Subdomain enumeration
site:*.target.com -www

# API endpoint discovery
site:target.com inurl:api OR inurl:v1 OR inurl:v2

# Find contact information
site:target.com "@target.com" (contact OR email)

# Exposed credentials (educational)
site:target.com filetype:env "PASSWORD"

# Document intelligence
site:target.com (filetype:pdf OR filetype:docx) (confidential OR internal)

# Error pages (potential info leakage)
site:target.com intitle:"error" OR intitle:"404"
```

---

## ⚠️ Limitations of Google Operators

### Google Rate Limiting

- **Issue**: Google detects and throttles automated or rapid queries
- **Symptoms**: CAPTCHA challenges, temporary IP blocks, reduced result accuracy
- **Solutions**: Use delays between queries, rotate IP addresses (ethically), use Google's official APIs

### Personalized Results

- **Issue**: Google tailors results based on:
  - Search history
  - Location
  - Language preferences
  - Signed-in account
- **Impact**: Results may vary between users and sessions
- **Solutions**: Use incognito mode, clear cookies, use VPN for neutral location

### Index Delays

- **Issue**: Google's index is not real-time
- **Impact**: Recent content may not appear immediately
- **Timeframe**: Can range from hours to weeks for new content

### False Positives

- **Issue**: Operators may return unexpected results
- **Examples**:
  - Cached versions may be outdated
  - `site:` might miss subdomains
  - `filetype:` can be circumvented by renaming files
- **Mitigation**: Manually verify critical findings

### Content Removal

- **Issue**: Content may be removed due to:
  - DMCA requests
  - Right to be forgotten laws (GDPR)
  - Webmaster requests
  - Legal orders
- **Impact**: Cached pages may disappear

### Operator Deprecation

Some operators have been deprecated or limited:
- `+` (force inclusion) - deprecated
- `~` (synonym search) - deprecated
- `link:` - severely limited
- `inanchor:` - limited availability

### Search Result Limits

- Google typically shows only the first 400-500 results for any query
- Very broad searches may be artificially limited
- Deep pagination is not possible

---

## 🛠️ Tools That Enhance Google Dorking

### Google Advanced Search
**URL**: [https://www.google.com/advanced_search](https://www.google.com/advanced_search)
- **Description**: Official GUI for constructing complex queries
- **Benefits**: User-friendly interface, no syntax memorization required
- **Use Case**: Beginners, quick filtering, visual query building

### GHDB (Google Hacking Database)
**URL**: [https://www.exploit-db.com/google-hacking-database](https://www.exploit-db.com/google-hacking-database)
- **Description**: Curated database of security-focused dorks maintained by Offensive Security
- **Categories**:
  - Sensitive Directories
  - Files Containing Passwords
  - Vulnerable Files
  - Vulnerable Servers
  - Error Messages
  - Files Containing Juicy Info
- **Use Case**: Security research, penetration testing, vulnerability discovery

### Ahrefs / SEMrush
**Purpose**: SEO and competitive analysis
- **Ahrefs**: Advanced site explorer, backlink analysis, content research
- **SEMrush**: Keyword research, domain analytics, market intelligence
- **OSINT Value**: Discover competitor strategies, analyze web presence, track domain changes

### Shodan
**URL**: [https://www.shodan.io](https://www.shodan.io)
- **Description**: Search engine for Internet-connected devices
- **Comparison to Google**:
  - Google indexes web content; Shodan indexes devices/services
  - Direct banner grabbing and service identification
  - Real-time vulnerability scanning
- **Use Case**: IoT security, infrastructure mapping, exposed service discovery

### Additional Tools

#### Dorksearch
**URL**: [https://dorksearch.com](https://dorksearch.com)
- Fast dork query engine
- Pre-built dork categories
- API access available

#### Google Dork Scanner (GDS)
- Automated dork scanning
- Customizable dork lists
- Report generation

#### Recon-ng
- OSINT framework with Google dork modules
- Scriptable reconnaissance
- Data correlation

#### theHarvester
- Email, subdomain, and host reconnaissance
- Multiple search engine support
- Automated OSINT gathering

#### SpiderFoot
- Automated OSINT tool
- 200+ modules including Google dorks
- Correlation and visualization

#### Wayback Machine (Internet Archive)
**URL**: [https://archive.org/web](https://archive.org/web)
- View historical versions of websites
- Recover deleted content
- Track changes over time

#### Have I Been Pwned
**URL**: [https://haveibeenpwned.com](https://haveibeenpwned.com)
- Check if emails/domains are in data breaches
- Complementary to Google operator research

---

## 🔮 What More Can Be Added to This Project?

### Interactive Dork Generator
- **Description**: Web-based tool where users select categories and automatically generate dork queries
- **Features**:
  - Dropdown menus for operators
  - Real-time query preview
  - Copy-to-clipboard functionality
  - Query history tracking
- **Technology Stack**: React/Vue.js frontend, Firebase/Supabase backend

### CLI Tool
- **Name**: `dork-cli` or `google-operator-tool`
- **Features**:
  ```bash
  dork-cli search --site example.com --filetype pdf --keyword confidential
  dork-cli generate --category "admin panels" --target example.com
  dork-cli scan --scope-file targets.txt --output json
  ```
- **Technology**: Python (Click/Typer), Node.js (Commander), or Go
- **Integrations**: Export to CSV, JSON, Markdown reports

### Browser Extension
- **Features**:
  - Right-click context menu for instant dorks
  - Sidebar with common operator templates
  - Syntax highlighting for complex queries
  - Quick domain/filetype filters
  - Save favorite dork patterns
- **Platforms**: Chrome, Firefox, Edge
- **Technology**: JavaScript, WebExtensions API

### Web-Based OSINT Dashboard
- **Features**:
  - Multi-query parallel execution
  - Result aggregation and deduplication
  - Visual mapping of discovered assets
  - Timeline view of cached content
  - Export findings to PDF/CSV
  - Collaboration features (team sharing)
- **Technology**: Next.js, D3.js for visualizations, Supabase/PostgreSQL

### Dataset of Safe Example Dorks
- **Structure**:
  ```
  dorks/
  ├── educational/
  ├── research/
  ├── seo/
  ├── journalism/
  └── bug-bounty/
  ```
- **Format**: JSON/YAML with metadata
- **Metadata**: Category, risk level, description, example results
- **Community Contribution**: GitHub-based submission system

### Automation Ideas (Python Scripts)

#### Subdomain Enumerator
```python
# subdomain_enum.py
def google_subdomain_enum(domain):
    dork = f"site:*.{domain} -site:www.{domain}"
    # Implementation with requests + BeautifulSoup
```

#### Sensitive File Finder
```python
# sensitive_finder.py
def find_sensitive_files(domain, filetypes):
    for ft in filetypes:
        dork = f"site:{domain} filetype:{ft} (password OR confidential)"
        # Implementation
```

#### Report Generator
```python
# report_gen.py
def generate_markdown_report(results):
    # Create detailed OSINT report with timestamps
    # Include screenshots, metadata, risk ratings
```

#### Automated Reconnaissance Pipeline
- Chain multiple dorks
- Deduplicate results
- Check for live endpoints
- Generate executive summary

### Video Tutorial Series
- Beginner to advanced operator usage
- Real-world OSINT investigations (redacted)
- Tool demonstrations
- Ethical hacking scenarios

### API Service
- RESTful API for dork generation
- Rate-limited queries
- Authentication/API keys
- Endpoint examples:
  ```
  POST /api/generate-dork
  GET /api/dork-categories
  POST /api/execute-search
  ```

### Mobile Application
- iOS/Android app for on-the-go OSINT
- Saved query templates
- QR code scanning for quick domain searches
- Secure credential storage for authorized testing

### Integration Plugins
- Burp Suite extension for reconnaissance
- OWASP ZAP add-on
- Maltego transforms
- Metasploit auxiliary modules

### Machine Learning Enhancements
- NLP-based dork suggestion
- Pattern recognition in results
- Anomaly detection (unusual exposures)
- Risk scoring algorithm

### Gamification/Training Platform
- CTF-style challenges using dorks
- Progressive difficulty levels
- Leaderboards for ethical researchers
- Certification upon completion

---

## ⚖️ Disclaimer & Ethics

### Educational Purpose Only

This repository and all associated materials are provided **strictly for educational, research, and authorized security testing purposes**.

### Legal Disclaimer

- The creators and contributors of this project **do not endorse or encourage illegal activity**
- **You are solely responsible** for your actions when using these techniques
- Unauthorized access to computer systems is **illegal** under laws including but not limited to:
  - Computer Fraud and Abuse Act (CFAA) in the United States
  - Computer Misuse Act in the United Kingdom
  - European Union Cybercrime Directive
  - Local and international cybercrime laws

### Ethical Guidelines

✅ **ACCEPTABLE USE:**
- Academic research with proper authorization
- Authorized penetration testing and bug bounty programs
- OSINT gathering from publicly accessible sources
- Personal security audits of your own assets
- Educational demonstrations in controlled environments
- Journalism and investigative research within legal bounds

❌ **PROHIBITED USE:**
- Accessing systems without explicit permission
- Exploiting discovered vulnerabilities without authorization
- Downloading or distributing sensitive/private data
- Conducting denial-of-service attacks
- Circumventing authentication mechanisms
- Any activity that violates terms of service or laws

### No Responsibility for Misuse

The authors, contributors, and maintainers of this project:
- **Disclaim all responsibility** for any misuse of the information provided
- **Are not liable** for any damages, legal consequences, or harm resulting from the use or misuse of these techniques
- **Strongly encourage** ethical behavior and legal compliance
- **Recommend** consulting with legal counsel before conducting security research

### Responsible Disclosure

If you discover vulnerabilities using these techniques:
1. **Do not exploit** the vulnerability
2. **Document** your findings professionally
3. **Report** to the appropriate security contact (security@domain.com)
4. **Allow reasonable time** for remediation (typically 90 days)
5. **Do not publicly disclose** until the issue is resolved or the disclosure deadline passes

### Privacy & Data Protection

- Respect individuals' privacy rights
- Comply with GDPR, CCPA, and other data protection regulations
- Do not collect or store personal data without consent
- Be mindful of sensitive information you may encounter

### Professional Conduct

As security researchers and OSINT practitioners:
- Operate with **integrity and transparency**
- Follow **responsible disclosure practices**
- Respect **scope and boundaries**
- Prioritize **harm prevention**
- Contribute to a **safer digital ecosystem**

---

## 🤝 Contributing

Contributions are welcome! Please follow these guidelines:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/new-dork-category`)
3. **Commit** your changes (`git commit -m 'Add new OSINT category'`)
4. **Push** to the branch (`git push origin feature/new-dork-category`)
5. **Open** a Pull Request

### Contribution Ideas
- Add new dork examples (with ethical use cases)
- Improve documentation
- Fix typos or clarify explanations
- Add tool recommendations
- Translate to other languages
- Create visual diagrams or infographics

### Code of Conduct
- Be respectful and professional
- Provide constructive feedback
- Ensure all contributions align with ethical guidelines
- Do not submit malicious or illegal content

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### Summary
- ✅ Use for personal and commercial projects
- ✅ Modify and distribute
- ✅ Use for educational purposes
- ⚠️ No warranty provided
- ⚠️ Authors not liable for misuse

---

## 📞 Contact & Support

- **Issues**: Open an issue on GitHub for bugs or feature requests
- **Discussions**: Use GitHub Discussions for questions and community interaction
- **Security**: Report security vulnerabilities privately to [security contact email]

---

## 🙏 Acknowledgments

- Google for maintaining a powerful search platform
- The OSINT community for sharing knowledge
- Offensive Security for maintaining GHDB
- Security researchers who practice responsible disclosure
- All contributors to this project

---

## 📚 Additional Resources

### Learning Resources
- [OSINT Framework](https://osintframework.com/)
- [SANS OSINT Summit](https://www.sans.org/cyber-security-training-events/)
- [Trace Labs OSINT Challenges](https://www.tracelabs.org/)
- [Bellingcat's Online Investigation Toolkit](https://www.bellingcat.com/)

### Communities
- [r/OSINT on Reddit](https://www.reddit.com/r/OSINT/)
- [OSINT Curious](https://osintcurio.us/)
- [IntelTechniques Forum](https://inteltechniques.com/blog/)

### Books
- "Open Source Intelligence Techniques" by Michael Bazzell
- "The Art of Invisibility" by Kevin Mitnick
- "Social Engineering: The Science of Human Hacking" by Christopher Hadnagy

---

<div align="center">

### ⭐ If you found this guide helpful, please star this repository!

**Remember: With great power comes great responsibility. Use these techniques ethically and legally.**

Made with 🔍 for the OSINT and Cybersecurity Community

</div>
#   A d v a n c e d - G o o g l e - O p e r a t o r s  
 