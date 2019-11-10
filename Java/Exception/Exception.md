# Exception
I have some questions about Java exceptions, so list them here.

## When should throw new exception?
If the program goes into un-expected case. Like: invalid argument inputs, dependency service exception, etc.

## When should try or declare?
1. If we cannot handle it or translate the exception, then we declare it directly.
2. If we can translate the exception, then we should use try-catch handler.
