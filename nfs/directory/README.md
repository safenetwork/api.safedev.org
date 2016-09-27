# Directory API

### Conventions

| Field | Description |
| --- | --- |
| rootPath | An enum representation of the root directory (`app` or `drive`).<br> `app` specifies the app's root directory, while `drive` corresponds to the SAFE Drive of the user.<br><br>For example, `/websites/example` can either refer to `/SAFEDrive/websites/example` or `/sample-app-root-dir/websites/example` depending on if `rootPath` refers to `drive` or `app` respectively. |
| directoryPath | The full path of the directory (e.g. `/websites/example`). |
| isPrivate | A boolean value to indicate whether the directory is private or public. |
