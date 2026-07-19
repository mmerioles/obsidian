
exit status - when you run a command, you get an error code

ex. ping 
`ping 10.30.10.1 -c 1`
`echo $?` - status of 0 is successful

conditional
`ping 10.30.1.1 -c 1 && echo "ping worked" || "ping failed"`