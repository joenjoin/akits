# Record event sequence
# Do actions on the device, press Ctrl-C to finish
adb shell getevent -t > events.txt
# Convert event sequence to script
./decode_events.py events.txt > events.sh
# Load the script to the device
adb push events.sh /data/local/tmp/
# Set the permissions
adb shell chmod 755 /data/local/tmp/events.sh
# Run script
adb shell sh /data/local/tmp/events.sh

