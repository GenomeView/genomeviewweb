# Setting up authentication and encryption

## Authentication
GenomeView supports BasicAuth for webservers

To create pasword files you can use htpasswd:
http://httpd.apache.org/docs/2.0/programs/htpasswd.html
```
 htpasswd -c /location/of/.htpasswd username
```

Explanation how to setup .htaccess to a folder:
http://httpd.apache.org/docs/2.2/howto/htaccess.html#auth
```
 AuthUserFile /location/of/.htpasswd
 AuthType Basic
 AuthName “My Files"
 Require valid-user
```




Important is that you put the password file outside the document root that is accessible through the web.

That should get you up and running.

## Encryption
GenomeView support SSL encrypted connections. It will use the certificate that is presented, but it will not verify the integrity of the key-chain.

