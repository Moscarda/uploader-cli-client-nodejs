### Install

As requeriments you need `nodejs` and `npm`. 

    npm install -g apaste

In Debian GNU/Linux 8 (Jessie) the npm version is too old to work with. You will need to upgrade npm manually.

    # install requeriments
    apt-get nodejs nodejs-legacy npm
    # npm install -g npm            # install npm 3.3.x, uncomment for jessie
    # hash -r                       # rescan $PATH, uncomment for jessie
    # finally install apaste
    sudo npm install -g apaste

### apaste, the share.riseup.net command-line client

This is a modification of [upclient](https://github.com/Upload/upclient), the [Up1](https://github.com/Upload/Up1) command-line client to make it work with [https://share.riseup.net](https://share.riseup.net). As there is currently no way to customize it using config files, we had to make this for now.

Please help and contribute directly to the [Up1 command-line client](https://github.com/Upload/upclient)

    Usage: apaste [options] [files]
    
    Upload files and text to an Up1 based pastebin. If no argument is specified, stdin is assumed.
    
    Options:
      -b, --binary        force application/octet-stream (for downloadable file)
      -t, --text          force text/plain (for pastebin)
      -f, --file <name>   force file name for stdin based inputs
      -m, --mime <mime>   force given mime type (default: detect)
          --version       display version information and exit
          --help          display this help and exit
    

### Usage examples

Paste command output to Up1:

    ps aux | apaste

Copy an image file to Up1:

    apaste image.png

Take a screenshot (using a selection rectangle), send it to Up1, and put the result link on the clipboard:

    import png:- | apaste | xsel -b

Do the same as above, but also notify when complete:

    import png:- | apaste | tee >(xsel -b) >(xargs notify-send "Upload Complete")

### Up1

For more information on Up1, view the README at https://github.com/Upload/Up1
