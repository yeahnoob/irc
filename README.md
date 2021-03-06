# irc [![Build Status](https://travis-ci.org/aatxe/irc.svg?branch=master)](https://travis-ci.org/aatxe/irc) #
A thread-safe IRC library in Rust. The client portion is compliant with 
[RFC 2812](http://tools.ietf.org/html/rfc2812) and includes some additional, common features. The 
server portion is still a work in progress. You can find up-to-date, ready-to-use documentation 
online [here](http://aatxe.github.io/irc/irc/). The documentation is generated with the 
default features. These are, however, strictly optional and can be disabled accordingly. 

## Getting Started ##

To start using this library with cargo, you can simply add `irc = "*"` to your dependencies to your
Cargo.toml file. You'll likely want to take a look at some of the examples, as well as the 
documentation. You'll also be able to find a small template to get a feel for the library.

## Getting Started with Bots ##

```rust
extern crate irc;

use irc::client::server::{IrcServer, Server};
use irc::client::server::utils::Wrapper;

fn main() {
    let irc_server = IrcServer::new("config.json").unwrap();
    let server = Wrapper::new(&irc_server);
    server.identify().unwrap();
    for message in server.iter() {
        // Do message processing.
    }
}
```

## Contributing ##
Contributions to this library would be immensely appreciated. As this project is public domain, 
all prospective contributors must 
[sign the Contributor License Agreement](https://www.clahub.com/agreements/aatxe/irc), a 
public domain dedication.
