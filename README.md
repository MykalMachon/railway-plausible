# Railway: Plausible Analytics Template

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/template/mzYEXO?referralCode=IFlm92)


## What is this template?
Plausible Analytics is a simple, open-source, lightweight (< 1 KB) and privacy-friendly alternative to Google Analytics. Plausible is trusted by 10,000+ paying subscribers to deliver their website and business insights.

This template makes it trivial to deploy an instance of [Plausible Analytics](https://plausible.io/) with all of it's required services on [Railway](https://railway.app).

See [the Plausible Analytics docsite](https://plausible.io/docs) for a more in-depth explanation of its feature set.

## Quick start guide

1. Click the "Deploy on Railway" button above, or [click here](https://railway.app/template/mzYEXO?referralCode=IFlm92)
2. Follow the setup steps in Railway
3. Monitor your services as they come up
    - If the Plausible Analytics service is provisioned before the ClickHouse service, you have to re-set the environment variables that reference the ClickHouse service.
        - Once the ClickHouse service is up, navigate to the Plausible Analytics service, and select the "Variables" tab. 
        - find and click the "edit" button on the `CLICKHOUSE_DATABASE_URL` environment variable in the Plausible Analytics service. 
        - Re-save the variable without changing the contents. 
        - This should trigger a redeploy with the proper environment variables.  
5. Setup your websites with Plausible analytics
    1. Navigate to the domain for your Plausible Analytics service. 
    2. Follow the prompts to create an account on the service 
    3. Follow the prompts to set up tracking on your website. 
    4. For more information on how to use Plausible, [check their site](https://plausible.io/docs).

## Additional Resources 

If you'd like to customize your instance of Plausible Analytics, I would recommend reviewing the documentation for both ClickHouse DB, and Plausible Analytics. Here are some links to get you started: 
- Plausible welcome guide: https://plausible.io/docs/
- Plausible self-hosting docs: https://plausible.io/docs/self-hosting-configuration
- ClickHouse docker docs: https://hub.docker.com/r/clickhouse/clickhouse-server/

## Feedback 
If you experience any issues or have any feedback at all, [you can create a GitHub issue here](https://github.com/MykalMachon/railway-plausible/issues)

### Known Issues
- When the Plausible Analytics service is provisioned before the ClickHouse service, you have to re-set the environment variables that reference the ClickHouse service.
    - Once the ClickHouse service is up, navigate to the Plausible Analytics service, and select the "Variables" tab. 
    - find and click the "edit" button on the `CLICKHOUSE_DATABASE_URL` environment variable in the Plausible Analytics service. 
    - Re-save the variable without changing the contents. 
    - This should trigger a redeploy with the proper environment variables.  