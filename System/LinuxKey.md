# apt-key vs gpg

<pre>
apt-key 
   add filename
           Add a new key to the list of trusted keys. The key is read from
           filename, or standard input if filename is -.

gpg
   --import

   --fast-import
          Import/merge keys. This adds the given keys to the keyring.  The
          fast version is currently just a synonym.
</pre>