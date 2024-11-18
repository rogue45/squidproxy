# squidproxy
docker setup for squid proxy


version: "3"
services:
  proxy:
    image: ubuntu/squid
    environment:
      TZ: UTC
    ports:
      - "3128:3128"
    volumes:
      - ./clean_squid.conf:/etc/squid/squid.conf
      - ./squid_password:/etc/squid/squid_password
    restart: always

# To install apache2-utils in order to add user/password for basic and ntlm auth
# apt update
# apt install apache2-utils
# htpasswd -c /etc/squid/squid_password tester
# add your pw and confirm (password1)

# test it by entering: /usr/lib/squid/basic_ncsa_auth /etc/squid/squid_password
# then enter <username> <password> and you should get an OK validating your file is g2g


# https://simplificandoredes.com/en/squid-user-authentication/



# service squid restart


