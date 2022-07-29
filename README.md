# <span style="color:teal">shuttle</span>

## Description:
Retrieve hyperlinks via cli.

I got the inspiration from [tldr](https://github.com/tldr-pages/tldr) and [cht.sh](https://github.com/chubin/cheat.sh) but I needed a private internal utility for confidential resources.

---
## Requirements:

* Currently only supported in `bash v3+` but with future plans for `python3` and `go`.

* [jq](https://stedolan.github.io/jq/) - tested on v1.5

---

## Usage:

Links are stored in valid json files named according to the resource being searched.  For example, the file `foo.json` would be the argument when executing `./shuttle foo`.

Tree structure is:
```bash
.
├── shuttle
└── shuttle-files
    ├── foo.json
    └── bar.json
```
Syntax is very simple:
```bash
./shuttle $arg
```
Example use case:
```bash
#If $arg is not passed

./shuttle
Missing argument.  These lookups are available:

app1
app2
```
```bash
./shuttle app1
{
  "name": "app1",
  "links": [
    {
      "name": "Official Docs",
      "value": "https://app1/docs"
    },
    {
      "name": "Runbook",
      "value": "https://app1/runbook"
    },
    {
      "name": "Dashboard",
      "value": "https://app1/dashboard"
    },
    {
      "name": "Collaboration",
      "value": "https://app1/collab"
    }
  ]
}
```

```bash
./shuttle app2
{
  "name": "app2",
  "wiki": "https://app2/wiki",
  "playbook": "https://app2/playbook",
  "diagram": "https://app2/diagram",
  "communication": "https://app2/comms"
}
```
---