# Advanced Router Configurations

1. Stop debug message interruption during configuration

```bash
    R3(config)#line console 0
    R3(config-line)#logging synchronous
```

2. IP version 6 configuration on cisco routers

## IPv6 configurations

```bash
    R2(config)#ipv6 unicast-routing
    R2(config)#int f0/0
    R2(config-if)#ipv6 address 2001:3200:fade:1100::f/56
```

