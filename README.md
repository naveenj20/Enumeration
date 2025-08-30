## NAME: NAVEEN JAISANKER
## REG. NO.: 212224110039
## DATE: 30/08/2025

# Explore Google hacking and enumeration 

# AIM:

To use Google for gathering information and perform enumeration of targets

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various Google hacking keywords and enumeration tools as follows:


### Step 3:
Open terminal and try execute some kali linux commands

## Pen Test Tools Categories:  

| Operator    | Description                        | Example Usage           |
| ----------- | ---------------------------------- | ----------------------- |
| `site:`     | Search within a specific domain    | `site:example.com`      |
| `inurl:`    | Search in URL                      | `inurl:admin`           |
| `intitle:`  | Search in page title               | `intitle:"index of"`    |
| `filetype:` | Search by file type                | `filetype:pdf`          |
| `intext:`   | Search inside page text            | `intext:"confidential"` |
| `link:`     | Pages that link to a specific site | `link:example.com`      |
| `cache:`    | View cached version of a site      | `cache:example.com`     |
| `ext:`      | Same as filetype                   | `ext:xls`               |

 ## Architecture 
 ```
+----------------------+
|   Attacker / Hacker  |
|   (Browser & Google) |
+----------+-----------+
           |
           | Google Dork Queries
           v
+---------------------------+
|       Google Search       |
+---------------------------+
           |
           | Indexed Public Content
           v
+---------------------------+
|   Target Websites / Data  |
| - Leaked files            |
| - Open directories        |
| - Sensitive info          |
+---------------------------+

```

# Output:
SITE:
<img width="1918" height="1021" alt="Screenshot 2025-08-30 154559" src="https://github.com/user-attachments/assets/5a8ea71b-0d6f-4e1e-8b3c-4c1c2629c894" />

INURL:
<img width="1919" height="1032" alt="Screenshot 2025-08-30 154641" src="https://github.com/user-attachments/assets/3e631157-c222-4941-bfae-3cee2b8fd449" />

INTITLE:
<img width="1919" height="1031" alt="Screenshot 2025-08-30 154742" src="https://github.com/user-attachments/assets/2f18382d-1b5e-4b10-937d-8acf1a4db9df" />

FILETYPE.PDF
<img width="1919" height="1027" alt="Screenshot 2025-08-30 154814" src="https://github.com/user-attachments/assets/388da503-e431-4cce-9562-5d2c1b856429" />

INTEXT:
<img width="1919" height="1017" alt="Screenshot 2025-08-30 154831" src="https://github.com/user-attachments/assets/1af99f63-3cef-477c-90a7-abc16f46324d" />

LINK:
<img width="1919" height="1026" alt="Screenshot 2025-08-30 154853" src="https://github.com/user-attachments/assets/310e95bc-90ff-4587-b61f-128daa68d06b" />

CACHE:
<img width="1919" height="1034" alt="Screenshot 2025-08-30 155023" src="https://github.com/user-attachments/assets/badeb877-1507-49a3-9090-feef48eaebdf" />


# DNS Enumeration
<img width="1173" height="906" alt="Screenshot 2025-08-30 155056" src="https://github.com/user-attachments/assets/ca207185-38df-4058-a173-576e18919e3f" />


## DNS Recon

| Record Type | Meaning                        | Example Output                   |
| ----------- | ------------------------------ | -------------------------------- |
| A           | Host to IPv4 address           | `example.com -> 93.184.216.34`   |
| AAAA        | Host to IPv6 address           | `example.com -> ::1`             |
| MX          | Mail server info               | `mail.example.com`               |
| NS          | Name servers                   | `ns1.example.com`                |
| TXT         | Misc data (SPF, verifications) | `v=spf1 include:_spf.google.com` |
| CNAME       | Canonical names (aliases)      | `www -> example.com`             |

## Common Tools Used (Kali Linux)

