# Entering-tranquility

## Prevent Mac from updating
sudo vi /etc/hosts\n
#Prevent updates\n
0.0.0.0 swdist.apple.com.edgekey.net\n
0.0.0.0 swdist.apple.com.akadns.net\n

## Prevent Chrome from updating
Method that helped me:

To empty these directories:
/Library/Google/GoogleSoftwareUpdate/
~/Library/Google/GoogleSoftwareUpdate/
Then change the permissions on these folders named 'GoogleSoftwareUpdate' so that there's no owner and no read/write/execute permissions.
In terminal:

cd /Library/Google/
sudo chown nobody:nogroup GoogleSoftwareUpdate
sudo chmod 000 GoogleSoftwareUpdate
cd ~/Library/Google/
sudo chown nobody:nogroup GoogleSoftwareUpdate
sudo chmod 000 GoogleSoftwareUpdate
Then do the same for the folder Google one level up.
cd /Library/
sudo chown nobody:nogroup Google
sudo chmod 000 Google
cd ~/Library/
sudo chown nobody:nogroup Google
sudo chmod 000 Google

## Prevent Microsoft updates on Mac
Another options without delete …
launchctl domain/service.plist

launchctl disable user/501/com.microsoft.update.agent.plist
launchctl disable user/501/com.microsoft.OneDriveStandaloneUpdater.plist

sudo launchctl disable system/com.microsoft.OneDriveStandaloneUpdaterDaemon.plist
sudo launchctl disable system/com.microsoft.OneDriveUpdaterDaemon.plist
sudo launchctl disable system/com.microsoft.autoupdate.helper.plist

