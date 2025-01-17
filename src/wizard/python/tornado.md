---
name: Tornado
doc_link: https://docs.sentry.io/platforms/python/guides/tornado/
support_level: production
type: framework
---

The Tornado integration adds support for the [Tornado Web
Framework](https://www.tornadoweb.org/). A Tornado version of 5 or greater and
Python 3.6 or greater is required.

1. Install `sentry-sdk` from PyPI:

   ```bash
   $ pip install --upgrade sentry-sdk
   ```

2. If you're on Python 3.6, you also need the `aiocontextvars` package:

   ```bash
   $ pip install --upgrade aiocontextvars
   ```

3. Initialize the SDK before starting the server:

   ```python
   import sentry_sdk
   from sentry_sdk.integrations.tornado import TornadoIntegration

   sentry_sdk.init(
      dsn="___PUBLIC_DSN___",
      integrations=[
         TornadoIntegration(),
      ],

      # Set traces_sample_rate to 1.0 to capture 100%
      # of transactions for performance monitoring.
      # We recommend adjusting this value in production,
      traces_sample_rate=1.0,
   )

   # Your app code here, without changes

   class MyHandler(...):
       ...
   ```
