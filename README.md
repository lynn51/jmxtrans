jmxtrans
========
For OpenTSDBWriter, Using "subAttr" can get CompositeData.

### Example Configuration
Here is an example configuration.

```
{
    "servers": [
        {
            "port": "1099",
            "host": "localhost",
            "username": "jmxReadonlyUser",
            "password": "secret",
            "queries": [
                {
                    "outputWriters": [
                        {
                            "@class": "com.googlecode.jmxtrans.model.output.OpenTSDBWriter",
                            "settings": {
                                "host": "tsd1.example.com",
                                "port": 4242,
                                "tagName": "Memory",
				                        "tags": {"monitor":"kafka.example.com","port":"8091","service":"vip"},
				                        "subAttr" : ["used"]
                            }
                        }
                    ],
                   "obj" : "java.lang:type=Memory",
                   "resultAlias": "Memory",
                   "attr" : ["HeapMemoryUsage"]
                }
            ]
        }
    ]
}
```
