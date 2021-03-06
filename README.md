[Cozy][cozy] Dummy
=======================================

What's Cozy?
------------

![Cozy Logo](https://cdn.rawgit.com/cozy/cozy-guidelines/master/templates/cozy_logo_small.svg)

[Cozy] is a platform that brings all your web services in the same private space. With it, your webapps and your devices can share data easily, providing you with a new experience. You can install Cozy on your own hardware where no one's tracking you.

What's Dummy?
--------------

Dummy is a konnector used for development, debugging and test purpose. It is used to test error from the connector to the [Home][].


Build
-------

Build locally all flavours
```bash
yarn build
```

Deploy flavours on their respective branch
```bash
yarn deploy
```


Install
-------

Since `dummy` is only for development purposes, it must not be available in the Cozy store and as such is only published
on GitHub and on the registry in the dev channel. Travis automatically updates those branches and the registry when a
change lands on master.

### Flavors

- `build`: Dummy connector
- `build_aggregator`: Used to test the aggregator account feature used in
  Banking konnectors
- `build_form`: Used to test various form elements used in the authentication
  form
- `build_oauth`: Used to test oauth flow. Real example :
  [Facebook](https://github.com/konnectors/cozy-konnector-facebook/). See
  specific [README](./flavours/oauth/README.md) for more information.
- `build_twofa`: Used to test 2FA flow for example for the
  [Amazon](https://github.com/konnectors/amazon) connector

Each of this flavor is published on a build branch, for example [here](https://github.com/konnectors/dummy/tree/build_twofa).

Here is the install command for each flavor:

```bash
# Install the build flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build

# Install the build_aggregator flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build_aggregator

# Install the build_bank flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build_bank

# Install the build_form flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build_form

# Install the build_oauth flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build_oauth

# Install the build_twofa flavour
cozy-stack konnectors install dummy git://github.com/konnectors/dummy.git#build_twofa
```

Additionally, the 2FA flavor is published in the registry at `registry://dummy/dev`. It can be useful for flows
where it is not suitable to install the connector via the CLI. (This need double check)

```bash
cozy-stack konnectors install dummy registry://dummy/dev
```

[cozy]: https://cozy.io "Cozy Cloud"
[Home]: https://github.com/cozy/cozy-home
