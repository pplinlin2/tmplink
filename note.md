# Virsh Command
### Host
* nodeGetMemoryStats: Prints memory stats of the node
```
[~] # virsh nodememstats
total  :              8114880 KiB
free   :              1942752 KiB
buffers:               493372 KiB
cached :              3675452 KiB

[~] #
[~] # cat note.py
#!/usr/bin/env python
import libvirt
conn = libvirt.open('qemu:///system')
print conn.getMemoryStats(libvirt.VIR_NODE_MEMORY_STATS_ALL_CELLS)
[~] #
[~] # ./note.py
{'cached': 3675832L, 'total': 8114880L, 'buffers': 493372L, 'free': 1954272L}
```
```
[~] # cat /proc/meminfo | grep -E "^MemTotal|^MemFree|^Buffers|^Cached"
MemTotal:        8114880 kB
MemFree:         1951756 kB
Buffers:          493376 kB
Cached:          3676012 kB
```

