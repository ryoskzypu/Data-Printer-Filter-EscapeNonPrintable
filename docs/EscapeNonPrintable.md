# NAME

Data::Printer::Filter::EscapeNonPrintable - escape missing ASCII nonprintable characters

# SYNOPSIS

In your `.dataprinter`:

```perl
print_escapes = 1
filters       = EscapeNonPrintable
```

Alternatively:

```perl
use DDP print_escapes => 1, filters => ['EscapeNonPrintable'];
```

# DESCRIPTION

This module is a filter plugin for [Data::Printer](https://metacpan.org/pod/Data%3A%3APrinter).

## Rationale

Since [DDP](https://metacpan.org/pod/DDP) does not escape all ASCII control chars in [print\_escapes](https://metacpan.org/pod/Data%3A%3APrinter%3A%3AObject#print_escapes),
this filter escapes them to octal notation. Vertical tab (`\x0b`) and DEL (`\x7f`)
chars are also missed, thus escaped.

All the missing chars are colorized to their `escaped` [color theme](https://metacpan.org/pod/Data%3A%3APrinter%3A%3ATheme).

Note that this is a hack; the proper way to fix this should be to patch DDP.

See:

- [https://github.com/garu/Data-Printer/issues/184](https://github.com/garu/Data-Printer/issues/184)
- [https://github.com/garu/Data-Printer/pull/101](https://github.com/garu/Data-Printer/pull/101)
- [https://github.com/garu/Data-Printer/pull/201](https://github.com/garu/Data-Printer/pull/201)

# DECORATING

To call this filter and process its result from another filter, you can use:

```perl
my $str = Data::Printer::Filter::EscapeNonPrintable::parse( $ref, $ddp );
```

Note that the loading order of filters matters, so ensure the caller is the last one in the chain.

# BUGS

Report bugs at [https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/issues](https://github.com/ryoskzypu/Data-Printer-Filter-EscapeNonPrintable/issues).

# AUTHOR

ryoskzypu <ryoskzypu@proton.me>

# SEE ALSO

- [Data::Printer](https://metacpan.org/pod/Data%3A%3APrinter)
- [Data::Printer::Filter](https://metacpan.org/pod/Data%3A%3APrinter%3A%3AFilter)
- [ascii(7)](http://man.he.net/man7/ascii)
- [https://en.wikipedia.org/wiki/C0\_and\_C1\_control\_codes](https://en.wikipedia.org/wiki/C0_and_C1_control_codes)
- [https://en.wikipedia.org/wiki/Escape\_sequences\_in\_C](https://en.wikipedia.org/wiki/Escape_sequences_in_C)

# COPYRIGHT

Copyright © 2026 ryoskzypu

MIT-0 License. See LICENSE for details.
