# .NET Core Website

This .NET Core website only supports authentication against a tenant in a Microsoft Entra ID service in Azure. This code works perfectly with the free tier of Entra ID but does not support authorization against an API endpoint. 

## Setup

### Step 1: Register Your Application in Entra ID
1. Go to the Microsoft Entra admin center.
1. Under App registrations, register a new application for the website.
1. Set the Redirect URI to https://localhost:5001/signin-oidc (or adjust the port to match your project).
1. Under Authentication, enable ID tokens since this application is a web app using OpenID Connect.
1. Configure API permissions to include permissions like openid and profile and any other required for your app. Grant admin consent to these permissions to ensure all users in the organization can sign in.

### Step 2: Configure API Permissions and Admin Consent
1. In the app registration settings, go to API Permissions.
1. Add Microsoft Graph API permissions (e.g., openid, profile, and User.Read) to enable basic user information access.
1. Click Grant admin consent to allow the application access to these permissions for all users.

### Step 3: Configure msalConfig
1. Open authConfig.js
1. Replace <CLIENT_ID> with the Client ID from the app in Step 1.
1. Replace <TENANT_ID> with the Tenant ID from Entra ID tenant.
1. Replace <PRIMARY_DOMAIN> with the Primary Domain from Entra ID tenant.
1. Replace <CLIENT_SECRET> with the Client Secret for the app.

## Tutorials
* https://learn.microsoft.com/en-us/aspnet/core/security/authentication/azure-active-directory/?view=aspnetcore-8.0

## Versions
* .NET: 8.0.10
