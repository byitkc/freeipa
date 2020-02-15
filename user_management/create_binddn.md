# Creating a Bind DN for use with LDAP Integrated Tools

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