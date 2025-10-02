# n8n-heroku

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://dashboard.heroku.com/new?template=https://github.com/MadScientist85/n8n-heroku/tree/main)

## n8n - Free and open fair-code licensed node based Workflow Automation Tool.

This is a [Heroku](https://heroku.com/)-focused container implementation of [n8n](https://n8n.io/).

## Deployment Options

### Option 1: Deploy with Button (Recommended)

Use the **Deploy to Heroku** button above to launch n8n on Heroku. When deploying, make sure to check all configuration options and adjust them to your needs. It's especially important to set `N8N_ENCRYPTION_KEY` to a random secure value. 

### Option 2: Deploy with Heroku CLI

If you prefer using the Heroku CLI:

1. Clone this repository:
   ```bash
   git clone https://github.com/MadScientist85/n8n-heroku.git
   cd n8n-heroku
   ```

2. Create a new Heroku app:
   ```bash
   heroku create your-app-name
   ```

3. Set the stack to container:
   ```bash
   heroku stack:set container
   ```

4. Add PostgreSQL addon:
   ```bash
   heroku addons:create heroku-postgresql:mini
   ```

5. Set required environment variables:
   ```bash
   heroku config:set N8N_ENCRYPTION_KEY=your-secure-random-key
   heroku config:set WEBHOOK_URL=https://your-app-name.herokuapp.com
   heroku config:set GENERIC_TIMEZONE=Europe/Berlin
   heroku config:set DB_POSTGRESDB_SSL_REJECT_UNAUTHORIZED=false
   ```

6. Deploy to Heroku:
   ```bash
   git push heroku main
   ```

## Configuration

When deploying, you'll need to configure the following environment variables:

- **N8N_ENCRYPTION_KEY**: Set this to a random secure value. This is crucial for securing your data.
- **WEBHOOK_URL**: Replace `<appname>` with your Heroku application name (e.g., `https://your-app-name.herokuapp.com`)
- **GENERIC_TIMEZONE**: Set your timezone (default: Europe/Berlin)
- **DB_POSTGRESDB_SSL_REJECT_UNAUTHORIZED**: Should be set to `false` for Heroku PostgreSQL

## Additional Resources

Refer to the [Heroku n8n tutorial](https://docs.n8n.io/hosting/server-setups/heroku/) for more information.

If you have questions after trying the tutorials, check out the [forums](https://community.n8n.io/).
