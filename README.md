# sumrecon
Repo forked from [Gr1mmie/sumrecon](https://github.com/Gr1mmie/sumrecon)

## Modifications

- [+] add verification for `certspotter` and `subjack` (idea of [this pull request](https://github.com/Gr1mmie/sumrecon/pull/6) of [phanikaran](https://github.com/phanikaran)
- [+] The original script was searching 2 times in the whole system (`/`) for the [Eyewitness](https://github.com/RedSiege/EyeWitness) python file, in this script I removed the heavy search by using the package [eyewitness](https://www.kali.org/tools/eyewitness/). Therefore, the verification for eyewitness is faster and better, that can do a huge difference in the script's speed.
  - It replaces `[ ! -x "$(find / -type f -name 'EyeWitness')" ]` by `[ ! -x "$(command -v eyewitness)" ]` 2 times (see this [commit](https://github.com/nathanoell/sumrecon/commit/6c6a508e2ae820b7e550d3e23a1c9ab87290e244))

## DEPENDENCIES
* assetfinder - https://github.com/tomnomnom/assetfinder
* amass - https://github.com/OWASP/Amass
* certspotter - #curl -s https://certspotter.com/api/v0/certs\?domain\=$url | jq '.[].dns_names[]' | sed 's/\"//g' | sed 's/\*\.//g' | sort -u (set as alias)
* sublist3r - https://github.com/aboul3la/Sublist3r
* httprobe - https://github.com/tomnomnom/httprobe
* waybackurls - https://github.com/tomnomnom/waybackurls
* whatweb - https://github.com/urbanadventurer/WhatWeb
* nmap - https://nmap.org/download.html
* eyewitness - https://github.com/FortyNorthSecurity/EyeWitness
