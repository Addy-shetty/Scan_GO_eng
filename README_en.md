<p align="center">
<a href="[https://github.com/wgpsec/ENScan_GO](https://github.com/wgpsec/ENScan_GO)">
<img src="README/logo.png" alt="Logo" width="80" height="80">
</a>
<h3 align="center">ENScan Go</h3>
<p align="center">
Targeting HW/SRC scenarios, solving various challenges in gathering domestic enterprise information.
<br />
<br />
<a href="[https://github.com/wgpsec/ENScan_GO/stargazers](https://github.com/wgpsec/ENScan_GO/stargazers)"><img alt="GitHub stars" src="[https://img.shields.io/github/stars/wgpsec/ENScan_GO](https://img.shields.io/github/stars/wgpsec/ENScan_GO)"/></a>
<a href="[https://github.com/wgpsec/ENScan_GO/releases](https://github.com/wgpsec/ENScan_GO/releases)"><img alt="GitHub releases" src="[https://img.shields.io/github/release/wgpsec/ENScan_GO](https://img.shields.io/github/release/wgpsec/ENScan_GO)"/></a>
<a href="[https://github.com/wgpsec/ENScan_GO/blob/main/LICENSE](https://github.com/wgpsec/ENScan_GO/blob/main/LICENSE)"><img alt="License" src="[https://img.shields.io/badge/License-Apache%202.0-blue.svg](https://img.shields.io/badge/License-Apache%202.0-blue.svg)"/></a>
<a href="[https://github.com/wgpsec/ENScan_GO/releases](https://github.com/wgpsec/ENScan_GO/releases)"><img alt="Downloads" src="[https://img.shields.io/github/downloads/wgpsec/ENScan_GO/total?color=brightgreen](https://img.shields.io/github/downloads/wgpsec/ENScan_GO/total?color=brightgreen)"/></a>
<a href="[https://goreportcard.com/report/github.com/wgpsec/ENScan_GO](https://goreportcard.com/report/github.com/wgpsec/ENScan_GO)"><img alt="Go Report Card" src="[https://goreportcard.com/badge/github.com/wgpsec/ENScan_GO](https://goreportcard.com/badge/github.com/wgpsec/ENScan_GO)"/></a>
<a href="[https://twitter.com/wgpsec](https://twitter.com/wgpsec)"><img alt="Twitter" src="[https://img.shields.io/twitter/follow/wgpsec?label=Followers&style=social](https://img.shields.io/twitter/follow/wgpsec?label=Followers&style=social)" /></a>







<a href="[https://github.com/wgpsec/ENScan_GO/discussions](https://github.com/wgpsec/ENScan_GO/discussions)"><strong>Explore more Tricks »</strong></a>





<br />
<a href="[https://github.com/wgpsec/ENScan_GO?tab=readme-ov-file#%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97](https://github.com/wgpsec/ENScan_GO?tab=readme-ov-file#%E4%BD%BF%E7%94%A8%E6%8C%87%E5%8D%97)">🧐How to Use</a>
·
<a href="[https://github.com/wgpsec/ENScan_GO/releases](https://github.com/wgpsec/ENScan_GO/releases)">⬇️Download</a>
·
<a href="[https://github.com/wgpsec/ENScan_GO/issues](https://github.com/wgpsec/ENScan_GO/issues)">❔Report Bug</a>
·
<a href="[https://github.com/wgpsec/ENScan_GO/discussions](https://github.com/wgpsec/ENScan_GO/discussions)">🍭Submit Request</a>
</p>

## 🤷‍♂️Disclaimer

The technologies, ideas, and tools mentioned in this article are solely for security-focused learning and exchange purposes. No one is permitted to use them for illegal purposes or profit. Otherwise, you bear the consequences yourself.

The data used is all public data; **we do not provide cracking or bypass methods**. Using this program may result in ⌈Account Anomalies⌋.

**If this program affects or infringes upon your legitimate rights, please contact us at** admin#wgpsec.org (replace # with @)

## ⚒️Features

* Supported Data Sources
* AiQiCha (AQC)
* TianYanCha (TYC)
* Kuaicha
* Fengniao
* QiChaCha (Not provided)
* XiaoLanBen (Not provided)


* Data Plugins
* Aladdin (Offline temporarily due to outdated data feedback)
* CoolApk
* Qimai Data
* ICP Filing Info Query API


