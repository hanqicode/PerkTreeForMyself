# HeapDump Summary

## What is HeapDump?
A heap dump is a snapshot of the memory of a Java process.

The snapshot contains information about the Java objects and classes in the heap at the moment the snapshot is triggered.

## How to do HeapDump?
1. SSH to your service host
```bash
ssh your_service_host
```

2. Find process ID about your service
```bash
ps aux | grep <Your_Service_Name>
```

3. Dump to a file
```bash
cd <path>/jdk1.8/bin/
(sudo -u xxxxx) ./jmap -dump:file=/tmp/YourFile,format=b <process-id-to-dump>
```

4. Change file permission
```bash
(sudo -u xxx) chmod 777 YourFile
```

5. On your local laptop, SCP file back
```bash
scp username@your_service_host:/tmp/YourFile /Users/xxx/Desktop
```

6. There are two ways to analyze the file

    1. jhat(heap analysis tool)
    ```bash
    <path>/jdk1.8/bin/jhat </Path/To/File>
    ```

    ```
    It will default use 7000 port. So we should visit: http://localhost:7000/.
    ```

    2. jvisualvm
    ```bash
    ./jvisualvm

    Then choose and load your heap dump file through UI
    ```

## Reference
1. [VisualVM](https://visualvm.github.io/).
1. [Oracle Java VisualVM Guide](https://docs.oracle.com/javase/8/docs/technotes/guides/visualvm/heapdump.html)
1. [Oracle jmap - Memory Map](https://docs.oracle.com/javase/7/docs/technotes/tools/share/jmap.html)
1. [Oracle jhat - Heap Analysis Tool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/jhat.html)
