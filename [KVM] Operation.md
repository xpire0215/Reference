# Operation

### Version - Ubuntu 18.04

[Install KVM guests with virt-install]([Install KVM guests with virt-install](https://www.howtoforge.com/installing-kvm-guests-with-virt-install-on-ubuntu-8.10-server))



### Install Ubuntu

```
> sudo virt-install -n test-vm -r 512 --vcpus=1 --file ./test-vm.qcow2 --file-size 30 --vnc --noautoconsole --os-type ubuntu --accelerate --network=bridge:br0 --hvm 
```



### Install Windows 8.1

```
> sudo virt-install -n win8.1 -r 2048 --vcpus=2 --file ./window8.1.qcow2 --file-size 30 --cdrom ../Downloads/Win8.1_Chinese\(Traditional\)_x64.iso --vnc --noautoconsole --os-type win8.1 --accelerate --network=bridge:virbr0 --hvm 
```



### VNC

```
> virsh vncdisplay win8.1
```

##### Use VNC-Viewer to view the vm



### KVM

```
> virsh start win8.1
```

