#!/bin/bash
#if [ true != "$INIT_D_SCRIPT_SOURCED" ] ; then
#    set "$0" "$@"; INIT_D_SCRIPT_SOURCED=true . /lib/init/init-d-script
#fi
### BEGIN INIT INFO
# Provides:          ramdisk
# Required-Start:    
# Required-Stop:     
# X-Stop-After:      sendsigs
# Default-Start:     2 3 4 5
# Default-Stop:      0 1 6
# Short-Description: Ramdisk
# Description:       Ramdisk
### END INIT INFO

# Author: Michal Subrt <spekodlak@gmail.com>

do_start () {
  /usr/sbin/ramdisk load
}

do_stop () {
  /usr/sbin/ramdisk backup
}

do_restart () {
  do_stop
  do_start
}

case "$1" in
  start)
        do_start
	;;
  reload|force-reload)
	echo "Error: argument '$1' not supported" >&2
	exit 3
	;;
  stop)
	do_stop
	;;
  stop)
	do_restart
	;;
  status)
	exit 0
	;;
  *)
	echo "Usage: $0 start|stop|restart" >&2
	exit 3
	;;
esac
