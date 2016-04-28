# Wercker cache step
[Wercker](https://wercker.com) step to store and restore directories between builds.
You can use this to cache Maven, SBT, Ivy dependency repository to speed up the
step when the build tool "Download the whole internet"

![Oh look Maven downloading internet](maven-download-internet.png "Oh look Maven downloading internet")

# Options

- `action` Either "store" or "restore"
- `directories` (optional) Space separated list of directories to cache. Default: ``$HOME/.m2 $HOME/.ivy2 $HOME/.sbt`

# Example
```yaml
build:
    steps:
        - sharpershape/cache:
            action: restore

    # ... your steps here ...

    after-steps:
        - sharpershape/cache:
            action: store
```
# License
The MIT License (MIT)

# Changelog

## 0.1.0
- Initial release