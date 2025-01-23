<p align="center"><img src="https://i.imgur.com/8kltxBa.png" /></p>

<h1 align="center">🚀 CORS Misconfiguration Scanner</h1>

<p align="center">
  A Python framework designed to aid security testing of CORS (Cross-Origin Resource Sharing) configurations.
</p>

<hr>

### 🛡️ What is CORS Misconfiguration?
CORS Misconfiguration is a weakness in the server configuration that governs the cross-origin resource sharing mechanism. CORS that is not properly configured can allow:

1. 📂 Credential exploitation (for example, cookies and tokens).
2. 🎯JavaScript-based attacks to steal sensitive data.

### ✨ Key Features

1. 🔍 Detects Vulnerable CORS Headers:
Scans for headers such as Access-Control-Allow-Origin and Access-Control-Allow-Credentials.
2. 📊 Visual Report:
Displays the security status of each domain with color coding using Colorama.
3. 📁 Multi-Domain Support:
Checks multiple domains from the input file.
4. ⚡ Easy to Use
Simple design for easy vulnerability analysis.

### 🛠️ Installation
To install CORSpect.py, make sure you have Python version 3.6 or later installed, then download this tools file from your repository or directory.

Installation Steps:
1. Make sure you have Python 3.6 or later:
```
python3 --version
```
2. Install the necessary dependencies with the following command:
```
pip install -r requirements.txt
```

### What is Needed to Run CORSpect.py?
Python 3.6 or later is required to run CORSpect.py.
Make sure you have the following modules:
`requests`
`colorama`
If you have problems with module installation, use:
```
pip install requests colorama
```
#### Installation Troubleshooting
For Debian/Ubuntu Systems
If there are installation issues (especially regarding additional libraries), make sure you have the basic development tools required for Python:
```
sudo apt-get install python3-dev build-essential
```
### 📖 How to Use CORSpect.py
1. Run CORSpect.py directly through the terminal:
```
python3 CORSpect.py
```
2. Enter the name of a file containing a list of target domains to check, for example `domains.txt`.
```
Masukkan path file domain (contoh: domain.txt): domains.txt
```
4. CORSpect.py will read the domains, check the CORS headers of each target, and display the results for misconfiguration.
5. Scan Result:
✅ Secure: There is no misconfiguration in the CORS header.
❌ Vulnerable: CORS configuration allows exploitation.

### 📂 Domain File Format
The domains.txt file should be formatted like this:
```
https://example1.com
http://example2.com
example3.com
```
Notes: If the URL has no protocol (`http://` or `https://`), the tool will automatically add `https://`.

### 🧪 Usage Example
1. Starting a Scan
```
Masukkan path file domain (contoh: domain.txt): domains.txt
[INFO] Total domain yang ditemukan: 5

[INFO] Memeriksa CORS misconfiguration untuk https://example.com
 - Access-Control-Allow-Origin: *
   [VULNERABLE] Mengizinkan semua origin (*), ini rentan terhadap eksploitasi!
 - Access-Control-Allow-Credentials: true
   [VULNERABLE] Kombinasi Allow-Credentials: true dan Allow-Origin: * adalah konfigurasi yang sangat berbahaya!

[RESULT] Domain https://example.com terdeteksi rentan terhadap CORS Misconfiguration.

```

### The Difference Between Secure and Vulnerable Domains
# 🎯 Vulnerable Domains
Domains that have the following configurations are considered vulnerable:
1. `Access-Control-Allow-Origin: *`
2. `Access-Control-Allow-Credentials: true along with Allow-Origin: *.`

# 🛡️ Secure Domains
1. Do not have any CORS related headers.
2. Existing CORS headers are configured specifically for trusted domains.

### 🎯 Results and Analysis
1. Vulnerable:
If the domain is vulnerable to CORS misconfiguration.
2. Safe:
If no CORS headers are found or the configuration is considered safe.

## ⚙️ License
License
Copyright (C) 2025 by Tengku Arya Saputra

Use of CORSpect.py to scan systems without explicit permission from the owner may violate the law in your country. The author is not responsible for any misuse or damage caused by this tool.
