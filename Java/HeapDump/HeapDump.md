# HeapDump Summary

## What is HeapDump?
A heap dump is a snapshot of the memory of a Java process.

The snapshot contains information about the Java objects and classes in the heap at the moment the snapshot is triggered.

## How to do HeapDump?
1. SSH to your service host

2. Find process ID about your service
```bash
ps aux | grep <Your_Service_Name>
```

3. Dump to a file
```bash
(sudo -u xxxxx) <path>/jdk1.8/bin/jmap -dump:file=/tmp/YourFile,format=b <process-id-to-dump>
```

4. Change file permission
```bash
(sudo -u xxx) chmod 777 YourFile
```

5. SCP file to your local laptop
```bash
scp username@your_service_host:/tmp/YourFile /Users/xxx/Desktop
```

6. Analysis
  6.1 Analysis the file with jhat
```bash
<path>/jdk1.8/bin/jhat </Path/To/File>
```

```
It will default use 7000 port. So we should visit: http://localhost:7000/.
```
  6.2 Analysis with jvisualvm
```bash
./jvisualvm

Then load your heap dump file
```

## Reference
1. [VisualVM](https://visualvm.github.io/).
1. [Oracle Java VisualVM Guide](https://docs.oracle.com/javase/8/docs/technotes/guides/visualvm/heapdump.html)
1. [Oracle jmap - Memory Map](https://docs.oracle.com/javase/7/docs/technotes/tools/share/jmap.html)
1. [Oracle jhat - Heap Analysis Tool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/jhat.html)
