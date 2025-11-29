# Bunkernet

This project is not fancy or impressive in any way. It is just a bunch of configurations to set up a local internet (intranet) using several free open source projects by awesome people who made awesome stuff. The goal is to easily turn a mini PC, or similar machine, into a WiFi hotspot running a suite of web services you'll want if you lose, or already don't have, access to the internet where the bunkernet box will run.

## Why not just use IIAB?
This project is similar to IIAB (https://github.com/iiab/iiab) with a few specific differences.
- IIAB is designed for running on a raspberry pi.
  - Bunkernet can run on anything debian can (which is pretty much everything)
- IIAB isn't very customizable. You can't easily add new services and bookmark them on the dashboard.
    - Bunkernet uses portainer and dashy, so that anyone who knows what they're doing can easily host new services and add them to the dashboard.

IIAB is a great project and I love that it exists, but when using it I felt restricted by what I could run it on and how I could customize it, which ultimately comes down to the fact that it was never designed for the use cases I had. Thus, bunkernet.

Terms:
- Bunkernet: an intranet of web services and archives
- Bunkernet box: a machine bunkernet is running on

## ✨ Features ✨

- **Dashboard**
    - [Dashy](https://dashy.to/) (easy way to access everything)
- **Media & Content**
    - [Kiwix](https://kiwix.org/) (access Wikipedia, TedTalks, online forums and more)
    - [Archivebox](https://archivebox.io/) (archive whatever website you want)
- **File storage, editing, and organization**
    - [Nextcloud](https://nextcloud.com/) (cloud storage)
    - [OnlyOffice](https://www.onlyoffice.com/) (Microsoft file editing)
    - [SterlingPDF](https://www.stirling.com/) (PDF editing, signing, etc...)
- **AI**
    - [Open Web UI](https://openwebui.com/) (Robust AI interface)
    - [Ollama](https://ollama.com/) (AI server)
- **Misc tools**
    - [LubeLogger](https://lubelogger.com/) (vehicle records management)
    - [LibreTranslate](https://github.com/LibreTranslate/LibreTranslate/) (translate between different langauges)
- **Server management**
    - [PiHole](https://pi-hole.net/) (DNS and Ad blocking)
    - [Nginx Proxy Manager](https://nginxproxymanager.com/) (reverse proxy)
    - [Portainer](https://www.portainer.io/) (docker container management)

In general, the benefits of self hosting are accessibility, speed, security, and privacy. 

### Accessibility
By combining the following services you can address the majority of needs in the digital age without requiring an internet conncetion. The whole world could go out, but as long as you have power, you have the files and services you need.

### Speed
Assuming you're running these services on a fast enough system, you're load times might actually improve. No more waiting for a page to load or movie to buffer due to pesky neighbors hogging all the bandwidth.

### Security
While no system is perfectly secure, it sure is hard to hack something when it's completely disconnected from the internet. So unless you leave it connected or someone gets ahold of the device this is running on physically, you're in a pretty good place.

### Privacy
Nothing is being tracked and sent to anyone. You can use all of these services carefree of any future privacy policy changes or government overrides.


## Internal Network and Port Mapping

Network mask: 172.1.0.0/16

| **Application**            | **IP**        | **Port(s)**                |
|----------------------------|---------------|----------------------------|
| pihole                     | 172.1.0.53    | 53, 8853 (admin port)      |
| Nginx Proxy Manager        | 172.1.0.80    | 80, 443, 8801 (admin port) |
| Portainer                  | 172.1.0.2     | 9443                       |
| NextCloud                  | 172.1.0.3     | 8802                       |
| NextCloud DB               | 172.1.0.4     |                            |
| Redis                      | 172.1.0.5     |                            |
| Only Office                | 172.1.0.6     | 8804, 8803 (web)           |
| Ollama                     | 172.1.0.7     | 11434                      |
| Open Web UI                | 172.1.0.8     | 8805                       |
| Dashy                      | 172.1.0.9     | 8806                       |
| Kiwix                      | 172.1.0.10    | 8807                       |
| LubeLogger                 | 172.1.0.11    | 8808                       |
| Sterlingpdf                | 172.1.0.12    | 8809                       |
| Archivebox                 | 172.1.0.13    | 8810                       |
| Sonic (for archive box)    | 172.1.0.14    | 1491                       |
| Libre Translate            | 172.1.0.15    | 8811                       |
