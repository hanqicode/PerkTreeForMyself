# 11 - The Environment

The shell maintains a body of information during our shelle session called the **environment**.

Some data stored in the environment and will be used by programs as system configurations.

## What Is Stored In The Environment?
There are two kinds of variables:
1. environment variables.
2. shell variables.

`printenv`: print only environment variables.
Since the list of variables will be fairly long, it is best to pipe like: `printenv | less`.

`set`: when use directly, it will print shell + environment variables.

`export`: export environment to subsequently executed programs

`alias`: create an alias for a command
