import random
import time
import datetime  
import base64
from Crypto.Cipher import AES

info = 'Flag Encrypted on 2023-08-02 10:27'
date = list(map(int, info.split(' ')[-2].split('-')))
time = list(map(int, info.split(' ')[-1].split(':')))
rf = 'lQbbaZbwTCzzy73Q+0sRVViU27WrwvGoOzPv66lpqOWQLSXF9M8n24PE5y4K2T6Y'
iv = b"\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0\0"
ct = base64.b64decode(rf)
for hh in range(24):
    for sec in range(60):
        for ml in range(1000):
            dt2 = datetime.datetime(date[0], date[1], date[2], hh, time[1], sec, 1000*ml)
            ts2 = datetime.datetime.timestamp(dt2)
                    
            seed2 = round(ts2*1000)

            random.seed(seed2)

            key2 = []
            for i in range(0,16):
                key2.append(random.randint(0,255))

            key2 = bytearray(key2)

            cipher = AES.new(key2, AES.MODE_CBC, iv)
            pt = cipher.decrypt(ct)
            if pt[:4] == b'flag':
                print(pt)
