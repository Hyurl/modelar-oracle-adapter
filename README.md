# Modelar-Oracle-Adapter

**This is an adapter for [Modelar](http://modelar.hyurl.com) to connect**
**Oracle database.**

## Install

```sh
npm install modelar-oracle-adapter
```

## How To Use

```javascript
const { DB } = require("modelar");
const OracleAdapter = require("modelar-oracle-adapter");

DB.setAdapter("oracle", OracleAdapter).init({
    type: "oracle",
    database: "XE",
    host: "127.0.0.1",
    port: 1521,
    user: "SYSTEM",
    password: "******"
});
```

## Warning

Since `node-oracledb` requires some prerequisites before installing, you must 
prepare you machine as its
[documentation](https://github.com/oracle/node-oracledb/blob/master/INSTALL.md)
says. You could try to install it before installing `modelar-oracle-adapter`, 
that guarantees successful installation.

Oracle database transfers identifiers to UPPER-CASE by default, but with this 
adapter, they will keep the form of which they're defined.

If you want to use full features of modelar with this adapter, you must set an
`id` field for every table as its primary key.