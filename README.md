[![Ghostery](https://www.ghostery.com/wp-content/themes/ghostery/images/ghostery_logo_black.svg)](https://www.ghostery.com)
---

This is a modified version of the popular Ghostery browser extensions (Chrome/Firefox/Opera/Edge), that helps you browse smarter by giving you control over ads and tracking technologies to speed up page loads, eliminate clutter, and protect your data.

Ghostery helps you browse smarter by giving you control over ads and tracking technologies to speed up page loads, eliminate clutter, and protect your data. This is the unified code repository for the Ghostery browser extensions in Chrome, Firefox, Opera and Edge.

## Build instructions

#### Install yarn
**https://yarnpkg.com/en/docs/install**

#### Install local npm packages
```sh
$ yarn install --frozen-lockfile
```

## Build variants
```sh
# Build all sources
$ yarn run build.dev
```

```sh
# Build for production
$ yarn run build.prod
```

```sh
# Build and watch for changes
$ yarn run build.watch
```

## Enable Debugging / Logging
```javascript
// In manifest.json set
"debug": true,
"log": true,
```

## Testing and Linting
```sh
# Run unit tests
$ yarn run test.unit
```

```sh
# Run linter over the ./app and ./src folders
$ yarn run lint
```

```sh
# Lint a specific file
$ yarn run lint.raw -- src/utils/matcher.js
```

```sh
# Disable lint
$ NO_LINT=true yarn run build.dev
```

## Cliqz Source Code
Ghostery implements the following open-source products from [Cliqz](https://cliqz.com/en/)

[**Human Web**](https://cliqz.com/en/whycliqz/human-web)
+ [How it works](https://cliqz.com/en/magazine/techblog-human-web-reliably-removes-uids)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/human-web/)

[**Anti-Tracking**](https://cliqz.com/en/whycliqz/anti-tracking)
+ [How it works](https://cliqz.com/en/magazine/how-we-at-cliqz-protect-users-from-web-tracking)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/antitracking)

[**Ad Blocker**](https://cliqz.com/en/whycliqz/adblocking)
+ [GitHub](https://github.com/cliqz-oss/adblocker)

[**MyOffrz**](https://cliqz.com/en/cliqz-angebote)
+ [GitHub](https://github.com/cliqz-oss/browser-core/blob/master/modules/offers-v2)

### Building Cliqz Modules for Ghostery
Cliqz modules are pre-built and included under the `browser-core` NPM dependency in [package.json](package.json). To reproduce this build process, grab the appropriate Ghostery release (v7.x.x) from the [browser-core](https://github.com/cliqz-oss/browser-core/releases) project.

```sh
$ npm install
$ ./fern.js build configs/ghostery.js --no-maps --environment=production
$ ./fern.js pack configs/ghostery.js
```

## Compatibility

+ Firefox: 52+
+ Firefox Android: 55+
+ Chrome: 58+
+ Opera: 45+
+ Edge: 34.14291+

## License
[MPL-2.0](https://www.mozilla.org/en-US/MPL/2.0/) Copyright 2019 Ghostery, Inc. All rights reserved.

See [LICENSE](LICENSE)

## Tracker Databases
The [databases](/databases) folder contains JSON skeletons to show the schema expected by the extension pattern [matcher](/src/utils/matcher.js). See the [Database README](/databases/README.md) for more information.
Ghostery's production tracker databases have been purposely excluded from this project, as they remain proprietary to Ghostery, Inc. Which leads us to this grim, yet obligatory...

**Copyright Notice**

The proprietary databases are the intellectual property of Ghostery, Inc. and are protected by copyright and other applicable laws. All rights to them are expressly reserved by Ghostery, Inc. You may not use these databases or any portion thereof for any purpose that is not expressly granted in writing by Ghostery, Inc. All inquires should be sent to [legal@ghostery.com](legal@ghostery.com).  Ghostery, Inc. retains the sole discretion in determining whether or not to grant permission to use the databases. Unauthorized use of the databases, or any portion of them, will cause irreparable harm to Ghostery, Inc. and may result in legal proceedings against you, seeking monetary damages and an injunction against you, including the payment of legal fees and costs.

[![Ghostery](https://www.ghostery.com/wp-content/themes/ghostery/images/github/ghosty_coder.jpg)](https://www.ghostery.com)
