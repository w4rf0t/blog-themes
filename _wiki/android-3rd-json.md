---
layout: wiki
title: JSON
cate1: Android
cate2:
description: JSON
keywords: Android
---

## gson

## FastJson

### 循环引用的问题

### Circular reference problem

If the same object is added to a List multiple times, it will be converted to this by default in `JSON.toJSONString`:

```json
[
    {
        "k1": "v1",
        "k2": []
    },
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"},
    {"$ref": "$.paras[0]"}
]
```


I have added it to the List many times because of the misoperation, so it is good to solve the misoperation.

As for the case where it is really the real intention (maybe only the front end?), you can refer to <http://blog.csdn.net/Singleton1900/article/details/50435247> to solve it.
### boolean serialization field naming

```java
public class Test {
    private boolean isTest;

    public boolean isTest() {
        return isTest;
    }

    public void setTest(boolean isTest) {
        this.isTest = isTest;
    }
}
```

When objects of this class use the `JSON.toJSONString` method, the `isTest` field name is changed to `test`.

There are several ways to solve it:

1. Change the field name to test (compliant with Java Bean)

2. Annotate the field name, indicating that its serialized name is `isTest`

3. Using Gson

The related discussion issues in the FastJson project are as follows:

<https://github.com/alibaba/fastjson/issues/278>
