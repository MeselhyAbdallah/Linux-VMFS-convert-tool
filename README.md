# VMFS Converter

Overview:
VMFS Converter is a simple tool to mount VMFS devices, copy their contents to a host directory, and optionally convert VMDK files to QCOW2 format.

# How to Use:

**1. Download the latest RPM release using wget:**
wget https://github.com/MeselhyAbdallah/VMFS-Mount-Tool/blob/main/vmfs-convert-1.0-1.el8.noarch.rpm

**2. Install the RPM (RHEL/CentOS):**
sudo yum install ./vmfs-mount-1.0-1.el8.noarch.rpm

**3. Run the converter script:**
vmfs-mount

**Follow the prompts for:**
- Target directory to copy VMFS contents
- VMFS device (PARTUUID or /dev/sdX)
- Optionally convert `.vmdk` files to `.qcow2`
- Optionally remove original VMFS files

**Limitations:**
- Requires root privileges to access VMFS devices.
- Does not handle snapshots or linked clones; only main VMDK files.
- Flat `.vmdk` files (`*-flat.vmdk`) must remain with descriptors.
- qemu-img' and 'podman' must be installed for conversion.
