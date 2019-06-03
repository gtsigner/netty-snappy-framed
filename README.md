## netty中的协议压缩

netty  codec -> SnappyFramedDecoder 和 Encoder


## 查看
https://github.com/zhaojunlike/netty-snappy-framed


## 使用
``` bash
yarn add netty-snappy
```

``` javascript
        const CryptoJs = require('crypto-js');
        const {snappy}=require('netty-snappy')
        const str = "{adasdas\"\"}";
        const compressed = CryptoJs.enc.Base64.stringify(snappy.compress(str));
        console.debug('compress：' + compressed);
        const uncompressed = snappy.decompress(compressed);
        console.debug('decompress：' + uncompressed);
        assert(str === uncompressed)
```