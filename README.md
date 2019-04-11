# CarthageBinaries

This repository contains carthage [binary project specifications](https://github.com/Carthage/Carthage/blob/master/Documentation/Artifacts.md#binary-project-specification) and compiled binary frameworks.

## Repository structure

Repository has the following structure:

```
.
├── Alamofire
│   ├── 4.8.1
│   │   └── Alamofire.framework.zip
│   └── Alamofire.json
├── Kingfisher
│   ├── 4.10.1
│   │   └── Kingfisher.framework.zip
│   ├── 5.3.0
│   │   └── Kingfisher.framework.zip
│   └── Kingfisher.json
└── LeadKit
    ├── 0.9.12
    │   └── LeadKit.framework.zip
    ├── 0.9.13
    │   └── LeadKit.framework.zip
    ├── 0.9.14
    │   └── LeadKit.framework.zip
    └── LeadKit.json
```

Where contents of json files looks like this:

```json
{
    "0.9.12": "https://github.com/TouchInstinct/CarthageBinaries/raw/master/LeadKit/0.9.12/LeadKit.framework.zip",
    "0.9.13": "https://github.com/TouchInstinct/CarthageBinaries/raw/master/LeadKit/0.9.13/LeadKit.framework.zip",
    "0.9.14": "https://github.com/TouchInstinct/CarthageBinaries/raw/master/LeadKit/0.9.14/LeadKit.framework.zip"
}
```

## Adding new binaries

* Add framework to [Cartfile](Cartfile)
* Run `carthage update` (add `--platform iOS` only if build failed for non-iOS platforms)
* Create folder for new version: `mkdir -p FrameworkName/X` where `X` - framework version (0.9.14 for example)
* Run `carthage archive FrameworkName --output FrameworkName/X`
* Create `FrameworkName.json` if there is not yet
* Create new branch, push your changes and create pull request
* You're done!
