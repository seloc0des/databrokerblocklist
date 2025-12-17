# DataBroker blocklist

DataBroker Blocklist is a Pi-hole / DNS blocklist focused on data brokers and related tracking endpoints.

This project was created and is maintained by **seloc0des** for the open source Pi-hole community to help reduce data broker collection and enrichment by blocking known domains after
the news of featured Urban VPN caught stealing data and AI usage history from its users. Information on that, can be found below. I've also combed through the incogni blog database and data broker url
submissions and compiled those data brokers to this list as well. Cutting off direct routes to the data brokers themselves.

https://www.techzine.eu/news/security/137399/ai-conversations-of-8-million-users-leaked-via-browser-extensions/
https://www.csoonline.com/article/4106949/featured-urban-vpn-caught-stealing-private-ai-chats.html

"Urban VPN's latest news reveals serious privacy concerns: since July 2025, the Urban VPN Proxy browser extension has been secretly harvesting users' AI chatbot conversations from platforms like ChatGPT, Claude, Gemini, and Microsoft Copilot. This data collection occurs even when VPN features are disabled, and the captured sensitive AI interactions are sent to Urban VPN's servers and shared or sold to third-party data brokers affiliated with Urban Cyber Security Inc. and BiScience. The extension automatically updated without notifying users, putting millions of AI chat users at risk of their conversations being exposed.

Despite Urban VPN's marketing of an "AI protection" feature, it does not prevent the data harvesting, which is embedded in the extension from version 5.5.0 onward, released in July 2025. The browser extension remains available on major stores like Chrome Web Store and Edge Add-ons, continuing this covert data interception practice. This significant privacy breach has brought Urban VPN under scrutiny, overshadowing its prior reputation as a free VPN service with over 70 million users worldwide.

Urban VPN operates primarily as a peer-to-peer (P2P) VPN network with AES-256 encryption using OpenVPN protocol. Though it provides unlimited simultaneous device connections and free service, it has faced criticism for its data logging and sharing practices, and lack of transparency such as the absence of third-party audits. Its affiliation with US jurisdiction and data brokerage companies adds to the privacy concerns. Users seeking stronger privacy protections and security are advised to consider these risks before using Urban VPN."

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
