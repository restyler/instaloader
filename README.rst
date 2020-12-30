


Instaloader (proxified version)
#################

This repo contains RapidApi proxified version of Instagram downloader https://github.com/instaloader/instaloader due to difficulties with bypassing Instagram firewalls from regular data center ip ranges.
This version solves "429 - Too many requests" rate limit errors of basic version of the downloader.

Should be used (and was tested) for public profiles download.
This version requires API key for proxies, get it here: https://rapidapi.com/restyler/api/instagram40 

Sample screenshot with unsuccessful and successful download of public profile:
***************

.. image:: https://user-images.githubusercontent.com/775507/103315213-6baf2400-4a3e-11eb-91aa-81a062966266.png


Usage:
***************
Make sure you've removed all previous versions of instaloader (``pip3 uninstall instaloader``) to avoid conflicts.

    $ pip3 install git+https://github.com/restyler/instaloader.git

    $ instaloader username1 [username2 ...] --rapidapi-key=[YOUR-SECRET-KEY]

If ``--rapidapi-key`` arg is not specified - the loader behaves like the basic version of the script, with direct connection to Instagram.


- downloads **public and private profiles, hashtags, user stories,
  feeds and saved media**,

- downloads **comments, geotags and captions** of each post,

- automatically **detects profile name changes** and renames the target
  directory accordingly,

- allows **fine-grained customization** of filters and where to store
  downloaded media,

- automatically **resumes previously-interrupted** download iterations.

::

    instaloader [--comments] [--geotags]
                [--stories] [--highlights] [--tagged] [--igtv]
                [--login YOUR-USERNAME] [--fast-update]
                profile | "#hashtag" | :stories | :feed | :saved

`Instaloader Documentation <https://instaloader.github.io/>`__


How to Automatically Download Pictures from Instagram
-----------------------------------------------------

To **download all pictures and videos of a profile**, as well as the
**profile picture**, do

::

    instaloader profile [profile ...] --rapidapi-key=[YOUR-SECRET-KEY]

where ``profile`` is the name of a profile you want to download. Instead
of only one profile, you may also specify a list of profiles.

To later **update your local copy** of that profiles, you may run

::

    instaloader --fast-update profile [profile ...] --rapidapi-key=[YOUR-SECRET-KEY]

If ``--fast-update`` is given, Instaloader stops when arriving at the
first already-downloaded picture. When updating profiles, Instaloader
automatically **detects profile name changes** and renames the target directory
accordingly.

Instaloader can also be used to **download private profiles**. To do so,
invoke it with

::

    instaloader --login=your_username profile [profile ...] --rapidapi-key=[YOUR-SECRET-KEY]

When logging in, Instaloader **stores the session cookies** in a file in your
temporary directory, which will be reused later the next time ``--login``
is given.  So you can download private profiles **non-interactively** when you
already have a valid session cookie file.

`Instaloader Documentation <https://instaloader.github.io/basic-usage.html>`__


Disclaimer
----------

.. disclaimer-start

Instaloader is in no way affiliated with, authorized, maintained or endorsed by Instagram or any of its affiliates or
subsidiaries. This is an independent and unofficial project. Use at your own risk.

Instaloader is licensed under an MIT license. Refer to ``LICENSE`` file for more information.

.. disclaimer-end

Contributing
------------

As an open source project, Instaloader heavily depends on the contributions from
its community. See
`contributing <https://instaloader.github.io/contributing.html>`__
for how you may help Instaloader to become an even greater tool.

It is a pleasure for us to share our Instaloader to the world, and we are proud
to have attracted such an active and motivating community, with so many users
who share their suggestions and ideas with us. Buying a community-sponsored beer
or coffee from time to time is very likely to further raise our passion for the
development of Instaloader.

| For Donations, we provide a PayPal.Me link and a Bitcoin address.
|  PayPal: `PayPal.me/aandergr <https://www.paypal.me/aandergr>`__
|  BTC: 1Nst4LoadeYzrKjJ1DX9CpbLXBYE9RKLwY
