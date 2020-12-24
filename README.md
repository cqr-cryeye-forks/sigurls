# sigurls

![made with go](https://img.shields.io/badge/made%20with-Go-0040ff.svg) ![maintenance](https://img.shields.io/badge/maintained%3F-yes-0040ff.svg) [![open issues](https://img.shields.io/github/issues-raw/drsigned/sigurls.svg?style=flat&color=0040ff)](https://github.com/drsigned/sigurls/issues?q=is:issue+is:open) [![closed issues](https://img.shields.io/github/issues-closed-raw/drsigned/sigurls.svg?style=flat&color=0040ff)](https://github.com/drsigned/sigurls/issues?q=is:issue+is:closed) [![license](https://img.shields.io/badge/license-MIT-gray.svg?colorB=0040FF)](https://github.com/drsigned/sigurls/blob/master/LICENSE) [![twitter](https://img.shields.io/badge/twitter-@drsigned-0040ff.svg)](https://twitter.com/drsigned)

sigurls is a reconnaissance tool, it fetches URLs from **AlienVault's OTX**, **Common Crawl**, **URLScan**, **Github** and the **Wayback Machine** for a given domain.

## Resources

* [Installation](#installation)
    * [From Binary](#from-binary)
    * [From source](#from-source)
    * [From github](#from-github)
* [Post Installtion](#post-installation)
    * [Config File](#config-file)
* [Usage](#usage)
* [Contribution](#contribution)

## Installation

#### From Binary

You can download the pre-built binary for your platform from this repository's [releases](https://github.com/drsigned/sigurls/releases/) page, extract, then move it to your `$PATH`and you're ready to go.

#### From Source

sigurls requires **go1.14+** to install successfully. Run the following command to get the repo

```bash
$ GO111MODULE=on go get -u -v github.com/drsigned/sigurls/cmd/sigurls
```

#### From Github

```bash
$ git clone https://github.com/drsigned/sigurls.git; cd sigurls/cmd/sigurls/; go build; mv sigurls /usr/local/bin/; sigurls -h
```

## Post Installation

#### Config File

sigurls' configuration file is located at `$HOME/.config/sigurls/conf.yaml` - created during the first run - and has the contents:

```yaml
version: 1.2.0
sources:
    - commoncrawl
    - github
    - otx
    - urlscan
    - wayback
```

## Usage

To display help message for sigurls use the `-h` flag:

```
$ sigurls -h

     _                  _
 ___(_) __ _ _   _ _ __| |___
/ __| |/ _` | | | | '__| / __|
\__ \ | (_| | |_| | |  | \__ \
|___/_|\__, |\__,_|_|  |_|___/ v1.2.0
       |___/

USAGE:
  sigurls [OPTIONS]

OPTIONS:
  -d             domain to fetch urls for
  -exclude       comma separated list of sources to exclude
  -ls            list all the sources available
  -nc            no color mode
  -silent        silent mode: output urls only
  -subs          include subdomains' urls
  -use           comma separated list of sources to use
```

## Contribution

[Issues](https://github.com/drsigned/sigurls/issues) and [Pull Requests](https://github.com/drsigned/sigurls/pulls) are welcome!
