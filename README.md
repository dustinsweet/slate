TSheets-APIDocs
=============
<p align="center">
    <img src="./source/images/logo.svg" width="150" alt="Logo"/>
</p>
REST API Documentation for TSheets by QuickBooks

**Support:** [Request Help](mailto:help@tsheets.com?subject=API Docs GitHub Help&cc=SBSEGTimeTrackingSegment-Partnerships@intuit.com)<br/>
**License:** [![Apache 2](http://img.shields.io/badge/license-Apache%202-brightgreen.svg)](http://www.apache.org/licenses/LICENSE-2.0) <br/>

This Git Repository is the official reference to the REST API Documentation of TSheets (the Time Capture Segment of Intuit).
Some of the features include:

* TSheets free trial information
* Quick start walkthroughs for developing to the API
* Comprehensive API references
* Code samples in multiple languages
* Best practices, tips & suggestions
* Detailed OAuth2 information
* Access to Postman Collection
* Information about our Partnership Progam

## Contribute:
We greatly encourage contributions! You can report and fix existing documentation bugs. Feel free to open issues and/or send pull requests.

The `master` branch of this repository contains the latest stable release of the API documentation.  Pull requests should be submitted against `master` by forking this repo into your account, developing and testing your changes, and creating pull requests to request merges. See the [Contributing to a Project](https://guides.github.com/activities/contributing-to-open-source/)
article for more details about how to contribute.

### Steps to Contribute:

1. Fork this repository into your account on Github
2. Clone *your forked repository* (not our original one) to your hard drive with `git clone https://github.com/YOURUSERNAME/TSheets-APIDocs.git`
3. Develop and validate your changes (see below)
5. Create a pull request for review to request merge
6. Obtain approval before your changes can be merged

### Steps to Build and Validate Changes
1. Install and launch Docker for [Mac](https://hub.docker.com/editions/community/docker-ce-desktop-mac) or [Windows](https://hub.docker.com/editions/community/docker-ce-desktop-windows).
2. Clone your forked repository (as above)
3. Make your changes
4. Build your changes: `./build.sh` (Mac) or `winbuild.cmd` (Windows)
5. Validate changes by viewing `./build/index.html` in a browser

Thank you for your contribution!