* Queryable Information
* ICP Filing
* APP
* Weibo
* WeChat Official Accounts
* Holding Companies
* Suppliers
* Mini Programs
* Public Recruitment Info
* External Investment Info
* ...


* Practical Functions
* Supports merged export
* Regex filtering for companies
* Supports deep query (collecting multi-layer grand-subsidiaries)
* Supports API mode for tool integration



## User Guide

### First Time Use

Go to [RELEASE](https://github.com/wgpsec/ENScan_GO/releases) to download the compiled file for use.

When using for the first time, you need to use the -v command to generate the configuration file and configure Cookies.

```
./enscan -v

```

### Quick Start

*If you encounter access issues, please try using Burp or a proxy yourself.* If the program **exits abnormally** after starting, an `enscan.gob` cache file will be retained in the program directory. Please delete it manually if running new information.

**Default Company Info** (Website Filing, Weibo, WeChat Official Account, App)

```
./enscan -n Xiaomi

```

**Batch Query** (Text separated by lines, PID mode optional)

```
./enscan -f f.txt

```

**Companies with 100% External Investment Shareholding**

```
./enscan -n Xiaomi -invest 100

```

**Combined Filtering**

Companies with >51% shareholding, branch agencies, only ICP filing info

```
./enscan -n Xiaomi -field icp -invest 51  --branch

```

Collect Grand-subsidiaries (`deep` parameter, must be used with `invest`), >51% shareholding, branch agencies, only ICP filing info

```
./enscan -n Xiaomi -field icp -invest 51 --branch --deep 2

```

**Using Different Channels**

Use TianYanCha data source (or set to `all` to combine multiple data sources)

```
./enscan -n Xiaomi -type tyc

```

Use multiple data sources together (Multi-channel + filtering is currently not supported)

```
./enscan -n Xiaomi -type aqc,tyc

```

Use plugin channels

```
./enscan -n Xiaomi -type aqc,miit

```

**Please set request delay to prevent causing impact**

```
./enscan -n Xiaomi -delay 3

```

### Using MCP

Enable the MCP server; it will listen on local http://localhost:8080

```
./enscan --mcp

```

Taking Cherry Studio configuration as an example

After configuration is complete, enable the MCP service

After configuration, you can write prompts according to your needs. Welcome to share useful prompts [here](https://github.com/wgpsec/ENScan_GO/discussions/163).

### Cookie Configuration

**AQC**

If a security verification appears, please use a browser to get the cookie and pass the verification to continue. Default query is aiqicha.baidu.com.

Please do not directly `document.cookie` for Cookie info, as `http-only` options might prevent full copying, leading to login failure.

**TYC tycid**

After configuring COOKIE, configure tycid.

**TYC auth_token**

After configuring COOKIE, configure auth_token.

For other Cookies, please refer to methods to obtain them yourself.

### Options Description

#### **field (Get Fields)**

Use the parameter `field` to specify the information to query. Multiple parameters can be specified together for quick collection.

```
-n Xiaomi -field icp,app

```

Supports the following parameters:

* `icp` Website filing info
* `weibo` Weibo
* `wechat` WeChat Official Account
* `app` Application info
* `job` Recruitment info
* `wx_app` WeChat Mini Program
* `copyright` Software Copyright
* `supplier` Supplier info (determined via tender documents)
* Others (Updated based on plugin status)

#### **type (Data Source)**

Use the parameter `type` to specify the required API data source.

```
-n Xiaomi -type tyc

```

**Query Data Sources**

* `aqc`   AiQiCha
* `tyc`   TianYanCha
* `kc`    Kuaicha
* `rb`    Fengniao
* `all`   Query All

**Plugins**

* `aldzs` Aladdin (Mini Programs only)
* `coolapk` CoolApk (APP only)
* `qimai` Qimai Data (APP only)
* `miit`   HG-ha's ICP_Query (ICP filing, APP, Mini Program, Quick App) **Not maintained by Wolf Group, team members please use internal version**

#### Full Parameters

*Documentation may not be up to date, please refer to program prompts.*

| Parameter | Example | Description |
| --- | --- | --- |
| -n | Xiaomi | Keyword |
| -i | 29453261288626 | Company PID (Auto-detect type) |
| -f | file.txt | Batch query, text separated by lines (Optional PID mode) |
| -type | aqc | API Type |
| -o |  | Folder location for result output (Optional) |
| -is-merge |  | Merge export |
| -invest |  | Investment ratio |
| -field | icp | Get field info |
| -deep | 1 | Recursively search n layers of companies, must be used with invest |
| -hold |  | Whether to query holding companies (May require VIP account) |
| -supplier |  | Whether to query supplier info |
| -branch |  | Query branch agency (branch company) info |
| -is-branch |  | Deep query branch agency info (Huge quantity) |
| -api |  | Whether API mode |
| -debug |  | Whether to show detailed debug info |
| -is-show |  | Whether to display info output |
| -is-group |  | Query keyword is a Group |
| -is-pid |  | Whether batch query file contains Company PIDs |
| -delay |  | Delay per request (S), -1 is random delay 1-5S |
| -branch-filter |  | Provide a regex; branch agencies/subsidiaries matching this regex will be skipped |
| -proxy |  | Set proxy |
| -timeout |  | Default 1 (minute) timeout per request |
| -no-merge |  | Batch query [Cancel] merge export |
| -v |  | Version info |

### API Mode

**API Call Effect**

You can use https://enscan.wgpsec.org/api/info to experience it (Offline due to abuse).

🥹 The plat platform has stopped maintenance, please don't ask about it~

#### API Description

Acquired info will be queried and displayed in real-time. Can be integrated via API with other tools. Please note **do not expose to the public internet**.

**Get Info**

```
GET /api/info?name=Xiaomi&invest=100&branch=true

```

| Parameter | Type | Description |
| --- | --- | --- |
| name | Text | Full Company Name (Choose one of two) |
| type | Text, consistent with command params | Data Source |
| field | Text, consistent with command params | Filter specific info |
| depth | Number | Crawl how many layers of companies (e.g., 2 is grand-subsidiary) |
| invest | Number | Filter investment ratio |
| holds | true | Filter holding companies |
| supplier | true | Filter supplier info |
| branch | true | Filter branch info |
| output | true | If true, export excel table for download |

##### PRO Custom Mode (Faster Speed)

v2.0.0 version adds pro mode, supporting custom calls without going through scheduling logic. **type is mandatory**.

```
GET /api/pro/:type&type=xxx
Example
GET /api/pro/advance_filter?name=Xiaomi&type=aqc
GET /api/pro/get_page?name=29453261288626&type=aqc&page=1&filed=icp

```

| type | Parameter | Description |
| --- | --- | --- |
| advance_filter | name (required) | Query keyword |
| get_ensd |  | Get mapping field info |
| get_base_info | pid | Get company basic info |
| get_page | pid | Page through to get specified type info |

#### Startup Deployment

**Golang Version Dependency**

```
go >= 1.22.1

```

**API Mode**

Starting API mode will listen on port 31000 and start the API service. Data can be read by calling the API service.

```ENScan_GO is a high-performance corporate reconnaissance tool written in Go. It automatically maps a target company's business structure—finding subsidiaries, investments, and hidden domains—to exponentially expand your bug bounty scope.
./enscan --api

```

## Communication & Feedback

Follow the official account `WgpSec狼组安全团队` (WgpSec Wolf Group Security Team), reply `加群` (Join Group), add the BOT, and send `enscan` to discuss together~

## 404 StarLink Plan

<img src="[https://github.com/knownsec/404StarLink/raw/master/Images/logo.png](https://github.com/knownsec/404StarLink/raw/master/Images/logo.png)" width="30%">

ENScanGo has joined the [404 StarLink Plan](https://github.com/knownsec/404StarLink).

## JetBrains OS licenses

`ENScanGo` had been being developed with `GoLand` IDE under the **free JetBrains Open Source license(s)** granted by
JetBrains s.r.o., hence I would like to express my thanks here.

<a href="[https://www.jetbrains.com/?from=wgpsec](https://www.jetbrains.com/?from=wgpsec)" target="_blank"><img src="[https://raw.githubusercontent.com/wgpsec/.github/master/jetbrains/jetbrains-variant-4.png](https://raw.githubusercontent.com/wgpsec/.github/master/jetbrains/jetbrains-variant-4.png)" width="256" align="middle"/></a>
