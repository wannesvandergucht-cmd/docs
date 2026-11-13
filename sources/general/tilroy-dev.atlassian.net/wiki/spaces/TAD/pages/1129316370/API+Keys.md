# Source: https://tilroy-dev.atlassian.net/wiki/spaces/TAD/pages/1129316370/API+Keys

Tilroy API documentation

/

API Keys

[Updated Dec 02, 2025](https://tilroy-dev.atlassian.net/wiki/spaces/TAD/history/1129316370)

- Anonymous Hedgehog

More actions

# API Keys

![](https://tilroy-dev.atlassian.net/wiki/aa-avatar/557058:9e831523-ee3d-43f8-863a-c67bcf872b0a)

By Wannes Van der Gucht

1 min

Add a reaction

# Get Access

To gain access to the APIs, Tilroy performs a configuration on your account.

Two keys are provided that are used to establish the connection with your account:

- **x-api-key**: determines the profile defining which APIs and endpoints you have access to.

- **Tilroy-Api-Key**: identifying your account

Do you want to get access to your account through API and get your API keys?

Please contact integrations@tilroy.com

# Customer API and bearer tokens

In addition if you use the Customer API you require an Authorization key.

- **Authorization**: The bearer token of the customer, so that we know whether you are allowed to retrieve or update data of a certain customer

If you are developing an app where the customer needs to update their own data, you can use the Authentication API to get a token for the customer by using the /tokens endpoint.

If you are writing a service for syncing customer data, we will need to provide you a bearer token with access to allow retrieving/updating the data of all customers.

When you get an error **'User xxx has no permission to update customer'** you are probably using a wrong combination of headers. Both the `Tilroy-Api-Key` and the the bearer token should be linked to the same tenant. This can happen when you have multiple tenants for each environment you are integrating with.

# Acceptance or Production?

For integrations, you typically have two accounts. One for acceptance (ACC) and one for production (PROD). You will receive a separate `Tilroy-Api-Key` for each.

An ACC account is essentially a separate account within the Tilroy Cloud platform. It is not a separate technical environment. The functions and capabilities of your ACC and PROD accounts are therefore the same.

Collapse action bar

View all comments

Open Details Panel

Remix page

Open Rovo Chat

Add a comment

Add a reaction