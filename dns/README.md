# DNS API

The DNS API can be used to manage public names and services on the SAFE Network.

DNS can be used to share public data and make it easily accessible.

This can be compared to the general web hosting on the clearnet where the user has to register a domain (e.g. `example.com`) and then map a subdomain (e.g. `www`) to his hosting provider. Similarly, the SAFE Network user has to create a long name (e.g. `example`) and then map a service (e.g. `www`) to a directory.

Any user can access public data using the service and the long name (e.g. `www.example`). Web browsers will display the content of the directory (e.g. `index.html`) associated with the service.

### Conventions

| Field | Description |
| --- | --- |
| longName | A human readable name that can be used for sharing public content (e.g. `example`). |
| serviceName | A service (e.g. `www`) that can be mapped to a long name (e.g. `example`). |
| rootPath | An enum representation of the root directory (`app` or `drive`).<br> `app` specifies the app's root directory, while `drive` corresponds to the SAFE Drive of the user. |
| serviceHomeDirPath | The full path of a home directory (e.g. `/websites/example`) that can be mapped to a service (e.g. `www`). |
