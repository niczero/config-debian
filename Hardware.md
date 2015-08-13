# Hardware

## CPU Throttling

Check your current capabilities
```
lsmod | grep cpufreq
apt-get install cpufrequtils
cpufreq-info
```

The intel_pstate driver is limited to two governors (powersave and
performance).  To disable it, edit /etc/default/grub
```
GRUB_CMDLINE_LINUX_DEFAULT="intel_pstate=disable"
```
and reboot.

Then re-check your capabilities.
```
cpufreq-info
for cpu in 0 1 2 3; do
  cpufreq-set -c $cpu --min 800MHz --max 2.5GHz -g ondemand
done
```
