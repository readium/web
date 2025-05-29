# 🌐 Readium Web

Readium Web is a toolkit for building Web Readers. It currently supports EPUB, with plans for PDF, audiobooks and comics/manga/webtoons in future revisions.

This repo is a work in progress, but it will host documentation and project management for the Readium Web project.

Readium Web is divided into two separate toolkits:

- the [TypeScript toolkit](https://github.com/readium/ts-toolkit)
- and the [Go toolkit](https://github.com/readium/go-toolkit)

## Why do we need two toolkits?

The TypeScript and Go toolkits are meant to be complementary rather than competing toolkits.

The primary use case of the `go-toolkit` in a Web Reader implementation is to:

* stream packaged resources (EPUB, CBZ)
* output a [Readium Web Publication Manifest](https://readium.org/webpub-manifest) for each of them over HTTPS
* along with various complementary API responses ([Positions List](https://readium.org/architecture/models/locators/positions/), [Guided Navigation](https://readium.org/guided-navigation))
* and stream individual resources of these publications over HTTPS


Whereas the primary use case of the `ts-toolkit` in a Web Reader implementation is to:

* interact with a [Readium Web Publication Manifest](https://readium.org/webpub-manifest) and related APIs
* provide various navigators to handle various publication types (reflowable publications and fixed layout for now)
* along with the lower level API associated to these navigators (for example the [Preferences API](https://readium.org/architecture/proposals/009-preferences-api.html) or [Decorator API](https://readium.org/architecture/proposals/008-decorator-api.html))

We could say that the `go-toolkit` turns a publication into an API, whereas the `ts-toolkit` is the engine of a Web Reader.

## Thorium Web and the Readium CLI

In addition to these toolkits, implementers can also build their projects directly on top of [Thorium Web](https://github.com/edrlab/thorium-web) and the [Readium CLI](https://github.com/readium/cli).

Thorium Web is an open-licensed Web Reader that's built on top of the TypeScript toolkit, providing UI components and all of the features that you would expect from a reading app.

The Readium CLI can stream EPUB publications over HTTP/HTTPS or connect to a storage such as S3, GCS or the local filesystem of a server.

We recommand looking into both projects as your default options when deploying a Web Reader.

## Readium Playground

[Readium Playground](https://github.com/readium/playground) is a reference implementation of Thorium Web.

A demo is available at <https://playground.readium.org> to play with the capabilities of Readium Web and Thorium Web. Unlike a vanilla version of Thorium Web, it also provides various affordances meant to illustrate how implementers can customize the behaviour of a Web Reader.

## License

Readium Web is published under a [BSD-3 license](https://github.com/readium/web/blob/main/LICENSE).

```
BSD 3-Clause License

Copyright (c) 2021, Readium Foundation

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this
   list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice,
   this list of conditions and the following disclaimer in the documentation
   and/or other materials provided with the distribution.

3. Neither the name of the copyright holder nor the names of its
   contributors may be used to endorse or promote products derived from
   this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
```
