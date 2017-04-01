
* {Stream}

`process.stdin` 属性返回一个等同于或关联到 `stdin` 的可写流 （[Readable][] stream）。

例如：
```js
process.stdin.setEncoding('utf8');

process.stdin.on('readable', () => {
  var chunk = process.stdin.read();
  if (chunk !== null) {
    process.stdout.write(`data: ${chunk}`);
  }
});

process.stdin.on('end', () => {
  process.stdout.write('end');
});
```

作为可写流，`process.stdin` 也同样可以在“旧”模式下使用与v0.10之前用Node.js编写的脚本兼容。
更多信息请查阅 [Stream compatibility][].

*注意*：在“旧”流模式下，“stdin”流默认暂停，所以必须调用`process.stdin.resume()`来读取。同时也请注意，调用`process.stdin.resume（）`将会使它本身回到“旧”流模式。


