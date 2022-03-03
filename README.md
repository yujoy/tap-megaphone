# Singer Tap for Megaphone

[![test](https://github.com/yujoy/tap-megaphone/actions/workflows/ci_workflow.yml/badge.svg)](https://github.com/yujoy/tap-megaphone/actions/workflows/ci_workflow.yml)
[![Code style: black](https://img.shields.io/badge/code%20style-black-000000.svg)](https://github.com/psf/black)
[![PyPI Version](https://img.shields.io/pypi/v/tap-megaphone?style=flat)](https://pypi.org/project/tap-megaphone/)
[![License](https://img.shields.io/pypi/l/tap-megaphone)](LICENSE.md)
[![Python](https://img.shields.io/pypi/pyversions/tap-megaphone)](https://pypi.org/project/tap-megaphone/)

`tap-megaphone` is a Singer tap for the [Megaphone API](https://developers.megaphone.fm/) built 
with the [Meltano Tap SDK](https://sdk.meltano.com) for Singer Taps.

Built with the Meltano [SDK](https://gitlab.com/meltano/sdk) for Singer Taps.

## Installation

- [ ] `Developer TODO:` Update the below as needed to correctly describe the install procedure. For instance, if you do not have a PyPi repo, or if you want users to directly install from your git repo, you can modify this step as appropriate.

```bash
pipx install tap-megaphone
```

## Supported Streams

The Megaphone tap replicates the following data:
* [Podcasts](https://jsapi.apiary.io/apis/megaphoneapi/reference/podcasts.html)
* [Episodes](https://jsapi.apiary.io/apis/megaphoneapi/reference/episodes.html)
* [Networks](https://jsapi.apiary.io/apis/megaphoneapi/reference/networks.html)
* [Campaigns](https://jsapi.apiary.io/apis/megaphoneapi/reference/campaigns.html)
* [Campaign Orders](https://jsapi.apiary.io/apis/megaphoneapi/reference/campaign-orders.html)
* [Promo Orders](https://jsapi.apiary.io/apis/megaphoneapi/reference/promo-orders.html)
* [Campaign Order Advertisements](https://jsapi.apiary.io/apis/megaphoneapi/reference/advertisements/campaign-order-advertisements-collection.html)
* [Promo Order Advertisements](https://jsapi.apiary.io/apis/megaphoneapi/reference/advertisements/promo-order-advertisements-collection/list-all-promo-order-advertisements.html)
* [Agencies](https://jsapi.apiary.io/apis/megaphoneapi/reference/agencies.html)
* [Advertisers](https://jsapi.apiary.io/apis/megaphoneapi/reference/advertisers.html)
* [Devices](https://jsapi.apiary.io/apis/megaphoneapi/reference/targeting/devices.html)
* [Nielsen Segments](https://jsapi.apiary.io/apis/megaphoneapi/reference/targeting/nielsen-segments.html)
* [Countries](https://jsapi.apiary.io/apis/megaphoneapi/reference/targeting/geotargeting-countries.html)
* [Regions](https://jsapi.apiary.io/apis/megaphoneapi/reference/targeting/geotargeting-regions.html)
* [DMAs](https://jsapi.apiary.io/apis/megaphoneapi/reference/targeting/geotargeting-dmas.html)
* [Advertiser Categories](https://jsapi.apiary.io/apis/megaphoneapi/reference/advertiser-categories.html)
* [IAB Advertiser Categories](https://jsapi.apiary.io/apis/megaphoneapi/reference/iab-advertiser-categories.html)
* [Organization Tags](https://jsapi.apiary.io/apis/megaphoneapi/reference/organization-tags.html)


## Configuration

**The tap accepts the following config options:**

- **`auth_token: str` (required)**: Megaphone API Authorization token generated from the Megaphone platform. Instructions on how to generate tokens [here](https://jsapi.apiary.io/apis/megaphoneapi/introduction/authorization.html).
- **`organization_id: str` (required)**: ID of the Organization in the form of a UUID. This can be grabbed by first [logging in to the Megaphone portal](https://cms.megaphone.fm/users/sign_in) and then copying the organization_id from the URL (ie. - https://cms.megaphone.fm/organizations/{organization_id}/dashboard).

A full list of supported settings and capabilities for this
tap is available by running:

```bash
tap-megaphone --about
```

## Usage

You can easily run `tap-megaphone` by itself or in a pipeline using [Meltano](www.meltano.com).

### Executing the Tap Directly

```bash
tap-megaphone --version
tap-megaphone --help
tap-megaphone --config CONFIG --discover > ./catalog.json
```

## Developer Resources

- [ ] `Developer TODO:` As a first step, scan the entire project for the text "`TODO:`" and complete any recommended steps, deleting the "TODO" references once completed.

### Initialize your Development Environment

```bash
pipx install poetry
poetry install
```

### Create and Run Tests

Create tests within the `tap_megaphone/tests` subfolder and
  then run:

```bash
poetry run pytest
```

You can also test the `tap-megaphone` CLI interface directly using `poetry run`:

```bash
poetry run tap-megaphone --help
```

### Testing with [Meltano](https://www.meltano.com)

_**Note:** This tap will work in any Singer environment and does not require Meltano.
Examples here are for convenience and to streamline end-to-end orchestration scenarios._

Your project comes with a custom `meltano.yml` project file already created. Open the `meltano.yml` and follow any _"TODO"_ items listed in
the file.

Next, install Meltano (if you haven't already) and any needed plugins:

```bash
# Install meltano
pipx install meltano
# Initialize meltano within this directory
cd tap-megaphone
meltano install
```

Now you can test and orchestrate using Meltano:

```bash
# Test invocation:
meltano invoke tap-megaphone --version
# OR run a test `elt` pipeline:
meltano elt tap-megaphone target-jsonl
```

### SDK Dev Guide

See the [dev guide](https://sdk.meltano.com/en/latest/dev_guide.html) for more instructions on how to use the SDK to 
develop your own taps and targets.
