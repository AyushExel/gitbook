---
description: Save a file to the cloud to associate the current run
---

# wandb.save

There are two ways to save a file to associate with a run.

1. Use `wandb.save(filename)`.
2. Put a file in the wandb run directory, and it will get uploaded at the end of the run.

{% hint style="info" %}
If you're [resuming](../advanced/resuming.md) a run, you can recover a file by calling`wandb.restore(filename)`
{% endhint %}

If you want to sync files as they're being written, you can specify a filename or glob in `wandb.save`.

## Examples of wandb.save

Save a model file from the current directory:

```python
wandb.save('model.h5')
```

Save all files that currently exist containing the substring "ckpt":

```python
wandb.save('../logs/*ckpt*')
```

Save any files starting with "checkpoint" as they're written to:

```python
wandb.save(os.path.join(wandb.run.dir, "checkpoint*"))
```

{% hint style="info" %}
W&B's local run directories are by default inside the ./wandb directory relative to your script, and the path looks like run-20171023\_105053-3o4933r0 where 20171023\_105053 is the timestamp and 3o4933r0 is the ID of the run. You can set the WANDB\_DIR environment variable, or the dir keyword argument of wandb.init to an absolute path and files will be written within that directory instead.
{% endhint %}

## Example of saving a file to the wandb run directory

The file "model.h5" is saved into the wandb.run.dir and will be uploaded at the end of training.

```python
import wandb
wandb.init()

model.fit(X_train, y_train,  validation_data=(X_test, y_test),
    callbacks=[wandb.keras.WandbCallback()])
model.save(os.path.join(wandb.run.dir, "model.h5"))
```

## Ignoring certain files

You can edit the `wandb/settings` file and set ignore\_globs equal to a comma separated list of [globs](https://en.wikipedia.org/wiki/Glob*%28programming%29). You can also set the **WANDB\_IGNORE\_GLOBS** environment variable. A common use case is to prevent the git patch that we automatically create from being uploaded i.e. **WANDB\_IGNORE\_GLOBS=\*.patch**

## Sync files before the end of the run

If you have a long run, you might want to see files like model checkpoints uploaded to the cloud before the end of the run. By default, we wait to upload most files until the end of the run. You can add a `wandb.save('*.pth')` or just `wandb.save('latest.pth')` in your script to upload those files whenever they are written or updated.

## Get the run name

If you'd like to use the run name from within your script, you can use `wandb.run.name` and you'll get the run name— "blissful-waterfall-2" for example.

