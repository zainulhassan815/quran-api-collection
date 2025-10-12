# Quran API Bruno Collection

Bruno API collection for testing and interacting with Quran content endpoints.

## About

This repository contains a [Bruno](https://www.usebruno.com/) API collection for the Quran Foundation API. Bruno is a fast, open-source API client that stores collections directly in your filesystem using a plain text markup language (Bru).

## Prerequisites

- [Bruno](https://www.usebruno.com/downloads) installed on your machine
- API credentials (client_id and client_secret) from Quran Foundation - [Request Access](https://api-docs.quran.foundation/request-access)

## Getting Started

### 1. Clone the Repository

```bash
git clone <repository-url>
cd quran-api-collection
```

### 2. Open in Bruno

1. Launch Bruno
2. Click on "Open Collection"
3. Select the folder containing this collection

### 3. Configure Environment Variables

The collection includes two environments:

- **DEV** - Pre-live/staging environment
- **PROD** - Production environment

#### Set Secret Variables

For your chosen environment (DEV or PROD), configure the following secret variables:

1. In Bruno, select the environment (DEV or PROD)
2. Add the following secret values:
   - `client_id` - Your OAuth2 client ID
   - `client_secret` - Your OAuth2 client secret

**Note:** The `token` variable will be automatically set after authentication.

#### Environment URLs

**DEV Environment:**
- Auth URL: `https://prelive-oauth2.quran.foundation`
- Base URL: `https://apis-prelive.quran.foundation`

**PROD Environment:**
- Auth URL: `https://oauth2.quran.foundation`
- Base URL: `https://apis.quran.foundation`

## Authentication

### Getting an Access Token

1. Open the **"Get Access Token"** request
2. Ensure you have configured `client_id` and `client_secret` in your environment
3. Send the request
4. The access token will be automatically saved to the `token` environment variable via the post-response script

The token uses OAuth2 client credentials flow with the `content` scope.

## Usage

1. **Authenticate First**: Run the "Get Access Token" request to obtain and store your access token
2. **Select Environment**: Choose either DEV or PROD environment from the environment selector
3. **Make Requests**: Navigate to the desired endpoint and send the request
4. **Customize Parameters**: Modify query parameters as needed for your use case

## Collection Structure

```
.
├── bruno.json                          # Collection configuration
├── collection.bru                      # Collection-level settings
├── environments/
│   ├── DEV.bru                        # Development environment
│   └── PROD.bru                       # Production environment
├── Get Access Token.bru               # OAuth2 authentication
└── Contents API/
    └── Verses/
        ├── Get Random Aayah.bru       # Random verse endpoint
        └── folder.bru                 # Folder configuration
```

## Features

- OAuth2 authentication with automatic token storage
- DEV and PROD environment configurations
- Organized folder structure for API endpoints
- Pre-configured query parameters for easy customization
- Post-response scripts for workflow automation

## Contributing

Feel free to add more endpoints and improve the collection as needed.

## Resources

- [Bruno Documentation](https://docs.usebruno.com/)
- [Quran Foundation API Documentation](https://api-docs.quran.foundation/)

## License

This collection is provided as-is for testing and development purposes.
