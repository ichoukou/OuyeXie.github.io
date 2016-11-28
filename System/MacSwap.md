 - [How to enable/disable swapping in Mac OS X](http://wiki.summercode.com/how_to_disable_or_enable_swapping_in_mac_os_x)

<pre>
<code>
To disable swap (pager daemon) run this command in Terminal:
sudo launchctl unload -w /System/Library/LaunchDaemons/com.apple.dynamic_pager.plist
After stopping pager daemon, you may want to remove swapfiles by this command:
sudo rm /private/var/vm/swapfile*
To enable swap, you need to boot in Single Mode (Hold [CMD + S] at booting time) and run this command:
sudo launchctl load /System/Library/LaunchDaemons/com.apple.dynamic_pager.plist
</code>
</pre>