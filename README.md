# Port Scanner

A multi-threaded TCP port scanner built in Python that scans one or more hosts for open ports, attempts to fingerprint services, and highlights simple vulnerability indicators. Designed for learning, security testing, and basic network auditing.

---

##  Features
- Scan single or multiple targets
- Custom port ranges or scan all 65,535 ports
- Multi-threading for speed
- Basic banner + service detection (FTP, SSH, HTTP, SMTP, etc.)
- Simple signature-based vulnerability hints
- Optional JSON output
- Graceful interrupt handling (Ctrl+C)

---

##  Tech Stack
- Python 3.x
- argparse, socket, threading, json (built-in)
- tqdm (progress bar)
- termcolor (colored output)
- ipython (optional, for screen clearing)

---

##  Installation
Clone the repository:
git clone https://github.com/cruiex/portscanner.git
cd portscanner

Install dependencies manually:
pip install tqdm termcolor ipython
(If you're not using IPython anymore, skip it.)

---

##  Usage
python portscanner.py -t <targets> [-p <port-range>] [-T <timeout>] [-n <num-threads>] [-o <output>] [-v]

---

##  Options
-t, --targets      Target IP(s) or domain(s), required  
-p, --port-range   Custom range (1-500, 20-80, all), default 1-100  
-T, --timeout      Timeout in seconds, default 1.0  
-n, --num-threads  Threads per batch, default 10  
-o, --output       Save results to JSON  
-v, --verbose      Enable verbose mode  

---

##  Examples
Scan a single target:
python portscanner.py -t 192.168.1.1

Scan with custom range:
python portscanner.py -t scanme.nmap.org -p 1-1000

Scan multiple hosts + save output:
python portscanner.py -t example.com 192.168.1.5 -p all -o results.json

Verbose mode:
python portscanner.py -t localhost -v
