# Domains and Subdomains

Webhosting services are provided to a specific 2nd level domain (example.com). A third level (or subdomain) "www" domain (www.example.com) can be automatically created for this domain (by your choice in [Hosting Control Panel](https://my.nuclear.hosting) during creating a new webhosting), as an alias (example.com and www.example.com are the same web presentation).

You can create an unlimited number of other subdomains on your domain (my.example.com). Nuclear.Hosting provide **3 types of subdomains** which are sligthly different in usage.

## 1. Subdomain Vhost

### Description

A subdomain is created like a standalone webhosting but its directory is located under the main domain hosting directory structure. The primary domain will have access to this subdomain directory (eg. with PHP script).

**Subdomain Vhost features:**

 - custom folder name for subdomain
 - turn on / off custom Error pages
 - enable / disable "www" subdomain alias (www.sub.example.com)
 - custom PHP version with custom PHP settings
 - custom password protected AWStats statistics
 - custom redirects
 - Available for both VIP and Basic memberships

**Subdomain Vhost Limitations:**

 - primary domain have access to subdomains data on the server (eg. within PHP script)
 - is linked with primary domain

### How to create

In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Subdomain (Vhost)```. To create a new subdomain click on the green ```Add new subdomain```.

## 2. Subdomain Alias

### Description

It is like a regular 2nd level domain alias. This subdomain is not physicaly created, it is just an alias which can be redirected (HTTP 301 code) either to primary domain or another domain / URL. Also can be pointed to specific directory on your primary domain FTP account.

**Subdomain Alias features:**

 - it is like an alias / virtual alias
 - can be redirected to another domain (HTTP 301)
 - can be redirected / routed to specific directory on the primary domain
 - different redirection types (by mod_rewrite) like: no flag, R, L, R+L, R=301+L
 - Let's Encrypt SSL Support (optinaly can be turned off for specific subdomain)
 - Available for both VIP and Basic memberships

**Subdomain Alias limitations:**

 - is linked with primary domain
 - primary domain have access to subdomains data on the server (eg. within PHP script)
 - no individual PHP settings or PHP versions (the same PHP version and configuration is applied like on primary domain)

### How to create

In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Subdomain for website```. To create a new subdomain click on the green ```Add new Subdomain```.

## 3. Standalone subdomain

### Description

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
 - you need a free hosting slot availbe to create a standalone subdomain (within max. domains limits of your account)

### How to create

The procedure is the same like when you creating a webhosting for a new 2nd level domain. In the [Hosting Control Panel](https://my.nuclear.hosting) navigate to ```Sites``` section and in the left-hand menu click on the ```Website```. To create a new subdomain click on the green ```Add new website```.

## Subdomains comparsion

|     | Subdomain Vhost | Subdomain Alias | Subdomain Standalone  |
|:---| ------------- |:-------------:|:-----:|
| SSL Let's Encrypt | ✓ | ✓ | ✓ |
| SSL Support | ✓ | ✕ | ✓ |
| Custom PHP version | ✓ | ✕ | ✓ |
| Custom PHP Configuration | ✓ | ✕ | ✓ |
| Data accesible from primary domain  | ✓ | ✓ | ✕ |
| Depends on primary domain | ✓ | ✓ | ✕ |
| Custom redirects | ✓ | ✓ | ✓ |
| Full-featured webhosting  | ✕ | ✕ | ✓ |
| Requires available hosting slot  | ✕ | ✕ | ✓ |

## Aliases

### What are domain aliases

An alias is a web server setting that assigns multiple domain names to a single virtual host in server configuration. It allows to display one web site under several domain names.

Alias can be configured in your [Hosting Control Panel](https://my.nuclear.hosting), under ```Sites``` section and then in the left-hand menu click on the ```Aliasdomain for website```.

### How to configure new domain alias

There is several way how to configure domain aliases with several different options regarding usage and behaviour you are expecting.

![Alias settings](img/domain_alias.png)

#### The same web presentations on different domains

You will use this option if you own different domains and you want everyone to have the same website.

Another use-case is when you have a domain pointed to another web hosting, you plan to transfer this domain to Nuclear.Hosting but with a newer website or newer content - you can dev a new version on hosting created on NH, on the original domain name without changing DNS record and just use an alias domain (or alias subdomain) to build a new version of the website and after that, you simply change DNS record of that domain.

**Example:** You have two domain names: ```example1.com``` and ```example2.com```. A domain ```example1.com``` has created a web hosting with website uploaded and is considered as *main* domain. The same content you want to see on the ```example2.com``` without creating an another standalone hosting and duplicating all website files to there, which is unnecessary. To achieve desired behaviour you need to configure ```example2.com``` as alias for ```example1.com``` and change a coresponding DNS record for ```example2.com``` (point domain to our servers).

To configure such domain alias, navigate to your [Hosting Control Panel](https://my.nuclear.hosting), ```Sites``` and ```Aliasdomain for website```, click on the ```Add new Aliasdomain```.

Complete the form as described bellow:

 - ```Domain``` enter your alias domain name
 - ```Parent website``` is a target (website to show when you enter alias domain name) for your alias
 - ```Redirect Type``` keep unchanged (```No redirect```)
 - ```Redirect path``` keep empty
 - ```Auto-Subdomain``` change value when you want to use wildcard-domain within your alias (*.youralias.tld) or www subdomain (www.youralias.tld) or just simple (none value) original alias domain name (name you entered into ```Domain``` field)

 Now just click on the ```Save``` button.

!!! note
	Do not forget to configure DNS zone of your alias domain and point to NH servers. The procedure is the same as for poiting domain for a regular hosting, described [here](/domains/#how-to-point-my-domain-to-nuclearhosting).

#### Different web presentations on different domains on one hosting

FIXME: Toto nejde ako na CH, musi sa to nasmerovat do zlozky v "Cesta presmerovani"

Thanks to aliases, you can run several different web presentations on different domains on one hosting. This solution is suitable in a situation where creating or purchasing standalone hosting for a given domain name would be unnecessary.

In this case you can point your alias domain to existing subdomain on already hosted domain.

**Example:** You have hosting created for a domain ```example.com``` and another domains ```mydomain.net``` and ```yourdomain.org``` where you want to create a simple websites without creating a new standalone hosting accounts for them. To do this, you need to create an two folders on ```example.com``` FTP space, let say ```mydomain``` and ```yourdomain``` in the main ```/web``` folder. Upload your websites to those folders. Configure domain ```mydomain.net``` as an alias for ```example.com``` and configure ```Redirect Path``` to folder ```/mydomain/``` and repeat the same for ```yourdomain.org``` but enter ```/yourdomain/``` to ```Redirect Path```. Configure necessary DNS records. Now when you enter ```mydomain.net``` content from ```example.com/mydomain``` will be loaded and when you enter ```yourdomain.org```, content from ```example.com/yourdomain``` will appear.

To configure this type of domain alias navigate to your [Hosting Control Panel](https://my.nuclear.hosting), ```Sites``` and ```Aliasdomain for website```, click on the ```Add new Aliasdomain```.

Complete the form as described bellow:

 - ```Domain``` enter your alias domain name
 - ```Parent website``` is a target (website to show when you enter alias domain name) for your alias
 - ```Redirect Type``` keep unchanged (```No redirect```) or choose ```L```
 - ```Redirect path``` enter folder name where website for this alias domain will be uploaded
 - ```Auto-Subdomain``` change value when you want to use wildcard-domain within your alias (*.youralias.tld) or www subdomain (www.youralias.tld) or just simple (none value) original alias domain name (name you entered into ```Domain``` field)

 Now just click on the ```Save``` button.

!!! note
	Do not forget to configure DNS zone of your alias domain and point to NH servers. The procedure is the same as for poiting domain for a regular hosting, described [here](/domains/#how-to-point-my-domain-to-nuclearhosting).

## Websites & Web Hosting

### Why we do not support caching servers (memcached, redis)

On our webservers we do not support caching servers like Memcached or Redis.

There is a big security problem with shared hosting and caching servers. Caching servers uses memory that is shared by all customers on the server. Then it is not such a problem to use the content of this shared memory to penetrate a foreign site.

Unfortunately, many shared hosting companies do not address this risk. But for us, safety comes first.

On the other side, the absence of caching servers support we have fast SSD/NVMe disks on all our servers. We are also able to connect for you a special RAM-Disk which is a dedicated piece of RAM memory connected as a regular directory (dedicated for you) where you can place your cache files. The advantage of this solution is that it's very similar to memcached or redis server where cached data are placed into RAM.

## WAF - Web Application Firewall

### What is WAF

A ```web application firewall (WAF)``` is an application firewall for HTTP applications. It applies a set of rules to an HTTP conversation. By inspecting HTTP traffic, it can prevent attacks stemming from web application security flaws, such as SQL injection, cross-site scripting (XSS), file inclusion, and security misconfigurations.

On our servers we are using [ModSecurity](https://www.modsecurity.org/) as WAF.

### Known issues of incompatibilities of WAF

Some application causing False Positive results from the WAF and those kind of requests are blocked. For those applications is not possible to fix the rules which are causing False positive cases. The only solution is to turn off those rules particulary or turn off WAF for whole application (**not recommended!**). To investigate those cases contact our Support team and with co-operation we decide what is the best solution of your particular situation.

Bellow you can find well-known False positive WAF cases which we can solve easily by disabling particular WAF rules for your website. To do that, please contact our Support team.

**Well-known False positive WAF issues:**

 - Divi Builder for Wordpress