# NFS API

The NFS (Network File System) API can be used to create directories and files on the SAFE Network.

The NFS API enables the creation of private and public directories. Private directories are encrypted with the user’s MAID keys and thus are only accessible by the user. Public directories are stored as unencrypted data on the network. Public directories can be used to share public data.

Public directories are created mostly to map with a service and long name using the DNS API, making it easy to share.

A directory called `SAFEDrive` can be used to store data that needs to be shared between multiple apps. This directory exists independently of any app.

When an app is authorized by a user for the first time, SAFE Launcher creates an exclusive directory for that app. This is the app’s root directory, and it's sandboxed such that other apps cannot access its content. So if the app wants to create its own configuration files, directories, etc. – which it does not want to share with other apps – it can put them into its dedicated root directory.

Apps can create directories and files in their dedicated root directory or in the SAFE Drive of the user. To access `SAFEDrive`, the app must be authorized with the `SAFE_DRIVE_ACCESS` permission.
