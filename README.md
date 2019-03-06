PanopticFilter
====

PanopticFilter is a anomaly log monitoring tool, designed as Fluentd out_exec filter.

## Requirement

* Perl (> 5.20)
  * Regexp::Assemble

## SYNOPSIS

`panopticfilter <SUBCOMMAND> [OPTIONS]

SUBCOMMAND is one of following:
  * build
      Build a pattern file by specified rules from sample logs.
  * run
      Monitor anomaly logs from STDIN plain text.
  * filter
      Monitor anomaly logs from STDIN JSON text.
  * strip
      Strip redundant sample logs from STDIN plain text.
  * multiline2singleline
      Transform multi-line logs to single-line logs.
  * json2text
  * version

## Description



## "build" Subcommand Options
  * -r FILE
     rule file
  * -o FILE
     output pettern file
  * -s FILE
     input sample log file. You can specify multiple files.
  * -d FILE
     (optional) output diagnosis file
  * -e NAME
     (optional) event name. Default: 50WELKNOWN

## "run" Subcommand Options
  * -p FILE
     pettern file

## "filter" Subcommand Options
  * -p FILE
     pettern file
  * -e 's/x/y/'
     tag replacement rule.
  * -o FILE
     (optional) output anomaly log file

## "strip" Subcommand Options
  * -r FILE
     rule file
  * -p FILE
     (optional) pettern file

## "multiline2singleline" Subcommand Options
  * --firstline REGEXP

## Install

1. clone or unzip.

```
    % git clone https://github.com/frisky-gh/panopticd.git
```

2. setup rsyslog, syslog-ng or other logger to output logs
   into ./panopticd/spool/targetlog/ .

```
    ex) rsyslog.conf
    $FileCreateMode 0644
    $template SyslogDaily,"/home/frisky/panopticd/spool/targetlog/syslog_%$year%-%$month%-%$day%"
    *.* ?SyslogDaily
```

3. complete.

## Usage

1. copy well-known syslogs to ./panopticd/conf/pattern/ as sample.

```
    % cp ./syslog.1 ./panopticd/conf/pattern/syslog-wellknown.samplelog
```

2. build patterns and patternsets from sample logs.

```
    % ./panopticd/bin/panopticctl build
```

3. copy conf files from examples and configurate it.

```
    % cd ./panopticd/conf
    % cp delivery.conf.example delivery.conf
    % vi delivery.conf
    % cp generate_pattern.conf.example generate_pattern.conf
    % vi generate_pattern.conf
    (continue...)
```

4. startup panopticd.

```
    % ./panopticd/bin/panopticd start
```

## Licence

[MIT](https://github.com/frisky-gh/panopticfilter/blob/master/LICENSE)

## Author

[frisky-gh](https://github.com/frisky-gh)

