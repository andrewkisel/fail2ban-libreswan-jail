# fail2ban-libreswan-jail

## Description
Basic Fail2Ban filter and jail configuration for Libreswan.

---

### Usage

In order to install it in your system, please follow these steps:
- Copy `libreswan.conf` into `/etc/fail2ban/filters.d/` directory.
- Copy and append contents of the file `jail.local` to `/etc/fail2ban/jail.local`. If it doesn't exist - just copy the file from this repo.
- Run `sudo service fail2ban restart` and it should work.

### Testing

To test you can use Fail2Ban's standard feature called `fail2ban-regex`. Usage is as follows: `sudo fail2ban-regex <path-to-logfile> <path-to-filter>'.
It also accepts a bunch of options like: `--print-all-matched`, `--print-all-missed`, `--print-all-ignored`.
Example: `sudo fail2ban-regex /var/log/auth.log.1 /etc/fail2ban/filter.d/libreswan.conf --print-all-matched`
to run the `libreswan.conf` filter against existing log in `/var/log/auth.log.1` and print all matches.

### Compatability

This has only been tested on Debian 10 w/Fail2Ban v0.10.2 and Libreswan 3.29. 

P.S: I don't see any reason why it would not be compatible with other versions, but have not verified.
The only thing that might change from version to version is log entry format. Adjust the regex accordingly.

---

© [Andrew Kisel](https://kisel.kisels.net/)
