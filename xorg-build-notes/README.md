# Build notes for X.Org

## Steps for connecting to #xorg-devel IRC: [Freenode registration steps](https://freenode.net/kb/answer/registration)

1. Register nickname by sending this message on IRC: /msg NickServ REGISTER password youremail@example.com

Note: Registration is one time. The nickname may expire after long time of no use.

2. Identify your nickname by sending this message on IRC: /msg NickServ IDENTIFY foo password

3. In case you forgot password, to reset your password send this message on IRC: /msg NickServ SENDPASS nickname

## Names of packages in Fedora (to that of mentioned in the website)

Package name on xorg build page | Package name in Fedora
--- | --- 
gmake | make
pkg-config | pkgconf-pkg-config
yacc | bison
lex | flex
libgbm | gbm
libmtdev | mtdev
libudev | udev
libcrpto | openssl
libmd | gromacs
xsltproc | libxslt

## Problems I faced while building [X.Org](https://www.x.org/wiki/Building_the_X_Window_System/)

- Bug in automake makes build throw this error: 

```bash
Unescaped left brace in regex is illegal here in regex; marked by <-- HERE in m/\${ <-- HERE ([^ \t=:+{}]+)}/ at /usr/local/bin/automake-1.11 line 4159.
```
Solution: [Patch for the bug](https://aur.archlinux.org/cgit/aur.git/tree/perl2.6.patch?h=automake-1.11)

- Error while building of docs/xorg-docs: [Pastebin link is here](https://pastebin.com/37Q29cat)

Solution: 

- libsha1 package is not installed on my machine. Its alternative mentioned in libsilc but I am unable to install it from the package manager. Package manager says package not found. 

Solution: 
