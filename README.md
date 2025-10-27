# VMFS Converter

Overview:
VMFS Converter is a simple tool to mount VMFS devices, copy their contents to a host directory, and optionally convert VMDK files to QCOW2 format.

# How to Use:

**1. Download the latest RPM release using wget:**

wget -O vmfs-convert-1.3-1.el9.noarch.rpm https://github.com/MeselhyAbdallah/Linux-VMFS-convert-tool/raw/main/vmfs-convert-1.3-1.el9.noarch.rpm


**2. Install the RPM (RHEL/CentOS):**

sudo yum install ./vmfs-mount-1.0-1.el8.noarch.rpm

**3. Run the converter script:**

vmfs-mount
- Choose docker.io hub

**Follow the prompts for:**
-Choose your operation mode:
local → Mount and copy from a physical VMFS disk using a container.
scp → Copy VM folders or full datastores from ESXi via SSH/SCP.

**You’ll be prompted for:**
- Target output directory (e.g. /mnt/vmfs-out)
- VMFS device path or ESXi datastore
- Optional VMDK → QCOW2 conversion
- Optional cleanup of original files

**Limitations:**
- Requires root privileges to access VMFS devices.
- Does not handle snapshots or linked clones; only main VMDK files.
- Flat `.vmdk` files (`*-flat.vmdk`) must remain with descriptors.
- qemu-img' and 'podman' must be installed for conversion.
