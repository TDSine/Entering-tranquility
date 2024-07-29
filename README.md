# Entering-tranquility

## Prevent Mac from updating
sudo vi /etc/hosts<br />
#Prevent updates<br />
0.0.0.0 swdist.apple.com.edgekey.net<br />
0.0.0.0 swdist.apple.com.akadns.net<br />

## Prevent Chrome from updating<br />
Method that helped me:<br />

To empty these directories:<br />
/Library/Google/GoogleSoftwareUpdate/<br />
~/Library/Google/GoogleSoftwareUpdate/<br />
Then change the permissions on these folders named 'GoogleSoftwareUpdate' so that there's no owner and no read/write/execute permissions.<br />
In terminal:<br />

cd /Library/Google/<br />
sudo chown nobody:nogroup GoogleSoftwareUpdate<br />
sudo chmod 000 GoogleSoftwareUpdate<br />
cd ~/Library/Google/<br />
sudo chown nobody:nogroup GoogleSoftwareUpdate<br />
sudo chmod 000 GoogleSoftwareUpdate<br />
Then do the same for the folder Google one level up.<br />
cd /Library/<br />
sudo chown nobody:nogroup Google<br />
sudo chmod 000 Google<br />
cd ~/Library/<br />
sudo chown nobody:nogroup Google<br />
sudo chmod 000 Google<br />

## Prevent Microsoft updates on Mac<br />
Another options without delete …<br />
launchctl domain/service.plist<br />

launchctl disable user/501/com.microsoft.update.agent.plist<br />
launchctl disable user/501/com.microsoft.OneDriveStandaloneUpdater.plist<br />

sudo launchctl disable system/com.microsoft.OneDriveStandaloneUpdaterDaemon.plist<br />
sudo launchctl disable system/com.microsoft.OneDriveUpdaterDaemon.plist<br />
sudo launchctl disable system/com.microsoft.autoupdate.helper.plist<br />

## For Mac App Store<br />
Open terminal and modify the lastest updated date by typing<br />
defaults write com.apple.appstored LastUpdateNotification -date "2029-12-12 12:00:00 +0000"<br />

