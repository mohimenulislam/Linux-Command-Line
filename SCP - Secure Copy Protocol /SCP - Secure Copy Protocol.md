### Secure Copy Protocol

#### Copy a file from `Conrolnode` to `host1`
```bash
scp /root/example.txt root@192.168.10.131:/root/    #or
scp /root/example.txt root@host1:/root/
```

#### Copy file from `host1`. 
```bash
scp root@host1:/root/testfile.txt /root/
```
