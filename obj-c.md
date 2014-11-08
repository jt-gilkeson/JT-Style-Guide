# JT's Objective-C Style Guide

## Constants 
For constant strings, prefer const NSStrings over #defines (ensures type-safety, limits scope)

```Objective-C
// Local (.m)
static NSString * const kFolderId = @"folderId";

// Externally visible a
// .h
extern NSString * const kFolderId;
// .m:
NSString * const kFolderId = @"folderId";

// Instead of
#define kFolderId @"folderId"
```

## Spacing

* One space should be used between the - or + and the return type, and no spacing in the parameter list except between parameters.

```Objective-C
- (void)deleteMessage:(NSNumber *)messageId
- (void)replyToMessage:(NSNumber *)messageId recipient:(NSNumber *)recipientId
```

* For pointers, separate type and * with a space, always group the * with the variable:

```Objective-C
- foo:(NSNumber *)messageId
NSNumber *messageId
```

* Protocols should have a space between the id and the type:

```Objective-C
@interface className : parentClass <protocolName>
- foo:(id <Prot>)anObject;
id <Prot> someObject;
id <Prot> *someObject;
```

* Keywords/Conditional Statement always have a space between the keyword and the condition: ``` if (expr), for (int x...) ```

* C/C++ style method names are immediately followed by the opening parentheses: ``` method(), add(x) ```

* Commas separating C/C++ parameters are followed by a space: ``` method(x, y, z); ```

* Operators have a space on each side: ``` x + y, (x == z) ```
* Exception: No spaces for Increment/Decrement operators: ``` x++ ```

* Semicolons in a for statement are followed by a space: ``` for (int x = 1; x < z; x++) ```


## Braces / Indentation 

Braces should follow Allman/BSD/C/Braces Left style:
* Braces always on their own line
* Opening and closing braces line up vertically
* Pairs of related keywords line up vertically (if, else if, else) (@try, @catch, @finally) (do, while)
* Exceptions: inline blocks:

```Objective-C
dispatch_async(fileIOQueue_, ^{
    NSString* path = [self sessionFilePath];
    if (path) 
    {
        // ...
    }
});

typedef NS_ENUM(NSInteger, ShapeType) 
{
    Circle,
    Rectangle,
    Triagle
};

@try
{
    if (expr)
    {
        statement;
        statement;
    }
    else if (expr)
    {
        statement;
    }
    else
    {
        statement;
        statement;
    }
 
    do
    {
        statement;
        statement;
    }
    while (x == y)
} 
@catch (NSException *e) 
{
    statement;
}
@finally
{
    statement;
    statement;
}
```
