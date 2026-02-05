[![CI](https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/actions/workflows/ci.yml/badge.svg?branch=main&event=push)](https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/actions/workflows/ci.yml)
[![Coverage Status](https://coveralls.io/repos/github/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/badge.svg?branch=main)](https://coveralls.io/github/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable?branch=main)

# Data::Printer::Filter::EscapeNonPrintable

This module is a filter plugin for [Data::Printer](https://metacpan.org/pod/Data::Printer).

## Rationale

Since [DDP](https://metacpan.org/pod/DDP) does not escape all ASCII control chars
in [print_escapes](https://metacpan.org/pod/Data::Printer::Object#print_escapes),
this filter escapes them to octal notation. Vertical tab (`\x0b`) and DEL (`\x7f`)
chars are also missed, thus escaped.

All the missing chars are colorized to their `escaped` [color theme](https://metacpan.org/pod/Data::Printer::Theme).

Note that this is a hack; the proper way to fix this should be to patch DDP.

See:

- https://github.com/garu/Data-Printer/issues/184
- https://github.com/garu/Data-Printer/pull/101
- https://github.com/garu/Data-Printer/pull/201

## Installation

To download and install this module directly with [cpanminus](https://metacpan.org/pod/App::cpanminus):

```shell
$ cpanm https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable.git
```

To do it manually, run the following commands (after cloning the repository):

```shell
$ cd Data-Printer-Filter-EscapeNonPrintable
$ perl Makefile.PL
$ make
$ make test
$ make install
```

## Support and documentation

You can find documentation for this module in [docs](docs/) or with the
`perldoc` command (after installing):

```shell
$ perldoc Data::Printer::Filter::EscapeNonPrintable
```

You can also look for information at:

- GitHub issue tracker (report bugs here)

    https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/issues

- Search CPAN

    https://metacpan.org/dist/Data-Printer-Filter-EscapeNonPrintable

## Copyright

Copyright © 2026 ryoskzypu

MIT-0 License. See LICENSE for details.
