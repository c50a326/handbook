# Ways to Upload/Send a File from Termux

## `cat` to termbin.com

1. Run `cat FILE | nc termbin.com 9999` where `FILE` is the file to be shared.
2. Click the link returned in the output of the command (it may take a few seconds, and you need a functioning internet connection), and then copy and paste to the recipient.

## Using `termux-setup-storage`

1. Read https://termux.com/storage.html bearing in mind:
   - `$HOME` is an environment variable, you can see what its value is with `echo $HOME`. The purpose of environment variables is so that programs/scripts can be portable across different environments (different computers with different users), e.g. a script that makes some changes within a user's home directory can simply operate on the directory `$HOME` rather than needing to discern this some other way.
   - `apt` is a _["package manager"](https://en.wikipedia.org/wiki/Package_manager)_. The vast majority of software people are using on Linux operating systems is open-source, thus it is freely available (on the internet, usually on [GitHub](https://github.com) these days) and can be provided via [software repositories](https://en.wikipedia.org/wiki/Software_repository). In order to download software (_packages_) from a _software repository_, a _package manager_ is required.
2. Run `termux-setup-storage` to add directory links to known areas of storage on the device.
3. Copy the file to one of these directories e.g.: `cp FILE.md ~/storage/shared`.
4. Share the file using a familiar application such as [Google Drive](https://drive.google.com). The file should be accessible in the location you copied it to.
