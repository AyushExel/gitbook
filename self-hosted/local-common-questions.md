---
description: Frequently asked questions about setting up locally-hosted versions of our app
---

# Local FAQ

### First time setup

The first time you launch local we will automatically log you in and prompt you to create a user with email and password. You should use that email and password that you originally used to log back in. If you need to reset the password you can start wandb/local with the LOCAL\_RESTORE environment variable set and use the temporary username / password that's printed out in the docker logs.

### Resetting your password

You can set the LOCAL\_RESTORE environment variable when you start local.  If you're starting wandb local using our cli you can do so with `wandb local -e LOCAL_RESTORE=true`

