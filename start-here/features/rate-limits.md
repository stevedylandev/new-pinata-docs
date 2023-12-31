---
description: Pinata API usage limits
---

# 🛑 Limits

### Rate Limits

The maximum number of API requests that can be made within a certain period of time.

{% tabs %}
{% tab title="Pinata API" %}
The current rate limit of the Pinata API is **180 requests per minute** (per IP).

**Exceptions:**

The following API calls have increased rate limits:

* Endpoints under the `/data/` route have a rate limit of 30 requests per minute
* The [Pinning Services API endpoint for listing content](https://ipfs.github.io/pinning-services-api-spec/#tag/pins/paths/\~1pins/get) has a rate limit of 30 requests per minute

#### Recommendations

For users with traffic that can be burst-heavy, we recommend using a task scheduler or queue-based upload approach that limits requests to the allowed amount.&#x20;

For NodeJS users specifically, we recommend the [bottleneck library](https://www.npmjs.com/package/bottleneck) to help with this.
{% endtab %}

{% tab title="Public Pinata Gateway" %}
The Pinata public IPFS gateway (gateway.pinata.cloud) is meant for testing purposes or very low volume retrieval and should not be used in production scenarios. It currently has the following rate limits:

* Each CID has a global rate limit of 15 requests per minute (this is across all IP addresses)
* Each IP address has a rate limit of 200 requests per minute
{% endtab %}

{% tab title="Dedicated Gateways" %}
At this time there are currently no rate limits for users retrieving content from a dedicated gateway.&#x20;
{% endtab %}
{% endtabs %}

### Upload Size Limits

There is no aggregate limit for uploads, but each individual upload (whether it is a file or a folder) is limited to **25 GB**.

There is also a file limit size of **10MB** for the pinJSONToIPFS API endpoint.
