# MJSXJ09CM
MJSXJ09CM camera

mkfifo /tmp/f
mkfifo /tmp/s
/mnt/data/bin/framegrabber -f /tmp/f -c 0 2>&1 >/dev/null &
/mnt/data/bin/framegrabber -f /tmp/s -c 1 2>&1 >/dev/null &
/mnt/data/bin/rtspserver -m /tmp/f -s /tmp/s -c /mnt/data/bin/config.json  2>&1 >/dev/null &
