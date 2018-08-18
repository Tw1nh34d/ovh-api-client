## Embedded libs for external scripts

### ovh-api-lib.sh

- OvhRequestApi() is wrapper for ovh-api-bash-client.sh
- use jsonsh-lib.sh ( just using loadJSON() )

**usage**
```
OvhRequestApi url [method] [post_data]
```

From your script or commandline, you can set :
- OVHAPI_BASHCLIENT_PROFILE
- OVHAPI_TARGET
- OVHAPILIB_DEBUG to 1 to enable lib debugging

This function set variables OVHAPI_HTTP_STATUS and OVHAPI_HTTP_RESPONSE

OVHAPI_HTTP_RESPONSE is forwarded to loadJSON() to avoid user to put this line each time.

#### Samples

Once you've a valid OVH API authentication, you can use the library

You can find some samples scripts in the **samples/** directory

**sample usage**

```
OVHAPI_BASHCLIENT_PROFILE=demo samples/list-domains.sh
```

See **samples/** directory for more details
