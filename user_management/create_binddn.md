# Creating a Bind DN for use with LDAP Integrated Tools

## Summary

There are instances where there are LDAP integrated systems that require us to use a Bind DN to authenticate against LDAP and query LDAP. We can easily create Bind DN's as Service Accounts using the following setup.

## Create a file with the details of our user

```
dn: uid=foreman,cn=users,cn=accounts,dc=home,dc=byitkc,dc=com
add:objectclass:account
add:objectclass:simplesecurityobject
add:uid:foreman
add:userPassword:averysecurepassword
add:passwordExpirationTime:20380119031407Z
add:nsIdleTimeout:0
```

The ```add:passwordExpirationTime``` line above is OPTIONAL

## Run the LDAP Updater against the file

```ipa-ldap-updater ./file.update```