| Tool           | Description                                | Usage Example                           |
| -------------- | ------------------------------------------ | --------------------------------------- |
| `nslookup`     | DNS lookup tool (simple queries)           | `nslookup example.com`                  |
| `dig`          | DNS lookup utility (detailed)              | `dig example.com any`                   |
| `host`         | Simple DNS querying tool                   | `host example.com`                      |
| `dnsenum`      | Perl script to enumerate DNS info          | `dnsenum example.com`                   |
| `fierce`       | DNS scanner to locate non-contiguous IPs   | `fierce -dns example.com`               |
| `dnsrecon`     | Powerful DNS enumeration script            | `dnsrecon -d example.com -a`            |
| `theHarvester` | Subdomain enumeration using search engines | `theHarvester -d example.com -b google` |


## OUTPUT:

### NSLOOKUP:
<img width="506" height="1088" alt="Screenshot 2025-08-30 155124" src="https://github.com/user-attachments/assets/8d3c2ce8-bfb6-4a66-ac2a-626ca5b5e907" />


### DIG:
<img width="804" height="712" alt="Screenshot 2025-08-30 155138" src="https://github.com/user-attachments/assets/43b2f4c2-5532-41b1-b223-781ffa3c8257" />


### HOST:
<img width="762" height="495" alt="Screenshot 2025-08-30 155203" src="https://github.com/user-attachments/assets/4ad13dbb-8c60-49f2-bfea-f904c76408e6" />


### DNSENUM:
<img width="1173" height="906" alt="Screenshot 2025-08-30 155056" src="https://github.com/user-attachments/assets/abc7a6c4-74d0-4d99-9ef9-de062acfd3a6" />



### FIERCE:
<img width="785" height="858" alt="Screenshot 2025-08-30 155317" src="https://github.com/user-attachments/assets/a6a67848-6a35-4a7c-8ffc-3bc41a01b97c" />


### theHarvester:
<img width="757" height="776" alt="Screenshot 2025-08-30 155420" src="https://github.com/user-attachments/assets/16502832-f808-4026-a242-8447c40bf00e" />


## Architecture Diagram 
```
+-------------------+        +------------------+       +------------------+
|                   |        |                  |       |                  |
|   Attacker (You)  +------->|   Target Server   +<----->+    DNS Server    |
| Kali Linux / Parrot|       | (Mail / DNS Host) |       |  (Authoritative) |
+---------+---------+        +---------+--------+       +---------+--------+
          |                            ^                          ^
          |                            |                          |
          |                            |                          |
          |           +-----------------------------+            |
          |           |      Information Tools      |            |
          |           |-----------------------------|            |
          |           | smtp-user-enum              |            |
          |           | nmap --script smtp-enum-*   |            |
          |           | dnsenum                     |<-----------+
          |           +-----------------------------+
          |
          v
+-----------------------------+
|   Output/Report             |
|  - Usernames Found          |
|  - MX Records / Zones       |
|  - Subdomains / IPs         |
+-----------------------------+

```

## dnsenum
**Purpose:** A multithreaded Perl script to enumerate information from DNS servers.

**Use case:** Performs DNS zone transfers, brute force subdomains, and gather host IPs.

```
dnsenum example.com
```

## Output:

<img width="1173" height="906" alt="Screenshot 2025-08-30 155056" src="https://github.com/user-attachments/assets/5ae4122e-682c-4545-b52d-2284f3f47960" />


## smtp-user-enum
**Purpose:** Standalone tool used to enumerate valid users by using the VRFY, EXPN, or RCPT TO commands.

**Use case:** Brute-forces SMTP to find users.

```
smtp-user-enum -M VRFY -U users.txt -t <target-ip>
```
  
 ## Output

  <img width="849" height="858" alt="Screenshot 2025-08-30 155802" src="https://github.com/user-attachments/assets/649f1318-2322-443b-b650-fe078649d01e" />



## nmap –script smtp-enum-users.nse <hostname>

**Purpose:** Uses smtp-enum-users NSE script to enumerate valid users on an SMTP server.

**Use case:** Helps identify email accounts on mail servers.

```
nmap -p 25 --script smtp-enum-users.nse <target-ip>
```
## OUTPUT:

<img width="806" height="191" alt="Screenshot 2025-08-30 155841" src="https://github.com/user-attachments/assets/111bebe5-3fbd-4133-ac7e-4baab1b77f4f" />




## RESULT:
The Google hacking keywords and enumeration tools were identified and executed successfully
