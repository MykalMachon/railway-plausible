# Railway: Plausible Analytics Template

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/mzYEXO?referralCode=IFlm92)


## What is this template?
This template makes it trivial to deploy an instance of [Plausible Analytics](https://plausible.io/) with all of it's required services on  [Railway](https://railway.app).

Plausible analytics is a simple, open source, lightweight (< 1 KB) and privacy-friendly alternative to Google Analytics. Plausible is trusted by 10,000+ paying subscribers to deliver their website and business insights.

See [the Plauisble Analytics docsite](https://plausible.io/docs) for a more in-depth explanation of its featureset.

## Quick start guide

1. Click the "Deploy on Railway" button above, or [click here](https://railway.app/template/mzYEXO?referralCode=IFlm92)
2. Do initial setup for the Clickhouse DB service.
3. Do initial setup for the Plausible Analytics service.
    1. There are two important environment variables to note here: 
        1. `BASE_URL`: this should be your Railway generated domain for your Plausible Analytics service. 
        2. `CLICKHOUSE_DATABASE_URL`: you can leave most of this untouched, bt you'll have to change the `<<YOUR_DOMAIN>>` string to match the Railway generated domain for your Clickhouse Database service.
4. Setup custom domains for your services (optional) 
    1. See [Railway's docs for setting up custom domains here](https://docs.railway.app/deploy/exposing-your-app#custom-domains). 
    2. Set a custom domain for your Clickhouse DB service.
        1. Update the `CLICKHOUSE_DATABASE_URL` environment variable on the Plausible Analytics service to reference your new Clickhouse DB domain.
    3. Set a custom domain for your Plausible Analytics service. 
        1. Update the `BASE_URL` environment variables on the Plausible Analytics service to reference your new Plausible Analytics domain.  
5. Setup your website with Plausible analytics
    1. Navigate to the domain for your Plausible Analytics service. 
    2. Follow the prompts to create an account on the service 
    3. Follow the prompts to setup tracking on your website. 
    4. For more information on how to use Plausible, [check their site](https://plausible.io/docs).

## Additional Resources 

If you'd like to customize your instance of Plausible Analytics, I would recommend reviewing the documentation for both ClickHouse DB, and Plausible Analytics. Here are some links to get you started: 
- Plausible Self-Hosting Docs: https://plausible.io/docs/self-hosting-configuration
- Clickhouse Docker Docs: https://hub.docker.com/r/clickhouse/clickhouse-server/

## Feedback 
If you experience any issues or have any feedback at all, [you can create a GitHub issue here](https://github.com/MykalMachon/railway-plausible/issues)

### Known Issues
1. *Cannot use private networking for Clickhouse DB*: unfortunately, Plausible Analytics does not seem to support IPV6 routing for the ClickHouse Database. This means we cannot use Railway's private networking features, and have to expose our Clickhouse Database to the public internet for it to be usable.
