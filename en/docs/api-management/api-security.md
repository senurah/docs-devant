# API Security

This document outlines key practices for securing APIs against threats and vulnerabilities. API security relies on authentication, which involves verifying identity with methods like API keys, tokens, or OAuth2, and authorization, which defines user permissions and enforces role-based access.

## Supported security schemes in Devant

Devant primarily supports two security schemes for APIs: `API Key` and `OAuth2`.

### API Key 

API Key is a simple and widely used method for securing APIs. It involves generating a unique key that clients must include in their requests to access the API. The key is typically sent in the request header. You can customize the security header name based on your requirements.

### OAuth2

OAuth2 is a robust and flexible authorization framework that allows third-party applications to access resources on behalf of a user. It involves obtaining an access token through various grant types, such as authorization code, client credentials, or implicit flow. OAuth2 provides better security and scalability for APIs, especially in scenarios involving multiple clients and users.

## Configuring security for Integration as APIs in Devant

Follow the steps given below.

1. Sign in to [Devant](https://console.devant.dev).
2. Select your project and navigate to the **Overview** page in the left navigation.
3. Select the Integration as API you want to configure security for.
4. In the Integration **Overview** page, on the right side, click **Configure Security**.
5. In the **Configure Security** pane, select the **Security Scheme** you want to use (API Key or OAuth2).

    - With **API Key** scheme, you can select Resource Level security for the API. By default, security is applied at the API level.
    - With **OAuth2** scheme, in addition to Resource Level security configurations, you can also configure permissions for the API. You can select from the available scopes or create new ones, and then assign them to each resource.

    !!! note
        If you select both **API Key** and **OAuth2**, authentication requirements depend on the resource:
        
        - For unscoped resources, clients can use either an API Key or OAuth2 access token to authenticate.
        - For resources with OAuth2 scopes assigned (permissions), only OAuth2 authentication is permitted.

6. Click **Apply** to save the changes. The changes will be deployed to the Development environment immediately. For other environments, you need to promote the changes.

    <div style="width: 80%;">
    ![API Security](../../assets/img/api-management/api-security.gif)
    </div>

To consume the secured API, please refer to the relevant documentation for the chosen security scheme:

- [Consuming an API secured with API Key](../consuming-apis/consuming-an-api-secured-with-an-api-key/)
- [Consuming an API secured with OAuth2](../consuming-apis/consuming-an-api-secured-with-oauth2/)
