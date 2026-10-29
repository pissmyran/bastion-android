# Architecture

Bastion for Android is a standalone Kotlin app at an early stage. It shares no code with the other platforms.

```text
        +-----------------------------+
        |   Android app (Kotlin)      |
        |   MainActivity              |
        +--------------+--------------+
                       |
        +--------------+--------------+
        |  BastionSshSession          |
        +--------------+--------------+
                       |
                Apache MINA SSHD
```

## Parts

- **SSH** goes through Apache MINA SSHD. The tests start a real SSH server in the process and verify the whole path without the system's own sshd.
- **Build scripts and app dependencies** are separate dependency surfaces in Gradle. A build tool dependency must not be moved into the app's runtime to turn a check green.

## Security boundary

Read, parse and write errors in `known_hosts` must reject the connection, never enable `AcceptAllServerKeyVerifier`. Keys and passwords are never stored in the repo or in test data.
