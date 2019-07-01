# What is a domain name

The domain or domain name is simply the internet address of your website, for example www.nuclear.hosdting. Each domain corresponds to a series of numbers. IP addresses (eg 1.1.1.1). It is always unique, so there can not be two identical domains.

We generally divide the domain into three levels. Individual levels are separated by a dot.

## First (TOP) Level Domain

First-level domain or Top-Level Domain, abbreviated to TLD. This domain is at the end or end. after the last dot. TLD domains are divided into two types:

 * Geographic - ccTLD
 * Generic - gTLD

### Geographic ccTLD

These domains are assigned to individual states. As a rule, they are in the form of an abbreviation for the country, for example, .UK for the United Kingdom, .SK for Slovakia, and so on.

### Generic gTLD

You can register these domains completely, they are general domains that are not associated with any state. (e.g., com, org, net). New registrations are now open for new gTLD domains (such as free, blog, party, movie, live, and more).

## Domain of the 2nd level

The 2nd level domain is a sequence of unique characters behind the national or generic domain. This domain is paid and must be registered. In this domain, only the English keyboard characters and only a small part of the ASCII characters can be used. The maximum domain length is 63 characters.

There are exceptions, domains that can contain special characters called IDN (Internationalized Domain Names). These domains contain special characters as a result, but they convert to a sequence of common characters in the background.

## Domain of 3rd level

We also call it a subdomain. The subdomain expands the second order domain. And so you can use the subdomain, you must be the 2nd order domain owner. No 3rd level domains are charged. The domain is in the form of, for example, subdomain.my-domain.com, but also www.my-domain.com.

# How to get your domain name

In case you don't have your domain name yet, you have to register your domain first, before you can start using Nuclear.Hosting webhosting services.

Domain is a necessary part of webhosting services.

!!! note
	Nuclear.Hosting does not provide domain name registrations, currently.

!!! note
	Read more about [what is a domain name](#what-is-a-domain-name).

Domain names registrations provide a several companies - *domain registrars*. Before you register your domain name, you have to think about its name and check, if this domain name is available to register (if is not registered by someone else).

You can choose from many TLD - Top Level Domains - such as: .com, .net, .co.uk, .biz, .store, .shop, .eu and many more. It is your choice which TLD you choose.

Domain names registration prices are vary and particular prices can be found in registrars pricelist.

## What domain registrar should I choose

As we mention before, there are several companies providing domain names registrations, out there.

We should recommend to use any of these:

 * NameCheap.com
 * Enom.com
 * Verisign

## I have sucessfuly register my domain, what now?

If you sucessfuly registered your domain name, you have to correctly setup DNS Name Servers for your domain. For more information how to do that, [continue here](#how_to_point_domain_to_hosting).

# How to point my domain to Nuclear.Hosting

If you have your domain name already registered, there are two options, how to point your domain to your webhosting.

1. By changing Name Servers on your domain (*recommended*)
2. By changing DNS records separately

## How to change DNS Name Servers on my domain

By changing DNS Name servers you define that all DNS records and all DNS queries to your domain are managed by our nameservers.

!!! note
	This is recommended way how to point your domain to NH webhosting.

About DNS Name servers change, you have to ask your domain name registrar. In the other words, the provider where you register your domain name. For example: GoDaddy, NameCheap, Moniker, Enom, and so on.

**Ask your domain registrar to setup these DNS Nameservers for your domain:**

!!! important
	**NS1 (primary):** ns1.nuclear.hosting

	**NS2 (secondary):** ns2.nuclear.hosting


!!! tip
	If you have DNSSEC enabled on your domain, delete all set DNS keys together with the nameserver change!

### Why to use our NameServers?

 * In our nameservers, all DNS records needed for properly services operation are automatically set up correctly.
 * Using our nameserver reduces the risk of possible service malfunctions.
 * Some services or features may be available only if you use our nameservers, such as automatically DKIM settings, automatically SPF settings, DNSSEC, cloud webhosting features and more.

## Changing DNS records separately

If you do not have the ability to change DNS name servers, you can set individual DNS records. You can find the values for the settings in the control panel on the home page. However, **we do not recommend this solution**.