
* {Stream}

`process.stdout` 属性返回一个链接到`stdout` 上的 [Writable][] 流 (fd `2`)。

例如，将 `process.stdin`拷贝到 `process.stdout` 上:

```js
process.stdin.pipe(process.stdout);
```

注意： `process.stdout` 与其他 Node.js 流在很多重要的地方不同，
查阅 [note on process I/O][] 以获取更多的信息。


