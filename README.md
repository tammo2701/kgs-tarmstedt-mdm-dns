# kgs-tarmstedt-mdm-dns

Pi-hole-Blocklist für MDM- und Enrollment-Domains.

## Einbinden (Adlist)

Pi-hole-UI → **Lists** → **Add a new list**:

```
https://raw.githubusercontent.com/tammo2701/kgs-tarmstedt-mdm-dns/main/mdm-block.txt
```

Danach **Tools → Update Gravity** ausführen (oder `docker exec pihole pihole -g`).

## Fallback: Regex

Falls die Subdomains nicht gesperrt werden: **Domains → Add a new domain** →
*Regex filter* + *Add to denylist* und den Inhalt von `regex-fallback.txt` einfügen.

## Prüfen

```
curl -s "https://<dein-doh-host>/<TOKEN>?name=decon.relution.io&type=A"
```

Gesperrte Domains liefern `0.0.0.0` bzw. NXDOMAIN.

## Hinweis

Das Repo ist öffentlich: **niemals** den DoH-Token oder Passwörter einchecken.
