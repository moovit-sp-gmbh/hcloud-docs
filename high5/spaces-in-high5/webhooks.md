# Webhooks

The webhooks section allows you to create, configure, edit, secure and delete webhooks as triggers for events.

Webhooks are a non-standardized and very convenient way to trigger events in helmut.cloud. Technically, a webhook in helmut.cloud can be invoked with a standard HTTP POST request to its URL. To ensure the call to the webhook is authorized, configure the HMAC signing and validation with a pre-shared key. Additionally or alternatively, multiple HTTP-headers can be set, e.g. to define the payload. A payload limited to 4 MB can be attached to the call.



## Event webhooks

With an event webhook, a single event out of many in a space can be triggered.

* Click "_+ Create webhook_"
* Choose "_Event webhook_"
* Click "Go"
* Choose a name
* Connect an event from the drop-down list
* Define a target account to execute the events stream

Below advanced options, you will find

* Headers to e.g. define content-type, requests or responses
* HMAC authorization headers
* An encryption algorithm to use with HMAC
* And the preshared key to use with HMAC



## Space webhooks

A space webhook offers the option to call an event inside a space defined by the payload of the call.

* Click "_+ Create webhook_"
* Choose "_Space webhook_"
* Click "Go"
* Choose a name
* Define the path to the exact event-name string in the calls payload (e.g. "status.event.name" for a JSON payload)
* Define a target account to execute the events stream

Below advanced options, you will find

* Headers to e.g. define content-type, requests or responses
* HMAC authorization headers
* An encryption algorithm to use with HMAC
* And the preshared key to use with HMAC



## Webhook payload types and sizes

The calls payload can be very versatile, as helmut.cloud accepts many payload types. Yet we encourage our users to use JSON payloads that include the name of the source event.

All payloads are capped at `4 MB`. As a consequence, helmut.cloud will discard all payloads larger than this.



## Securing your webhook with HMAC signatures and validation

To secure communication between third-party applications and helmut.cloud against man-in-the-middle and replay attacks, it is recommended that the third-party posting to the webhook signs all payloads with an HMAC pre-shared key. helmut.cloud can provide a unique key during webhook creation or it can be included by the third-party in the response body.

During webhook creation, see the advanced options to configure HMAC authorization. You can set a header name, decide between SHA1 and SHA256 encryption and generate a PSK for your third-party application. This pre-shared key must remain secret at all times to ensure its function.

When HMAC validation is enabled, unsigned calls or calls with a wrong signature with be discarded.



## Securing your webhook with custom headers

In case the posting third-party app does not support HMAC, it is possible to use custom headers to generate some layer of authentication. However, this is not as secure as signing with HMAC. Custom headers with a static secret may not help you evading MIM or replay attacks per default.



## Webhook URL validation

To be continued.



## Webhook response codes

To be continued.
