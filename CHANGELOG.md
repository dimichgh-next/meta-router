Changelog
=========

# 2.x

## 2.1.x

### 2.1.0

- Fixes [#7](https://github.com/patrick-steele-idem/meta-router/issues/7) - Allow route metadata to be attached to route handler function:

```javascript
function userHandler(req, res, next) {
    // ...
}

userHandler.routeMeta = {
    security: {
        authenticationRequired: true,
        redirect: true
    }
}

// You can also optionally attach middleware to the route:
userHandler.routeMiddleware = [
    function (req, res, next) {
        // ...
    },
    // ...
]

module.exports = userHandler;
```

- Introduced new shorthand syntax for declaring routes in JSON:

```json
[

    "GET /users/:user => ./user",
    "GET /login => ./user#login",
    "GET /logout => ./user#logout",
    "POST /users/:user/picture => ./user#uploadPicture"
]
```