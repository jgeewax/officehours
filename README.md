Office Hours
============

What?
-----

I'm going to try using GitHub to track requests for "office hours".
This is just an experiment, so we'll have to see how it works out.

When is the next open day?
--------------------------

See https://github.com/jgeewax/officehours/blob/master/2014/

How do I make a request?
------------------------

In this repository, there is a Markdown file for the date
where I have open hours (ie, ``2014-01-01.md``).

It will have a table of appointment slots, so if you want one,
just send me a pull request for a commit that fills out
one of the rows.

How do I get notified when you're hosting more office hours?
------------------------------------------------------------

Easy, just "watch" the repository.

How do I cancel my office hour request?
---------------------------------------

Just submit another pull request removing yourself from the appointment.

What's the catch?
-----------------

I'm using GitHub to automatically favor technical people,
but I'm open to talk to anyone about anything.

That said, I need a way of prioritizing requests
so the following things will bump you up in priority:

1. A link to a demo (even if it's just mockups)
1. If your GitHub account is really active
1. A digitally signed message (see below more for info)

Digitally signing?
------------------

You'll need a private key (easiest if it's in PEM format),
and you'll need to share the public key.

**How I'm going to verify your signature**

    $ openssl dgst -verify your-public-key.pub -signature your-file.sig -sha512 your-file
    Verified OK

Note that this means I need

1. Your original file
1. Your signature of the file
1. Your public key

so include all of these in the pull request in a directory named with your username
(see https://github.com/jgeewax/officehours/blob/master/requests/ for an example).

I also recommend that you test verifying before sending your pull request.

**How you should sign your file**

    $ openssl dgst -sign your-private-key.pem -out your-file.sig -sha512 your-file

**How you can generate a private key**

    $ openssl genrsa -out your-key.pem 2048

**How you get the public key from the private key**

    $ openssl pkey -in your-private-key.pem -pubout -out your-public-key.pub
