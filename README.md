# certdiff

Show the difference between 2 certificate files.

This code is licensed under the MIT license.

## Usage

    $ certdiff /path/to/file1.crt /path/to/file2.crt

## Output

Differences are highlighted using the `diff -y` output (side-by-side diff), output with the `|` character in between indicates differences between the files.

    $ ./certdiff cronweekly.com/cert.pem sysca.st/cert.pem
    subject= /CN=cronweekly.com                               |  subject= /CN=sysca.st
    issuer= /C=US/O=Let's Encrypt/CN=Let's Encrypt Authority     issuer= /C=US/O=Let's Encrypt/CN=Let's Encrypt Authority
    notBefore=Feb 15 08:48:00 2016 GMT                        |  notBefore=Feb 15 09:11:00 2016 GMT
    notAfter=May 15 08:48:00 2016 GMT                         |  notAfter=May 15 09:11:00 2016 GMT

If there are no differences, the tool will tell you.

    $ ./certdiff cronweekly.com/cert.pem othercert/cert.pem
    No differences, the data (FQDN, SAN, ...) is the same.
