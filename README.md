# Raspberry Pi x Jellyfin Workshop
UWF ACM

## Login Creds

`acm:uwfacm`

## Connect Rasp Pi to Windows PC

1. Control Panel -> Network and Internet -> View network status and tasks
2. Click the connection you are getting internet from (`uwf-argo-air`)
3. Properties -> Sharing
4. Enable `Allow other network users to connect through this computer's Internet connection`
5. Select the interface you want to share internet with (That is the rasp pi)
6. Click `OK`

## SSH from PC to Rasp Pi

1. Open powershell or your favorite ssh client
2. `ssh acm@192.168.137.2`
3. Password is `uwfacm`

## Installing Jellyfin

1. Navigate to the Jellyfin website https://jellyfin.org/downloads/server
2. Click `Install Instructions` under Ubuntu/Debian
3. Copy that command into the Rasp Pi Terminal
    `curl https://repo.jellyfin.org/install-debuntu.sh | sudo bash`
4. Press Enter to continue installation
5. It should say `Thank you for installing Jellyfin, and happy watching!` when its finished

## Configuring Jellyfin

1. Go to your PC's web browser, and go to the following address http://192.168.137.2:8096
2. Create the admin username `jellyfin`
3. Create a new password for it
4. Plug in the media drive with all of your movies / media
5. Go back to ssh, and enter `lsblk`
6. Identify the drive's name `sda`
7. Create a new directory for the mounting point `sudo mkdir /mnt/media_server`
8. Mount the drive using its drive name `sudo mount /dev/sda1 /mnt/media_server`
9. Go back to the website configuration, and finish setting up the server
10. Make sure to only allow access to the `media_server` directory
