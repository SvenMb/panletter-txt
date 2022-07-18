# Writing Letters in markdown using pandoc and print on typewriter

This templates allow to print simple letters on a typewriter like that on my
[erika](https://git.muehlberg.net/SvenMb/erika) project. (on [github](https://github.com/SvenMb/erika))

This project is derived from [JensErat/pandoc-scrlttr2](https://github.com/JensErat/pandoc-scrlttr2)

Letters produced for his LaTeX/pdf-Template can be reused here (without any graphics etc)

## Installing the Template and 

To install the templates 'dinbrief.md' and 'dinover.md', either store it in 
the working directoryor move it to the template folder in Pandoc's data directory,
usually ~/.pandoc/templates. The wrapper script 'panletter' must be in a $PATH reachable
directory or you need to call it with path.

## using the wrapper script

simple call (assuming it is in PATH):

    panletter example-letter.md

This will create a file 'example-letter.txt' with your letter.

### Options

With parameter --colums you can adjust the line width of your typewriter.

    panletter --columns=66 example-letter.md

Parameter --page will paginate the output.

    panletter --page=45 example-letter.md

Adds number of page and formfeed after 44 lines (45 line is pagenumber)
If not given the output won't be paginated.

With Parameter --tab you can set to which tabstop the tab (^I) will expand.
This way you set the address and infos on the right side of the header inside
the DIN letter.

    panletter --tab=70 example-letter.md

Sets tabstop to the 70st col.

You can also set the output file.

    panletter --output=letter.txt example-letter.md

You can set both template files

    panletter --template=dinbrief.md --overlay=dinover.md
    
You can see some help and the defaults via

    panletter --help

## Templates

The templates are pandoc templates. The overlay template will be concatenated
to the main template on a line by line base (like unix paste -d ""). A tabs inside the template will be
expandet according to the '--tab' option.

see example why this is done this way and how to use it.

## Letter Metadata in a YAML Metadata Block

see [JensErat/pandoc-scrlttr2](https://github.com/JensErat/pandoc-scrlttr2)

currently used variables in the examples and to be set in the YAML field:
* to
* subject
* date
* today (set to current date)
* opening
* closing
* encl (enclosures)
* invoice
* invoicename
* myref
* myrefname
* yourref
* yourrefname

special variable which includes the letter text
* body

## Copyright

This template, forked from the [pandoc-templates] is dual-licensed, under both the GPL (v2 or higher, same as pandoc) and the BSD 3-clause license (included below).

----

Copyright (c) 2014, John MacFarlane

Copyright (c) 2014, Jens Erat

Copyright (c) 2022, Sven Mühlberg

All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are met:

    * Redistributions of source code must retain the above copyright
      notice, this list of conditions and the following disclaimer.

    * Redistributions in binary form must reproduce the above
      copyright notice, this list of conditions and the following
      disclaimer in the documentation and/or other materials provided
      with the distribution.

    * Neither the name of John MacFarlane nor the names of other
      contributors may be used to endorse or promote products derived
      from this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

