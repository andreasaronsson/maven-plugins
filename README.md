# maven-plugins

Maven plugin versions and configuration


`HostKeyAlgorithms ssh-rsa` to your `~/.ssh/config`

ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts

## Release

Releases are published to Maven Central through the Sonatype Central Portal
(https://central.sonatype.com) using `central-publishing-maven-plugin`.

Prerequisites:

- A Central Portal user token (Account -> Generate User Token) in `~/.m2/settings.xml`:

  ```xml
  <server>
    <id>central</id>
    <username>TOKEN_USERNAME</username>
    <password>TOKEN_PASSWORD</password>
  </server>
  ```

- A GPG key for signing, published to a public keyserver.

Bump the version in `pom.xml`, then run:

```
mvn -DperformRelease=true clean deploy
```

The bundle is signed, uploaded, validated and published automatically
(`autoPublish`), and the build waits until the release is published.
