# Low Code Automation

This repository provides a Docker Compose file that runs open-source automation tools like n8n, enabling users to experiment with low-code automation platforms for rapid prototyping and POC implementation.

## Rationale

Low-code automation platforms enable developers and business users to quickly build and deploy workflow automations without writing extensive code. By reducing the technical barriers to entry, these tools democratize automation capabilities and allow businesses to focus on solving business problems rather than getting caught up in implementation details. This repository provides a practical starting point for exploring these capabilities in a controlled, local environment.

## Setup Instructions

1. Clone this repository.
2. Copy `.env.example` to `.env`, review the file, and fill in the relevant details.
3. Run `docker compose up --detach` to start all containers.

## Enabling Databases (MySQL or PostgreSQL)

The Docker Compose configuration includes optional MySQL and PostgreSQL databases that can be enabled and used with n8n. To work with either database, add `--profile db-mysql` or `--profile db-postgres` after any `docker compose` command.

For example, to enable MySQL, run:

`docker compose --profile db-mysql up --detach`

Similarly, to enable PostgreSQL, run:

`docker compose --profile db-postgres up --detach`

## Using with ngrok

You can use ngrok to create secure tunnels for testing webhook integrations or exposing local services to external systems. The ngrok-generated URL can then serve as the webhook URL in your workflow configurations. You can claim one free reserved domain after creating an account. This allows you to have a consistent URL for your webhooks instead of getting a new random URL each time you restart ngrok.

### Setting Up a Reserved Domain

1. Sign up for a free ngrok account at <https://ngrok.com/>
2. Install and authenticate ngrok with your auth token
3. Reserve a domain through your ngrok dashboard's Domains section
4. Use your domain by running: `ngrok http --domain=your-domain.[ngrok](ngrok-free.app)-free.app 5678`

Note that while the free tier includes one reserved domain, additional domains and features are available with paid plans.

When finished, update your `.env` file with the new domain. Note that ngrok domains support HTTPS connections.

## Contributing

We welcome issues, enhancement requests, and pull requests.

## Disclaimer

This setup is intended for educational purposes only.

## License

This project is licensed under the Unlicense - a license with no conditions whatsoever which dedicates works to the public domain. For more information, see <http://unlicense.org/>
