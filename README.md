# DataBroker blocklist

DataBroker Blocklist is a Pi-hole / DNS blocklist focused on data brokers and related tracking endpoints.

This project was created and is maintained by **seloc0des** for the open source Pi-hole community to help reduce data broker collection and enrichment by blocking known domains.

## Sources / methodology

Entries are compiled from publicly available information, including lists and research published by **incogni.com**, plus additional independent “deep internet” searching.

This list is not guaranteed to be complete or perfectly accurate; some domains may be legitimate for some users and environments.

## Non-affiliation

This project is not affiliated with Pi-hole, Incogni, or any of the companies listed in the blocklist.

## License

This repository is released under **CC0-1.0** (see `LICENSE`).

## Use with Pi-hole

This list is formatted in `hosts` style (one entry per line):

```
0.0.0.0 example.com
```

Pi-hole can consume this format as an adlist.

### Add the adlist

1. Host this repo on GitHub.
2. In Pi-hole, go to **Group Management** -> **Adlists**.
3. Add the *raw* URL to the list file, for example:

```
https://raw.githubusercontent.com/<YOUR_GITHUB_USERNAME>/<YOUR_REPO_NAME>/main/lists/databroker.txt
```

4. Click **Add**.
5. Update gravity (Pi-hole UI: **Tools** -> **Update Gravity**) or run:

```
pihole -g
```

## Notes

- Blocking apex domains (e.g. `oracle.com`) can break legitimate content and services from those companies. If you experience breakage, consider removing the entry or scoping to specific subdomains.
- If you’d prefer “domains-only” format (one domain per line), you can transform the file by removing the leading `0.0.0.0 ` prefix.

## Contributing

- Please submit PRs that add *domains only* (no URLs, paths, or wildcards).
- Keep one domain per line.
- If you’re adding a new broker, include a short note in the PR description describing why it belongs (ideally with a link to a public source).

## List files

- `lists/databroker.txt` - main blocklist
