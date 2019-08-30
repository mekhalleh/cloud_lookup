# cloud_lookup

This module can be useful if you need to test the security of your server and your
website behind a solution Cloud based. By discovering the origin IP address of the
targeted host.

More precisely, I use multiple data sources (in order ViewDNS.info, DNS enumeration and Censys)
to collect assigned (or have been assigned) IP addresses from the targeted site or domain
that uses the following:

- Amazon Cloudflare
- Amazon CloudFront
- Imperva Incapsula
- InGen Security (BinarySec EasyWAF)
- Sucuri

![alt text][module_info]

![alt text][module_advanced]

## Scenarios

### For auditing purpose

If successful, you must be able to obtain the IP(s) address of the website as follows:

![alt text][module_good]

In this case '**A direct-connect IP address was found**' is reported.

However, **_some disreputable administrators_** used a simple redircetion (301 and 302)
to force the passage through the WAF. This makes the IP address leak in the 'location'
parameter of the HTTP header.

![alt text][module_leak]

In this case '**A leaked IP address was found**' is displayed but the bypass is NOT effective.

[module_info]: https://raw.githubusercontent.com/mekhalleh/cloud_lookup/master/pictures/01-demo.png "Module: info"
[module_advanced]: https://raw.githubusercontent.com/mekhalleh/cloud_lookup/master/pictures/02-demo.png "Module: advanced"
[module_good]: https://raw.githubusercontent.com/mekhalleh/cloud_lookup/master/pictures/03-demo.png "Module: bypass is good"
[module_leak]: https://raw.githubusercontent.com/mekhalleh/cloud_lookup/master/pictures/04-demo.png "Module: IP adress leak"
