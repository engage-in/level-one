---
title: "My Fifth Post"
date: 2024-07-24T22:58:28+08:00
draft: false
toc: false
images:
tags:
  - untagged
---

* Test Code block

Signing a JWT, implemented in Perl5
```perl
#!/usr/bin/env perl
use Modern::Perl;
use Crypt::JWT qw/encode_jwt decode_jwt/;
use Crypt::PK::RSA;
use Data::Dumper;

my $encrypted = shift;
$encrypted = <STDIN> if !defined($encrypted);
die "no jwt given" if !defined($encrypted);
chomp($encrypted);

my $pub_key_file = "account.pub.pem";
my $pub_key = Crypt::PK::RSA->new($pub_key_file);
my $data = decode_jwt(token => $encrypted, key => $pub_key);
say Dumper \$data;
```
