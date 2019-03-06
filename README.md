PanopticFilter
====

PanopticFilter is a anomaly log monitoring tool, designed as Fluentd out_exec filter.

## Requirement

* Perl (> 5.20)
  * Regexp::Assemble

## SYNOPSIS

`panopticfilter <SUBCOMMAND> [OPTIONS]`

SUBCOMMAND is one of following:
<dl>
<dt> build
<dd>  Build a pattern file by specified rules from sample logs.
<dt> run
<dd>  Monitor anomaly logs from STDIN plain text.
<dt> filter
<dd>  Monitor anomaly logs from STDIN JSON text.
<dt> strip
<dd>  Strip redundant sample logs from STDIN plain text.
<dt> multiline2singleline
<dd>  Transform multi-line logs to single-line logs.
<dt> json2text
<dt> version
</dl>

## Description



## "build" Subcommand Options

<dl>
<dt> -r FILE
<dd>  rule file
<dt> -o FILE
<dd>  output pettern file
<dt> -s FILE
<dd>  input sample log file. You can specify multiple files.
<dt> -d FILE
<dd>  (optional) output diagnosis file
<dt> -e NAME
<dd>  (optional) event name. Default: 50WELKNOWN
</dl>

## "run" Subcommand Options
<dl>
<dt> -p FILE
<dd>  pettern file
</dl>

## "filter" Subcommand Options
<dl>
<dt> -p FILE
<dd>  pettern file
<dt> -e 's/x/y/'
<dd>  tag replacement rule.
<dt> -o FILE
<dd>  (optional) output anomaly log file
</dl>

## "strip" Subcommand Options
<dl>
<dt> -r FILE
<dd>  rule file
<dt> -p FILE
<dd>  (optional) pettern file
</dl>

## "multiline2singleline" Subcommand Options
<dl>
<dt> --firstline REGEXP
</dl>
 
## Licence

[MIT](https://github.com/frisky-gh/panopticfilter/blob/master/LICENSE)

## Author

[frisky-gh](https://github.com/frisky-gh)

