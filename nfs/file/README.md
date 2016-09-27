# File API

### Conventions

| Field | Description |
| --- | --- |
| rootPath | An enum representation of the root directory (`app` or `drive`).<br> `app` specifies the app's root directory, while `drive` corresponds to the SAFE Drive of the user.<br><br>For example, `/images/sample.png` can either refer to `/SAFEDrive/images/sample.png` or `/sample-app-root-dir/images/sample.png` depending on if `rootPath` refers to `drive` or `app` respectively. |
| filePath | The full path of the file (e.g. `/images/sample.png`). |

### Limitations

**The update file endpoint has been temporarily deprecated.** Currently `SequentialEncryptor` is used via `safe_core` to write chunks as and when available which does not support taking offsets. Once the `self_encryption` crate can support taking offsets while also writing chunks to the network as and when chunks are formed, the update file endpoint will be re-enabled. At present the workaround for modifying a file will be to delete and create it again as a new file.
