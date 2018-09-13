# ovsportranges

### Description
Openflow requires port ranges to be defined as bitwise matches. This module 
provides an easy way to the port/mask ranges for a specified port range.

As described in the [ovs-ofctl](http://www.openvswitch.org/support/dist-docs-2.5/ovs-ofctl.8.txt) documentation:
> Bitwise  match  on  TCP  (or  UDP or SCTP) source or destination
> port.  The port and mask are 16-bit numbers written  in  decimal
> or  in  hexadecimal prefixed by 0x.  Each 1-bit in mask requires
> that the corresponding bit in port must match.   Each  0-bit  in
> mask causes the corresponding bit to be ignored.

It is recommended to only use this for large ranges that would require a large number of flows.

### Installation
`pip install ovsportranges`

### Basic Usage
``` python
from ovsportrange import OvsPorts

if __name__ == "__main__":
    ovsports = OvsPorts()
    ranges = ovsports.get_hex_ports(1000, 1999)
    for r in ranges:
        print(r)
```

### Output
```text
0x3e8/0xfff8
0x3f0/0xfff0
0x400/0xfe00
0x600/0xff00
0x700/0xff80
0x780/0xffc0
0x7c0/0xfff0
```

