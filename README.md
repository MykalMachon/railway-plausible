# Railway: Plausible Analytics Template

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/mzYEXO?referralCode=IFlm92)


## What is this template?
Plausible analytics is a simple, open source, lightweight (< 1 KB) and privacy-friendly alternative to Google Analytics. Plausible is trusted by 10,000+ paying subscribers to deliver their website and business insights.

This template makes it trivial to deploy an instance of [Plausible Analytics](https://plausible.io/) with all of it's required services on [Railway](https://railway.app).

See [the Plauisble Analytics docsite](https://plausible.io/docs) for a more in-depth explanation of its featureset.

## Quick start guide

1. Click the "Deploy on Railway" button above, or [click here](https://railway.app/template/mzYEXO?referralCode=IFlm92)
2. Follow the setup steps in Railway
3. Monitor your services as they come up
    4. If the Plausible Analytics service comes up before Clickhouse DB, you'll need to copy this into the environment variable labelled `CLICKHOUSE_DATABASE_URL` in the Plausible Analytics service: `https://${{"Clickhouse DB".CLICKHOUSE_USER}}:${{"Clickhouse DB".CLICKHOUSE_PASSWORD}}@${{RAILWAY_SERVICE_CLICKHOUSE_DB_URL}}/${{"Clickhouse DB".CLICKHOUSE_DB}}`
5. Setup your websites with Plausible analytics
    1. Navigate to the domain for your Plausible Analytics service. 
    2. Follow the prompts to create an account on the service 
    3. Follow the prompts to setup tracking on your website. 
    4. For more information on how to use Plausible, [check their site](https://plausible.io/docs).

## Additional Resources 

If you'd like to customize your instance of Plausible Analytics, I would recommend reviewing the documentation for both ClickHouse DB, and Plausible Analytics. Here are some links to get you started: 
- Plausible welcome guide: https://plausible.io/docs/
- Plausible self-hosting docs: https://plausible.io/docs/self-hosting-configuration
- Clickhouse docker docs: https://hub.docker.com/r/clickhouse/clickhouse-server/

## Feedback 
If you experience any issues or have any feedback at all, [you can create a GitHub issue here](https://github.com/MykalMachon/railway-plausible/issues)

### Known Issues
1. *Cannot use private networking for Clickhouse DB*: unfortunately, Plausible Analytics does not seem to support IPV6 routing for the ClickHouse Database. This means we cannot use Railway's private networking features, and have to expose our Clickhouse Database to the public internet for it to be usable.
2. It seems like when the Plausible Analytics service is provisioned before the Clickhouse DB service, you have to re-set the environment variables that reference the Clickhoues DB Service in the Plausible Analytics service. This can be done by pasting the following value into the environment variable labeled `CLICKHOUSE_DATABASE_URL` in the Plausible Analytics service: `https://${{"Clickhouse DB".CLICKHOUSE_USER}}:${{"Clickhouse DB".CLICKHOUSE_PASSWORD}}@${{RAILWAY_SERVICE_CLICKHOUSE_DB_URL}}/${{"Clickhouse DB".CLICKHOUSE_DB}}`
