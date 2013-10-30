# conneg tests

A collection of language-agnostic tests in JSON format for HTTP's content negotiation.


## Structure

Each type of content negotiation has its own JSON file:

- [type.json](type.json)
- [charset.json](charset.json)
- [encoding.json](encoding.json)
- [language.json](language.json)

Each JSON file is an array of test cases.

Each test case is structured as `[description, provided, accept, result]` for positive tests, or just `[description, provided, accepted]` for negative tests.

`provided` is a string looking similarly to an `Accept[-*]` header, but it only has media-types (not media-ranges). The weight of each media-type is to be read as a relative weight from the server's perspective. Respectively, when the weight is equal among media-types, the specificity of media-types is a second level relative weight, while the order is the third level relative weight.

`accept` is the `Accept[-*]` header as a string.

`result` is the item in `provided` (bit-to-bit equality including whitespace and weight) that is a best match for content negotiation.


## License

[Apache 2.0](LICENSE)
