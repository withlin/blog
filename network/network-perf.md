```
root@10-102-126-131:/# perf trace --no-syscalls --event 'net:*' ping 10.233.79.100
PING 10.233.79.100 (10.233.79.100) 56(84) bytes of data.
64 bytes from 10.233.79.100: icmp_seq=1 ttl=63 time=0.448 ms
     0.000 ping/801679 net:net_dev_queue:dev=tunl0 skbaddr=0xffff902519307d00 len=84
     0.017 ping/801679 net:net_dev_start_xmit:dev=tunl0 queue_mapping=0 skbaddr=0xffff902519307d00 vlan_tagged=0 vlan_proto=0x0000 vlan_tci=0x0000 protocol=0x0800 ip_summed=0 len=84 data_len=0 network_offset=0 transport_offset_valid=1 transport_offset=20 tx_flags=0 gso_size=0 gso_segs=0 gso_type=0
     0.036 ping/801679 net:net_dev_queue:dev=eth0 skbaddr=0xffff902519307d00 len=118
     0.042 ping/801679 net:net_dev_start_xmit:dev=eth0 queue_mapping=0 skbaddr=0xffff902519307d00 vlan_tagged=0 vlan_proto=0x0000 vlan_tci=0x0000 protocol=0x0800 ip_summed=0 len=118 data_len=0 network_offset=14 transport_offset_valid=1 transport_offset=54 tx_flags=0 gso_size=0 gso_segs=0 gso_type=0
     0.057 ping/801679 net:net_dev_xmit:dev=eth0 skbaddr=0xffff902519307d00 len=118 rc=0
     0.067 ping/801679 net:net_dev_xmit:dev=tunl0 skbaddr=0xffff902519307d00 len=84 rc=0
     
```
