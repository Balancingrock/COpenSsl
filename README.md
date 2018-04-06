# COpenSsl
A module wrapper for the openSSL library for use by the Swift Package Manager (SPM).

COpenSsl is part of the [Swiftfire](http://swiftfire.nl) webserver project:

##### [SwifterSockets](https://github.com/Swiftrien/SwifterSockets)

Basic POSIX sockets utilities.

##### [SecureSockets](https://github.com/Swiftrien/SecureSockets)

A Swift wrapper around openSSL to provide secure connections. Builds on top of SwifterSockets.

##### [Swiftfire](https://github.com/Swiftrien/Swiftfire)

An open source web server in Swift.

##### [SwifterLog](https://github.com/Swiftrien/SwifterLog)

General purpose logging utility.

##### [SwifterJSON](https://github.com/Swiftrien/SwifterJSON)

General purpose JSON framework.

# OpenSSL

OpenSSL is available from [https://openssl.org](https://openssl.org)

To use this wrapper, openSSL must be installed on your system. This wrapper assumes that openSSL is installed in the default location _/usr/local_.

# Install

Install this as an SPM package with:
    
    $ git clone https://github.com/Balancingrock/COpenSsl
    $

To install openSSL on your system, please see [SecureSockets](https://github.com/Balancingrock/SecureSockets).

# Usage

Use this wrapper by creating a SPM dependency as follows:

    ...
       dependencies: [
           .Package(url: "https://github.com/Balancingrock/COpenSSL", "0.1.0"),
           ....
       ]

Keep in mind that openSSL must be installed for this wrapper to become usefull.

# Version history

Note: Planned releases are for information only, they are subject to change without notice.

#### v1.1.0 (Open)

- No new features planned. Features and bugfixes will be made on an ad-hoc basis as needed to support Swiftfire development.
- For feature requests and bugfixes please contact rien@balancingrock.nl

#### v1.0.0 (Planned)

- The current verion will be upgraded to 1.0.0 status when the full set necessary for Swiftfire 1.0.0 has been completed.

#### v0.2.0 (Current)

- Added xcode project for dummy framework.

#### v0.1.0

- Initial release
