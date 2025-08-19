# 🕵️‍♂️ VulnSniffer

[![Python](https://img.shields.io/badge/Python-3.7%2B-blue?logo=python)](https://www.python.org/)
[![License](https://img.shields.io/github/license/my895/VulnSniffer)](LICENSE)
[![Issues](https://img.shields.io/github/issues/my895/VulnSniffer)](https://github.com/my895/VulnSniffer/issues)

> **VulnSniffer** is a Python-based vulnerability scanner designed to detect the [OWASP ](https://owasp.org/www-project-top-ten/) vulnerabilities in your web applications.  
> Automate your security checks and keep your applications safe with ease!

---

## 📋 Table of Contents

- [Features](#features)
- [OWASP Top 10 Coverage](#owasp-top-10-coverage)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)
- [Sample Output](#sample-output)
- [Contributing](#contributing)
- [License](#license)
- [Acknowledgements](#acknowledgements)

---

## ✨ Features

- 🔍 **Automatic scanning** for OWASP Top 10 vulnerabilities.
- 📝 **Detailed reports** in multiple formats (JSON, HTML, TXT).
- ⚡ **Fast & lightweight**: Built with pure Python, no heavy dependencies.
- 🛠️ **Customizable scanning**: Easily configure scan targets and methods.
- 🧩 **Modular design**: Add or update vulnerability detectors with ease.
- 📑 **Clear documentation** and user-friendly CLI.

---
## 🛡️ OWASP Top 10 Coverage

VulnSniffer is built to detect the following vulnerability classes:

1. **A01: Injection** (SQL, NoSQL, Command, etc.)
2. **A02: Broken Authentication**
3. **A03: Sensitive Data Exposure**
4. **A04: XML External Entities (XXE)**
5. **A05: Broken Access Control**
6. **A06: Security Misconfiguration**
7. **A07: Cross-Site Scripting (XSS)**
8. **A08: Insecure Deserialization**
9. **A09: Using Components with Known Vulnerabilities**
10. **A10: Insufficient Logging & Monitoring**

> *Note: Exact coverage depends on implementation and configuration. See [docs/coverage.md](docs/coverage.md) for details.*

---

## 🚀 Installation

### Prerequisites

- Python 3.7+
- `pip`

### Steps

```bash
git clone https://github.com/my895/VulnSniffer.git
cd VulnSniffer
pip install -r requirements.txt
```

Or install directly via pip (if published):

```bash
pip install vuln-sniffer
```

---


### Common Options

| Argument                  | Description                                      |
|---------------------------|--------------------------------------------------|
| `--target`                | URL or IP address of the web app to scan         |
| `--output`                | Output file for the scan report                  |
| `--format`                | Report format: `json`, `html`, `txt`             |
| `--vulns`                 | Comma-separated list of vulnerabilities to scan  |
| `--threads`               | Number of concurrent threads (default: 4)        |
| `--config`                | Path to custom configuration file                |
| `--help`                  | Show help message and exit                       |

#### Example

```bash
python scanner.py --target https://example.org \
                  --output report.json \
                  --format json \
                  --vulns injection,xss
```

---

## ⚙️ Configuration

You can use a custom config file to fine-tune the scanner:

```yaml
# config.yaml example
target: https://example.com
threads: 8
vulnerabilities:
  - injection
  - xss
  - security_misconfiguration
report:
  format: html
  output: vuln_report.html
```

Run with config:

```bash
python scanner.py --config config.yaml
```

---

## 📊 Sample Output

```json
{
  "target": "https://example.com",
  "scan_date": "2025-08-19",
  "vulnerabilities": [
    {
      "type": "SQL Injection",
      "location": "/login",
      "severity": "high",
      "evidence": "' OR 1=1 --"
    },
    {
      "type": "XSS",
      "location": "/search",
      "severity": "medium",
      "evidence": "<script>alert(1)</script>"
    }
  ]
}
```

> For more sample outputs and explanations, see [docs/sample_reports](docs/sample_reports).

---

## 🤝 Contributing

Contributions are very welcome!  
See [CONTRIBUTING.md](CONTRIBUTING.md) for instructions.

- Fork the repo
- Create your feature branch (`git checkout -b feature/AmazingFeature`)
- Commit your changes (`git commit -am 'Add some AmazingFeature'`)
- Push to the branch (`git push origin feature/AmazingFeature`)
- Open a Pull Request

---

## 📜 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙏 Acknowledgements

- [OWASP Top 10](https://owasp.org/www-project-top-ten/)
- [Requests](https://docs.python-requests.org/)
- [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/)


