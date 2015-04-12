To make test nocloud disk image:

genisoimage  -output seed.iso -volid cidata -joliet -rock user-data meta-data

You can test the image in kvm without OpenStack by invoking kvm like this:

kvm -m 1024 -curses -net nic,model=virtio -net tap,ifname=mark0 \
-drive file=image.qcow2,if=virtio -drive file=seed.iso,if=virtio


