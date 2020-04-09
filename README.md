## 👷 `Worker-Template-That-Works` 

This is a CloudFlare Worker template to kickstart a project that aims to use external Node modules. Its just like the one the CloudFlare documentation provides... except it works :)

# Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

## Prerequisites

* An installation of [npm](https://www.npmjs.com/get-npm) (commonly recommended now to use [nvm](https://github.com/nvm-sh/nvm))

* A CloudFlare account [register here](https://dash.cloudflare.com/sign-up)

* CloudFlare’s open-source command-line tool [Wrangler](https://github.com/cloudflare/wrangler#installation)

```
npm i @cloudflare/wrangler -g
```

  [A quick guide on installing if you have more questions](https://developers.cloudflare.com/workers/quickstart/#installing-the-cli)

* A local [clone](https://github.com/triggermesh/Worker-Template-That-Works.git) of Worker-Template-That-Works

```
git clone https://github.com/triggermesh/Worker-Template-That-Works.git
cd Worker-Template-That-Works
```

If you have done this before just update the wrangler.toml file with your acount ID, run "  wrangler build  ", and you are finished! 

## Configure the project 

1. Install the application dependencies by executing the following command in the [root](https://github.com/triggermesh/Worker-Template-That-Works) directory of the flaretokinesis repository. 

```bash
npm install 
```

2. (Conditional) Create your CloudFlare Worker

* Navigate to the CloudFlare Console and select "Workers" from the right side pannel under "Analytics"

* If you have previously created worker(s) they will be displayed here and you can skip to the "Retrieving Authentication Information" section below.

* Select "Create a Worker"


3. "Retrieving Authentication Information"

* To create your API Token and Retrieve your Account ID follow the CloudFlare [instructions here](https://developers.cloudflare.com/workers/quickstart/#api-token).


4. Configure Wrangler. Set up your CloudFlare API Token on your local machine via the `wrangler config` subcommand or write directly to `$HOME/.wrangler/config/default.toml`

```bash
wrangler config
Enter API token:
```

You will need to add the following to the Wrangler.toml file found in the root directory of the project. 

```
API_key : <"your api key">
account_id  : <" your account ID">
```

Now install the NPM package you want to use and you can use it like normal.

All done! You can now deploy this service to the edge with functioning node modles! 

## Usage

To run a test deployment of the Cloudflare worker execute the following command from a Terminal/Command Prompt in the [root](https://github.com/triggermesh/Worker-Template-That-Works/) 
directory of flaretokinesis. 

```bash
wrangler preview
```

The preview command will take your built Worker project and upload it to a unique URL at cloudflareworkers.com.

## Deploy

To deploy a your own version of the code execute the following command:

```bash
wrangler publish 
```

If you run into any issues please look back on the sections that go over retreiving and setting your User ID and Authentication Information/Tokens from CloudFlare.

## Support

We would love your feedback and help on this project, so don't hesitate to let us know what is wrong and how we could improve them, just file an [issue](https://github.com/triggermesh/Worker-Template-That-Works.git/issues/new) or join those of use who are maintaining them and submit a [PR](https://github.com/triggermesh/Worker-Template-That-Works/compare).

## Code of conduct

This project is by no means part of [CNCF](https://www.cncf.io/) but we abide by its [code of conduct](https://github.com/cncf/foundation/blob/master/code-of-conduct.md).

