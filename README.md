# TidaLink
Standalone server for automatically syncing [TidalCycles](http://tidalcycles.org) and [Ableton Link](https://www.ableton.com/en/link/).

Quoting from:
http://lurk.org/r/post/7AM6Qt7DlvJtorbIuVLMFA

You'll need 'cmake' as well as a c++ compiler etc. If you're on a mac,
you will probably have to at least do this, which in turn requires
homebrew (get it from https://brew.sh/ if you don't already have it):

`brew install cmake`

Then install TidaLink with this:

```
mkdir src
cd src
git clone https://github.com/tidalcycles/TidaLink.git
cd TidaLink
/bin/bash compile.sh
```

To run TidaLink, do this:

```
cd build
./TidaLink
```

Restart your editor and run some tidal code. It should now be in
sync with any link compatible app that's running on the same network.
You might need to change the cps in TidaLink (with 'w' or 'e') or in
another link app before the sync kicks in.

You might also need to make a slight adjustment to get it bang on. You
can do this with the `nudger` function which isn't yet available in
atom. You can make it available with this command [add and evaluate this line in your tidal source file]:

```
(cps, nudger, getNow) <- cpsUtils'
```

then you can do slight adjustments with e.g.:

```
nudger (-0.02)
```

to bring it back two hundredths of a second.


