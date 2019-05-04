# rrss2imap

[![Built with cargo-make](https://sagiegurari.github.io/cargo-make/assets/badges/cargo-make.svg)](https://sagiegurari.github.io/cargo-make)

rrss2imap is a Rust reimplementation of the classical Python script [rss2imap](https://github.com/rcarmo/rss2imap)

Goals of this project include

* Having a reasonably performant implementation of rss2imap
* Learn Rust
* Explore parallel mechanism
* Maybe provide some kind of image embedding (DONE) with cache

## Getting Started

### As a user

* Download and install `rrss2imap` executable for your system (this doesn't work yet)
* Run `rrss2imap new` to create a feedfile. This ffed file will contain all the configuration, as well for 
imap server connection and for each feed configuration)

#### Feed configuration

A typical feedfile will look like this

```
{
  "settings": {
    "email": {
      "server": "the imap server of your mail provider",
      "user": "your imap user name",
      "password": "your imap user password",
      "secure": {
        "Yes": 993 // Set to "Yes" when using secured image
      }
    },
    // This config is to be used for each feed
    "config": {
        // This is the email address written in each mail sent. It can be different from the email user
        "email": "Nicolas Delsaux <nicolas.delsaux@gmx.fr>",
        // This is the imap folder in which mails will be written
        "folder": "RSS/rrss2imap"
        // Setting this to true will force rrss2imap to transform all images into
        // base64. This prevents images from beind downloaded (and is really cool when reading feeds from a smartphone)
        // But largely increase each mail size (which can be quite bothering)
        "inline_image_as_data": true
    }
  },
  "feeds": [
    {
      "url": "http://tontof.net/?rss",
      // This last updated is updated for each entry and should be enough to have rss items correctly read
      "last_updated": "2019-05-04T16:53:15",
      "config": {
          // each config element can be overwritten at the feed level
      }
    },
```

### As a developer
* clone this repository
* run `cargo run`

#### Prerequisites

You need a complete rust build chain

To perform a release, you'll also need

* [cargo make](https://github.com/sagiegurari/cargo-make#usage-predefined-flows)
* [cargo release](https://github.com/sunng87/cargo-release)
* [git journal](https://github.com/saschagrunert/git-journal)
* [cargo hublish](https://github.com/chasinglogic/cargo-hublish)

#### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```

And repeat

```
until finished
```

End with an example of getting some data out of the system or using it for a little demo

### Running the tests

Explain how to run the automated tests for this system

#### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

#### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

Take a look at Cargo dependencies

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/your/project/tags). 

## Authors

* **Nicolas Delsaux** - *Initial work* - [Riduidel](https://github.com/Riduidel)

See also the list of [contributors](https://github.com/Riduidel/rrss2imap/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* [Rui Carno](https://github.com/rcarmo) for Python implementation of [rss2imap](https://github.com/rcarmo/rss2imap)
* [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz) for [RSS](https://en.wikipedia.org/wiki/RSS) (and [rss2email](https://github.com/rss2email/rss2email))

