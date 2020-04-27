# freezer

This is the repository to use with [`brrr`](https://github.com/SiegfriedEhret/brrr).

## Package definition

An example can help, right ?

```
name: "exa"
latest_version: 0.9.0
releases_feed: ""
url: "https://github.com/ogham/exa"
versions:
  "0.9.0":
    linux:
      symlinks:
          "exa-linux-x86_64": "exa"
      binary_type: "zip"
      hash_sha1: "a9a384d8e462a78af6dd14ad80cebc67e674100f"
      url: "https://github.com/ogham/exa/releases/download/v0.9.0/exa-linux-x86_64-0.9.0.zip"
    macos:
      symlinks:
          "exa-macos-x86_64": "exa"
      binary_type: "zip"
      hash_sha1: "9c21c7c4e4ba5dc8c29a5d883a80efebd17843dc"
      url: "https://github.com/ogham/exa/releases/download/v0.9.0/exa-macos-x86_64-0.9.0.zip"
```

A package is a yaml file with the following properties:

- `name` (`String`, mandatory): the name of the package.
- `latest_version` (`String`, mandatory): the latest available version (used later in `versions`).
- `releases_feed` (`String`, optional): the rss feed to get new versions information. Useful to update the content of this repository.
- `url` (`String`, mandatory): the url of the package repository.
- `versions` (`Hash(version: String, Hash(arch: String, version: Binary))`, mandatory): a map with versions as keys, and as value a map with architecture (`linux`, `macos`) as keys, and a Binary as value, see below.

A Binary has the following properties:

- `binary_type` (`String`, mandatory): the type of binary file. Supported values: `binary`, `tar`, `zip`.
- `url` (`String`, mandatory): the url of the binary to download.
- `symlinks` (`Hash(String, String)`, mandatory): the keys are path to executable files, values are the name of the symbolic links.
- `hash_<hash type>` (`String?`, optional): the hash for the file from the `url`. Supported values for `<hash type>` are: `md5`,`sha1`.

## Development

### Contributing

1. Fork it (<https://github.com/SiegfriedEhret/freezer/fork>)
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request

### Contributors

- [Siegfried Ehret](https://github.com/SiegfriedEhret) - creator and maintainer

### License

This library is distributed under the MIT license. Please see the [LICENSE](./LICENSE) file.