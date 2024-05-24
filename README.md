# Xray + Argo for PaaS

Born for container platforms

* * *

# Table of contents

- [Project Features](README.md#Project Features)
- [Deployment](README.md#Deployment)
- [Thanks to the following authors for their articles and projects](README.md#Thanks to the following authors for their articles and projects)
- [Disclaimer](README.md#Disclaimer)

* * *

## Project Features:
* This project is used to deploy Xray on the PaaS platform, and the solution adopted is Argo + Xray + WebSocket + TLS
* Use CloudFlare's Argo Tunnel, directly select + tunnel, CDN no longer needs to be workers
* Xray core files have been "specially processed" so that each project is different, greatly reducing the risk of being blocked and implicated
* Backflow and splitting, supporting 4 mainstream protocols of Xray: vless / vmess / trojan / shadowsocks
* The uuid of vmess and vless, the password of trojan and shadowsocks, and the ws path of each protocol can be customized or use the default value
* Integrated Nezha probe, you can choose whether to install it
* No disguised web pages are used to reduce resource usage, because it will only be blocked by the platform and almost never by GFW
* Node information is output in the form of `Clash` and `Little Rocket Link`

## Deployment:
* Mirror `fscarmen/argo-xary:latest` (Note: xray is not a typo, just a keyword change)

* Variables used by the PaaS platform

  | Variable name | Required | Default value                        | Remarks |
  | ------------ | ------ |--------------------------------------| ------ |
  | UUID | No | 71e81693-65bf-4a87-ba99-7422c4053f5d | Can be generated online https://www.zxgj.cn/g/uuid |
  | WSPATH | No | argo                                 | Do not start with /, the protocol path is `/WSPATH-protocol`, such as `/argo-vless`, `/argo-vmess`, `/argo-trojan`, `/argo-shadowsocks` |
  | NEZHA_SERVER | No |                                      | IP or domain name of the Nezha probe server |
  | NEZHA_PORT | No|                                      | Nezha probe server port |
  | NEZHA_KEY | No |                                      | Nezha probe client-specific key |
  | PORT | No | 8443                                 | Inbound port, you need to forward (route) this port in the platform |

* Variables used by GitHub Actions

  | Variable name | Notes |
    |--------------|--------------|
  | DOCKER_USERNAME | Dockerhub username |
  | DOCKER_PASSWORD | Dockerhub password |
  | DOCKER_REPO | Dockerhub repository name |


<img width="1577" alt="image" src="https://user-images.githubusercontent.com/92626977/213895533-ce4bad42-a1f0-4ee4-8590-c5bbae5989c6.png">
<img width="1090" alt="image" src="https://user-images.githubusercontent.com/92626977/213895730-19a361b8-db3f-4f93-8656-325d76e5cbf9.png">
<img width="1670" alt="image" src="https://user-images.githubusercontent.com/62703343/213903422-b3183614-a36a-4b93-97f0-a381f4462b4d.png">

## Thanks to the following authors for their articles and projects:
Netizen @meihao202 provided information for participation

## Disclaimer:
* This program is for learning and understanding only, not for profit. Please delete it within 24 hours after downloading. It cannot be used for any commercial purpose. The text, data and pictures are all copyrighted. If reproduced, the source must be indicated.
* The use of this program must comply with the deployment disclaimer. The use of this program must comply with the laws and regulations of the deployment server location, the country where it is located, and the country where the user is located. The program author is not responsible for any improper behavior of the user.