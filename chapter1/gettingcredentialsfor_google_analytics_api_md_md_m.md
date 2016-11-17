# Getting credentials for Google Analytics API

> **Note**: you can use default credentials included in googleAnalyticsR package. But this API quota is shared for all googleAnalyticsR users. To guarantee that API quota is only for you - please create your own credentials. I've described this process below.



Navigate to [Google Developers Console](https://console.developers.google.com) and create **new project**.

Enable Google Analytics API:

![Enable and Manage APIs](developers_console_api.png)

Search: _Analytics_

![Searching API](developers_console_search_api.png)

Select _Enable_

![Enable API](developers_console_enable_api.png)

Create credentials:

![Create credentials](developers_concole_cerate_credentials.png)

![Step 1](developers_console_step1.png)

![Step 1a](developers_console_step1a.png.png)

![Step 2](developers_console_step2.png)

![Step 3](developers_console_step3.png)

![Step 4](developers_console_step4.png)

Get credentials:

![Get credentials](developers_console_get_credentials.png)

Save **Client ID** and **Client Secret**. You will need this to configure the library that downloads data from Google Analytics into R.

