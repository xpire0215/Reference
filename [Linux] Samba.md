### How to install and setting Samba
# Install Samba
sudo apt install samba

# Create a shared folder
mkdir /home/ken/SharedFolder

# Modify configuration file
sudo vim /etc/samba/smb.conf

# Add default setting to the bottom of configuration file
[Shared Folder]
  comment = Shared Folder
  path = /home/ken/SharedFolder
  read only = no
  browsable = yes

# Add a password to user
sudo smbpasswd -a ken

# Restart system
sudo systemctl restart smbd

### Connect to Samba via CLI ( Client PC )
# Install smbclient
sudo apt install smbclient (optional: cifs-utils)

# List avaliable folder
sudo smbclient -L samba_server_ip

# Connect to samba server
sudo smbclient //samba_server_ip/shared_folder -U user_name
sudo smbclient //samba_server_ip/shared_folder -U user_name%user_passwd
example: sudo smbclient //10.21.20.18/Common -U ken

# Mount the samba folder
mkdir /home/ken/Common
sudo mount //samba_server_ip/shared_folder ./Common -o username=user_name,password=user_passwd
example: sudo mount //10.21.20.18/Common ./Common -o username=ken,password=KenXXXXXX

# Unmount the samba folder
sudo umount ./Common
