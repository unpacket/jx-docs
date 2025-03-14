---
date: 2019-08-22T13:59:53Z
title: "jx step report"
slug: jx_step_report
url: /commands/jx_step_report/
---
## jx step report

Creates a HTML report from junit files

### Synopsis

This step is used to generate an HTML report from *.junit.xml files created from running BDD tests.

```
jx step report [flags]
```

### Examples

```
  # Collect every *.junit.xml file from --in-dir, merge them, and store them in --out-dir with a file name --output-name and provide an HTML report title
  jx step report --in-dir /randomdir --out-dir /outdir --merge --output-name resulting_report.html --suite-name This_is_the_report_title
  
  # Collect every *.junit.xml file without defining --in-dir and use the value of $REPORTS_DIR , merge them, and store them in --out-dir with a file name --output-name
  jx step report --out-dir /outdir --merge --output-name resulting_report.html
  
  # Select a single *.junit.xml file and create a report form it
  jx step report --in-dir /randomdir --out-dir /outdir --target-report test.junit.xml --output-name resulting_report.html
```

### Options

```
  -h, --help                   help for report
  -f, --in-dir string          The directory to get the reports from
  -m, --merge                  Whether or not to merge the report files in the "in-folder" to parse them and show it as a single test run
  -o, --out-dir string         The directory to store the resulting reports in
  -n, --output-name string     The result of parsing the report(s) in HTML format
  -s, --suite-name string      The name of the tests suite to be shown in the HTML report
  -t, --target-report string   The name of a single report file to parse
```

### Options inherited from parent commands

```
  -b, --batch-mode   Runs in batch mode without prompting for user input (default true)
      --verbose      Enables verbose output
```

### SEE ALSO

* [jx step](/commands/jx_step/)	 - pipeline steps

###### Auto generated by spf13/cobra on 22-Aug-2019
