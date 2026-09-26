# DNS Server

A lightweight DNS server implemented in **Python 3**, demonstrating DNS query handling, zone-file based resolution, and UDP networking.

## Features

* **DNS query handling** with support for resolving **A records**.
* **Zone file loading** from JSON-formatted configuration files.
* **UDP-based DNS server** listening on port 53.
* **Custom IP binding** for configuring the server's network interface.
* Zone files support `$origin`, TTL, and A record definitions.
* Can be tested using standard DNS tools such as **`dig`** and **`nslookup`**.

## Tech Stack

**Python 3 · DNS · UDP · JSON**

## Project Structure

```text
DNS_Server/
├── README.md
└── DNS-master/
    ├── dns.py
    └── zones/
        ├── yahoo.com.zone
        └── youtube.com.zone
```

## Zone File

Zone files define domain records using JSON:

```json
{
  "$origin": "yahoo.com",
  "a": [
    {
      "ttl": 3600,
      "value": "192.0.2.1"
    }
  ]
}
```

## Run

```bash
cd DNS-master
python3 dns.py
```

The server listens for DNS queries on **UDP port 53**.

Test with:

```bash
dig @<server-ip> yahoo.com
```

or:

```bash
nslookup yahoo.com <server-ip>
```

No external dependencies are required beyond **Python's standard library**.
