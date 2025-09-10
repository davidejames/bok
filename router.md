

### Upgrading router... ###

#### OpenWRT ####
Starting version is 18
Current version is 24


#### Steps ####
- had to do a reset to get into router with default password
- it was unable to upgrade from 18 to 24, so I ended up uploading every
  major version one at a time to get it up to 24
- one of the versions did complain that it didn't think the file was the
  correct one, but allowed me to force install if I was sure I had the file
  for the device - after double-checking, I did the force upgrade - all seemed
  well.
- got it to version 24...
  - set new password
  - setup new wireless network on one of the radios:
    - set it up on the most capable radio
    - must set country code according to the advice given:
        https://openwrt.org/docs/guide-quick-start/basic_wifi
    - setup with highest security option that was also flexible:
        the WPA3-SAE/WPA2-PSK one I think
    -
- wireless woes...
  - new network would not show up in any device.
  - tried disabling and enabling
  - tried restarting device, but then couldn't login on web console
- login woes...
  - logged in using a private browser window and it was fine!
- fixing config?
  - since the complaint from before had to do with some incompatibility of
    configuration and that could also cause oddities with setting up any
    settings on the device...
  - in admin/system - there is an option for erasing configuration.
  - hoping that with a clean config partition, the other issues will be
    resolved.
- setting up wireless (again)
  - once config was cleared, log back in, set new password again
  - setup wireless - it seems maybe a bit better behaved now..?
  - re-setup wireless on radio0, removed the default OpenWRT open wifis
    (disabled, open), and had highest security interface setup
  - radio started to work - but could not connect with my laptop or phone
  - changed to WPA2-Personal and both computer and phone could connect.
  - seemed like high time to rotate the password of our wifi, so I did that.
  - then setup HeliosL (2.4G) network that we use for rokus and such - kept
    the password the same to see if these devices would reconnect
    automatically.
  - some devices did connect automatically
  - wifi got really flaky and started dying periodically
- did another config reset, going to walk through slower this time...
    - enabling ONLY the 5G Helios for now
    - I know some roku devices don't behave well, so leave them off.

Walk through starter guide just so we don't miss something...
https://openwrt.org/docs/guide-quick-start/starterfaq
- installs/apps:
    - btop runs ok - need to 'force-utf' for it to start, but then is fine
    - tmux runs fine - I didn't do the tmux in tmux setup though, so it doesn't
      work very well
    - no neovim
    - vim is a pared down version - no netrw
- ssh access...
    - it would be a great idea to setup an ssh key, then backup that key to
      proton drive or proton pass - this would have completely prevented the
      getting locked out of openwrt completely
    - setup ssh key and made notes on the setup, summary:
        - put comment in key of: david@router.lan
        - used old password scheme <thing><base>


