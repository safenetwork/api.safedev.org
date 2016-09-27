# Authorization API

Reading public data using the DNS API does not require an authorization token. All other endpoints require authorized access.

Any app that wants to access endpoints that require authorized access must receive an authorization token from SAFE Launcher.

The app will initiate the authorization request with information about the app itself and the required permissions. SAFE Launcher will then display a prompt to the user with the app information along with the requested permissions. Once the user authorizes the request, the app will receive an authorization token. If the user denies the request, the app will receive an unauthorized error response.

### Unauthorized access

Unencrypted public data can be accessed without any authorization. For example, websites and blogs, which are made available for public viewing, require no authorization.

### Authorized access

Apps have to authorize with SAFE Launcher to get authorized access. SAFE Launcher will grant an authorization token once the user authorizes the app. Apps will use the obtained authorization token to invoke the REST API calls. These tokens are session-based and thus will be valid only while SAFE Launcher is running.

Apps can cache their authorization token to avoid making unnecessary authorization requests to SAFE Launcher (e.g. a user could restart an app while SAFE Launcher is still running).

### App directory

When an app is authorized for the first time, a root directory for the app is created and mapped to the account. The app can store and retrieve data only from this root directory, it cannot access the root directory of other apps.

If the app needs to access `SAFEDrive`, it must send an authorization request with the `SAFE_DRIVE_ACCESS` permission and the user must grant the permission.

### SAFE Drive

The SAFE Drive directory (`SAFEDrive`) is created by default for every account. Apps cannot access the SAFE Drive directory unless the user grants the `SAFE_DRIVE_ACCESS` permission at the time of authorization.

Users can use their SAFE Drive to store private and public data. For example, they can use it to store documents, images, audio files, videos, websites, etc.

SAFE Drive can also be used by apps for sharing data. For example, a camera app can store images in SAFE Drive and another image editing app can read the images from SAFE Drive.
