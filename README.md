# spfdmarc-checker
A script to analyze a domain's MX, SPF, and DMARC records, providing a detailed report, highlighting potential security issues, and suggesting improvements.

![image](https://raw.githubusercontent.com/pndw00/spfdmarc-checker/refs/heads/main/images/example.png)

## Prerequisites
- git
- dig

## Installation
1. Clone the repository:
```sh
git clone https://github.com/pndw00/spfdmarc-checker.git
```

2. Navigate into the project directory
```sh
cd spfdmarc-checker
```

3. Make `spfdmarc-checker` executable:
```sh
chmod +x spfdmarc-checker
```

4. Add alias for `spfdmarc-checker` command:
```sh
echo "alias spfdmarc-checker=\"$PWD/spfdmarc-checker\"" >> ~/.zshrc
```
Replace `.zshrc` with `rc` file of your shell.
To make your new alias affective you need to reload your shell.

## How to use
```txt
$ spfdmarc-checker --help
Usage: spfdmarc-checker [options] domain.com

Options:
  -h, --help           Show this help message
  --mx                 [✓] Only analyze MX record
  --spf                [✓] Only analyze SPF record
  --dmarc              [✓] Only analyze DMARC record
  --dkim               [✓] Only analyze DKIM record
  -s, --selector SEL   Test a specific DKIM selector
  -q, --quiet          Hide header

Description:
  This script retrieves and analyzes MX, SPF, DMARC and DKIM records for the given domain.
  It helps auditing email security quickly and visually.

Example:
  spfdmarc-checker example.com                     # Analyze all records
  spfdmarc-checker --mx example.com                # Analyze only MX
  spfdmarc-checker --spf example.com               # Analyze only SPF
  spfdmarc-checker --dmarc example.com             # Analyze only DMARC
  spfdmarc-checker --dkim example.com              # Analyze only DKIM
  spfdmarc-checker --dkim -s default example.com   # Analyze DKIM for a specific selector

Symbols:
  [✓] Success / Found
  [!!] Warning / Partial
  [✗] Error / Missing / Dangerous
```
