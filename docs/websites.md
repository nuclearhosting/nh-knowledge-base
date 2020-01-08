# Domains and Subdomains

Webhosting services are provided to a specific 2nd level domain (example.com). A third level (or subdomain) "www" domain (www.example.com) can be automatically created for this domain (by your choice in [Hosting Control Panel](https://my.nuclear.hosting) during creating a new webhosting), as an alias (example.com and www.example.com are the same web presentation).

You can create an unlimited number of other subdomains on your domain (my.example.com). Nuclear.Hosting provide **3 types of subdomains** which are sligthly different in usage.

### 1. Subdomain Vhost

#### Description

A subdomain is created like a standalone webhosting but its directory is located under the main domain hosting directory structure. The primary domain will have access to this subdomain directory (eg. with PHP script).

**Subdomain Vhost features:**

 - custom folder name for subdomain
 - turn on / off custom Error pages
 - enable / disable "www" subdomain alias (www.sub.example.com)
 - custom PHP version with custom PHP settings
 - custom password protected AWStats statistics
 - custom redirects
 - Available to both VIP and Free memberships

**Subdomain Vhost Limitations:**

 - does not support SSL certificates (even SSL Lets Encryp't)
 - primary domain have access to subdomains data on the server (eg. within PHP script)
 - it depends / is linked with primary domain

#### How to create

In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Subdomain (Vhost)```. To create a new subdomain click on the green ```Add new subdomain```.

### 2. Subdomain Alias

#### Description

It is like a regular 2nd level domain alias. This subdomain is not physicaly created, it is just an alias which can be redirected (HTTP 301 code) either to primary domain or another domain / URL. Also can be pointed to specific directory on your primary domain FTP account.

**Subdomain Alias features:**

 - it is like an alias / virtual alias
 - can be redirected to another domain (HTTP 301)
 - can be redirected / routed to specific directory on the primary domain
 - different redirection types (by mod_rewrite) like: no flag, R, L, R+L, R=301+L
 - Let's Encrypt SSL Support (optinaly can be turned off for specific subdomain)
 - Available to both VIP and Free memberships

**Subdomain Alias limitations:**

 - it depends / is linked with primary domain
 - primary domain have access to subdomains data on the server (eg. within PHP script)
 - no individual PHP settings or PHP versions (the same PHP version and configuration is applied like on primary domain)

#### How to create

In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Subdomain for website```. To create a new subdomain click on the green ```Add new Subdomain```.

### 3. Standalone subdomain

#### Description

Standalone subdomain is like a regular webhosting for 2nd level domain. It is independent on any other domain. It is a full-featured webhosting. **Standalone subdomains are available only for VIP membership users.**

**Standalone subdomain features:**

 - standalone and full-features webhosting with all features
 - indenpedent of any other domain
 - Let's Encrypt SSL support
 - custom PHP version & configuration
 - custom / dedicated FTP enviroment (no shared with any domain)
 - and all regular webhosting benefits and features

**Standalone subdomain limitations:**

 - no shared files / data / folders with primary or any other domain

#### How to create

The procedure is the same like when you creating a webhosting for a new 2nd level domain. In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Website```. To create a new subdomain click on the green ```Add new website```.

### Subdomains comparsion

|     | Subdomain Vhost | Subdomain Alias | Subdomain Standalone  |
|:---| ------------- |:-------------:|:-----:|
| SSL Let's Encrypt | ✕ | ✓ | ✓ |
| SSL Support | ✕ | ✕ | ✓ |
| Custom PHP version | ✓ | ✕ | ✓ |
| Custom PHP Configuration | ✓ | ✕ | ✓ |
| Data accesible from primary domain  | ✓ | ✓ | ✕ |
| Depends on primary domain | ✓ | ✓ | ✕ |
| Custom redirects | ✓ | ✓ | ✓ |
| Full-featured webhosting  | ✕ | ✕ | ✓ |

## Aliases

# Websites & Webhosting

## Why we do not support caching servers (memcached, redis)

On our webservers we do not support caching servers like Memcached or Redis.

There is a big security problem with shared hosting and caching servers. Caching servers uses memory that is shared by all customers on the server. Then it is not such a problem to use the content of this shared memory to penetrate a foreign site.

Unfortunately, many shared hosting companies do not address this risk. But for us, safety comes first.

On the other side, the absence of caching servers support we have fast SSD/NVMe disks on all our servers. We are also able to connect for you a special RAM-Disk which is a dedicated piece of RAM memory connected as a regular directory (dedicated for you) where you can place your cache files. The advantage of this solution is that it's very similar to memcached or redis server where cached data are placed into RAM.