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

## Readium Playground

The playground is a work in progress meant to illustrate the capabilities of Readium Web. In its current state, it provides a very basic vanilla reader that allows the user to navigate through publications.

Future work on this project will progressively bring it up to par with a reference implementation. Our current ETA for this work is to have something ready by the end of 2024.

- [Moby Dick](https://playground.readium.org/?book=https://publication-server.readium.org/bW9ieS1kaWNrLmVwdWI) (reflowable EPUB)
- [Bella the Dragon](https://playground.readium.org/?book=https://publication-server.readium.org/QmVsbGFPcmlnaW5hbDMuZXB1Yg) (fixed layout EPUB)

## Implementations

### De Marque

- [EPUB](https://r.cantook.com/cant/sample/aHR0cHM6Ly93d3cuY2FudG9vay5uZXQvc2FtcGxlLzUyODYyOTUvd2ViX3JlYWRlcl9tYW5pZmVzdD9mb3JtYXRfbmF0dXJlPWVwdWImc2lnaWQ9MTY4NzkyMzY5MiZzaWduYXR1cmU9NGM3YjA2YjYyMGE5ZWViNDdiYTliZTYyN2MzYjQ1MmJmNDc3ZWE1OTc0M2UwODJhOTAwMmExYTk5NDA2ODUxOA)
- [EPUB Fixed Layout](https://r.cantook.com/cant/sample/aHR0cHM6Ly93d3cuY2FudG9vay5uZXQvc2FtcGxlLzEwOTUwNTQwL3dlYl9yZWFkZXJfbWFuaWZlc3Q_Zm9ybWF0X25hdHVyZT1lcHViJnNpZ2lkPTE2ODc5MjM2OTImc2lnbmF0dXJlPTlmY2IyOWFmYjY2MGM0NDEzZmUwMmQ5ZGIyYTVkOTEyNTg1Yjc0OWE3Zjc4NTcwNGI2ZDEzMDExYzFiZjhlMmY)

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