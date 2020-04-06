# HeapDump Summary

## What is HeapDump?
A heap dump is a snapshot of the memory of a Java process.

The snapshot contains information about the Java objects and classes in the heap at the moment the snapshot is triggered.

## How to do HeapDump?
1. Find process Id about your service
```bash
ps aux | grep <Your_Service_Name>
```

2. Dump to a file
```bash
(sudo -u xxxxx) <path>/jdk1.8/bin/jmap -dump:file=/tmp/YourFile.txt,format=b <process-id-to-dump>
```

3. Analysis the file
```bash
<path>/jdk1.8/bin/jhat </Path/To/File>
```

4. Check the webpage
It will default use 7000 port. So we should visit: `http://localhost:7000/`.

## Reference
1. [VisualVM](https://visualvm.github.io/).
1. [Oracle Java VisualVM Guide](https://docs.oracle.com/javase/8/docs/technotes/guides/visualvm/heapdump.html)
1. [Oracle jmap - Memory Map](https://docs.oracle.com/javase/7/docs/technotes/tools/share/jmap.html)
1. [Oracle jhat - Heap Analysis Tool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/jhat.html)
