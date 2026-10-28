# Arkitektur

Bastion för Android är en fristående Kotlin-app i tidigt skede. Den delar ingen kod med de andra plattformarna.

```text
        +-----------------------------+
        |   Android-app (Kotlin)      |
        |   MainActivity              |
        +--------------+--------------+
                       |
        +--------------+--------------+
        |  BastionSshSession          |
        +--------------+--------------+
                       |
                Apache MINA SSHD
```

## Delar

- **SSH** går genom Apache MINA SSHD. Testerna startar en riktig SSH-server i processen och verifierar hela vägen utan systemets egen sshd.
- **Byggskript och appberoenden** är olika beroendeytor i Gradle. Ett byggverktygsberoende ska inte flyttas till appens runtime för att få en kontroll grön.

## Säkerhetsgräns

Läs-, tolknings- och skrivfel i `known_hosts` ska avvisa anslutningen, aldrig slå på `AcceptAllServerKeyVerifier`. Nycklar och lösenord lagras aldrig i repot eller i testdata.
