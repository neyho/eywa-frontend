# EYWA Frontend

This repo contains **free and not** opensourced EYWA frontend. Repo can be cloned and served with
EYWA Core by specifying

```
EYWA_SERVE
```
directory. I.E.
```
# Create directory that will be served with EYWA
cd ~/.eywa/
mkdir web
cd web

# Clone eywa frontend. It is important that it is cloned in eywa folder
git clone https://github.com/neyho/eywa-frontend.git eywa

# Export environment variable
export EYWA_SERVE=$HOME/.eywa/web

# Start EYWA
eywa core start
```

### Try it out

Navigate to http://localhost:8080

Also keep in mind that initialized EYWA Core
will allow only EYWA Client (this frontend client) redirects
to https://my.eywaonline.com.

If you want to allow ```http://localhost:8080``` or any other domain,
You will have to modify EYWA Frontend client through ```my.eywaonline.com```
and add redirects
```
# Login redirection
http://localhost:8080/eywa/callback

# Logout redirection
http://localhost:8080/eywa
```

**OR**

Use script to modify EYWA Frontend client. Checkout [Examples](https://github.com/neyho/eywa-examples)
to see how to connect to EYWA through cli and how to run scripts.

## 🚨 Important
EYWA frontend client uses _react-oidc-context_ library to authenticate user. _react-oidc-context_
doesn't allow http OIDC endpoints as OIDC specification explicitly requires TLS. Only ```http://localhost```
and ```http://127.0.0.1``` are allowed.
