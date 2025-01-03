# DiskPart Guide: Clean, Partition, Format, and Assign Letter to Disk

This guide explains how to use **DiskPart** to clean a disk, create partitions, format it with a file system, and assign a drive letter.

```bash
# 1. Open Command Prompt as Administrator
# Press Win + X and select "Command Prompt (Admin)" or "Windows PowerShell (Admin)". 
# Alternatively, search for cmd, right-click it, and select "Run as Administrator".

# 2. Launch DiskPart
diskpart

# 3. List All Disks
# List all available disks to identify the disk you want to clean.
list disk

# Example Output:
# Disk ###  Status         Size     Free     Dyn  GPT
# --------  -------------  -------  -------  ---  ---
# Disk 0    Online         500 GB   0 B
# Disk 1    Online         1 TB     0 B

# 4. Select the Disk
# Select the disk you want to clean (replace X with the disk number).
select disk X

# 5. Clean the Disk
# Clean the selected disk, which removes all partitions and data.
clean

# For a more secure clean, use:
clean all

# 6. Create a New Partition
# Create a new primary partition that takes up the entire disk.
create partition primary

# Alternatively, to create a partition with a specific size (in MB):
# create partition primary size=102400   # For a 100 GB partition

# 7. Format the Partition
# Format the partition with the desired file system. 
# Here, we're using NTFS as an example:
format fs=ntfs quick

# 8. Assign a Drive Letter
# Assign a drive letter (e.g., E) to the partition.
assign letter=E

# 9. Exit DiskPart
# Once all steps are completed, exit DiskPart.
exit