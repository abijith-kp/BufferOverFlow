Buffer Overflow Attack
======================

* cat /proc/sys/kernel/randomize\_va\_space
* echo 0 > /proc/sys/kernel/randomize\_va\_space
* write the vulnarable code
* compile it with g++ -fno-stack-protector -mpreferred-stack-boundary=2
* check the running of the prog using `python -c 'print "A" * 400'`
* use gdb to show the segmentation fault
* we can see that eip and ebp are overwritten. Since eip is overwritten we can
  conclude that we can control the program flow until it is there in the
  memory
* to know how much bytes to overwrite the return address we use
  metasploitframework(/opt/metasploit/msf3/tools/)
* use pattern_create.rb 600
