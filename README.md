# EYWA Frontend

This repo contains **free and not opensourced** EYWA frontend. Repo can be cloned and served with
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


# Why not opensource?

### Timing Isn't Right
Our frontend codebase is currently around **30k lines of code**.
It’s an internal tool with limited documentation,
containing advanced concepts closely tied to **EYWA Core**, such as:

- **Modeling** - Not just ERD Data models
- **EYWA DB** -  which tracks differences between remote and 
local states while offering built-in operations like 
stack/slice/delete GraphQL mutations directly through client-side commits.

For a better development experience, these concepts need to be **isolated** and **well-documented**.
However, this requires significant effort and, at this point, we haven’t received
sufficient feedback indicating that this is a priority for the community.

If you find **EYWA** and its ecosystem relevant, we’d love your support!  
- **Star this repository** or [EYWA Core](https://github.com/neyho/eywa-core)
to show interest and help us prioritize.

For those looking to explore, [Toddler](https://github.com/gersak/toddler) is a great place to start!
