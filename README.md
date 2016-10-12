![Alt text](img/net.security.tiny.jpg?raw=true "net.security")

[![Project Status: WIP - Initial development is in progress, but there has not yet been a stable, usable release suitable for the public.](http://www.repostatus.org/badges/latest/wip.svg)](http://www.repostatus.org/#wip) 
[![Build Status](https://travis-ci.org/r-net-tools/net.security.svg?branch=master)](https://travis-ci.org/r-net-tools/net.security) 
[![Coverage Status](https://coveralls.io/repos/github/r-net-tools/net.security/badge.svg?branch=master)](https://coveralls.io/github/r-net-tools/net.security?branch=master)


#### Package for Data Driven Security purposes.

## Install

From R console just type:  
`devtools::install_github(repo = "r-net-tools/net.security")`  

If you want to test future features, just add branch as parameter:  
`devtools::install_github(repo = "r-net-tools/net.security", ref = "devel")`  

## Usage
Load package using `library("net.security")` then you can access directly to security standards data frames.
It also includes an API server mapping data driven security functions defined in ddsecurity.R

### Security Standards
#### CVE
Reference: http://cve.mitre.org/about/faqs.html  
Raw Data:
 - MITRE: http://cve.mitre.org/data/downloads/index.html#download
 - NIST: https://nvd.nist.gov/download.cfm  

Data Frame: `View(cves)`

#### CWE
Reference: http://cwe.mitre.org/data/index.html#documentation  
Raw Data: https://cwe.mitre.org/data  
Data Frame: `View(cwes)`  

#### CPE
Reference: https://nvd.nist.gov/cpe.cfm  
Raw Data: http://static.nvd.nist.gov/feeds/xml/cpe/dictionary/official-cpe-dictionary_v2.3.xml.gz  
Data Frame: `View(cpes)`  
 
### CAPEC
Reference: https://capec.mitre.org/data/xsd/ap_schema_v2.7.1.xsd  
Raw Data: https://capec.mitre.org/data/xml/capec_v2.8.xml  
Data Frame: `View(capec$attacks)` or `View(capec$categories)`  

### OVAL
Reference: https://oval.cisecurity.org/  
Raw Data: https://oval.cisecurity.org/repository/download/5.11.1/all/oval.xml  
Data Frame: `View(oval)`  

### API
#### Start Server
Ensure that Rscript is in your PATH. Open system command line, go to this package and run the api.R script.
```bash
net.security$ Rscript api.R
Starting server to listen on port 8000
```
Then open a browser and go to: [http://127.0.0.1:8000/cveinfo?cve.id=CVE-2010-2010](http://127.0.0.1:8000/cveinfo?cve.id=CVE-2010-2010)

![Alt text](img/api.screenshot.jpg?raw=true "api net.security")
