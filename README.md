# COpenSsl

A module wrapper for the openSSL library for use by the Swift Package Manager (SPM).

COpenSsl is part of the [Swiftfire](http://swiftfire.nl) webserver project.

# OpenSSL

OpenSSL is available from [https://openssl.org](https://openssl.org)

To use this wrapper, openSSL must be installed on your system. This wrapper assumes that openSSL is installed parralel to the top level directory of COpenSSL.

Like this:

    ~/Documents/Projects/openssl
    ~/Documents/Projects/COpenSSL

# Install

Copy this as an SPM package with:
    
    $ git clone https://github.com/Balancingrock/COpenSsl


To install openSSL on your system, please see [SecureSockets](https://github.com/Balancingrock/SecureSockets).

# Usage

Use this wrapper by creating a SPM dependency as follows:

    ...
       dependencies: [
       .Package(url: "https://github.com/Balancingrock/COpenSSL", Version(0, 6, 0)),
           ....
       ]

Keep in mind that openSSL must be installed for this wrapper to become usefull.

## SPM

To use this package as is:

- the openSSL libraries and include files must be installed as described in the section "Install".
- the executable must be instructed where to find the libraries: `$ swift build -Xlinker -L/../openssl/lib` (assuming the executable project is also parallel to the openSSL and COpenSSL projects)

If another location for openSSL is used, clone the project and link the cloned project. Make sure to update the `module.modulemap` to refer to the proper location for openSSL. Since this is a specific copy for your use only, you can also specify the complete filepath.

Alternative: Use pkgConfig

- using pkgConfig make sure you are using the correct version of the openSSL libraries and headers: `$ pkg-config --libs openssl`
- in the file `Package.swift` add the line `pkgConfig: "openssl"` so that the package manifest reads like:

~~~    
let package = Package(
    name: "COpenSsl",
    pkgConfig: "openssl"
)
~~~    
(beware the comma after the name spec)

## Xcode

To use this package as is under Xcode the above also applies, however the executable should now also know where to find the openSSL libraries and include files. This can be done under:

`<project-name> -> <target-name> -> Build Settings -> Search Paths -> Header Search Paths & Library Search Paths`

and under

`<project-name> -> <target-name> -> Build Settings -> Linking -> Other Linker Flags -> "-L../openssl/lib -lssl -lcrypto"`

# Version history

Note: Planned releases are for information only, they are subject to change without notice.

#### v1.1.0 (Open)

- No new features planned. Features and bugfixes will be made on an ad-hoc basis as needed to support Swiftfire development.
- For feature requests and bugfixes please contact rien@balancingrock.nl

#### v1.0.0 (Planned)

- The current verion will be upgraded to 1.0.0 status when the full set necessary for Swiftfire 1.0.0 has been completed.

#### v0.6.0 (Current)

- Rewritten to minimalist version to avoid using the pkgConfig (which can point to the wrong openSSL version)

#### v.0.5.0

- keeping up with demands from swiftfire/ upgrading xcode verions etc.

#### v0.2.0

- Added xcode project for dummy framework.

#### v0.1.0

- Initial release
