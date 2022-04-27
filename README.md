# Windows-10-Education-SmartOS-BHYVE-image-dataset


Download the image from the bt hash:

magnet:?xt=urn:btih:0b37a8f5eef4e739a0677e2910732558b4463fba&dn=win10education-smartos-bhyve-image.tar&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce&tr=udp%3A%2F%2Fopen.tracker.cl%3A1337%2Fannounce&tr=udp%3A%2F%2F9.rarbg.com%3A2810%2Fannounce&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A6969%2Fannounce&tr=udp%3A%2F%2Fwww.torrent.eu.org%3A451%2Fannounce&tr=udp%3A%2F%2Fopentor.org%3A2710%2Fannounce

or use the provided .torrent file


Install the image:

imgadm install -m win10education.dsmanifest -f win10education.zvol.gz

Create the vm:

vmadm create -f win10education.json

Make it boot with efi:

vmadm update $UUID bootrom="/usr/share/bhyve/uefi-rom.bin"

Show the vnc port (is set to 32320 in the json cofiguration file):

vmadm info $UUID

NOTE:

Automatic network configuration from the json configuration file do not work, leave dhcp and change the network settings inside the windows virtual machine.

This virtual machine is created following the instructions at https://github.com/TritonDataCenter/sdc-vmtools-windows/tree/master/bhyve
and other tips from the Smartos community at https://smartos.topicbox.com/groups/smartos-discuss and varius other websites and blogs.
