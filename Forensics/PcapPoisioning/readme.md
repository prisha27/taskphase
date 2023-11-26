#PcapPoisioning
>On downloading the file trace.pcap --- we see it is packet capture file which means. They basically contain data transferred over a network in discrete packets i.e. basically information about the communication between devices on that network
>
>Now we have to filter the data and find the flag this can be done with the help of this command :
>```
>strings trace.pcap | grep pico
```
it extract and filter printable strings from the file and then search for the string containing ' pico '.
