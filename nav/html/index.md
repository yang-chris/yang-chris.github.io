---
title: html
date: 2016-07-12 15:06:59
---
var fs = require("fs");
fs.watchFile(__dirname + "/test.txt", {interval: 20}, function (cur, prev) {
    if (Date.parse(prev.ctime) == 0) {
        console.log("文件被创建");
    } else if (Date.parse(cur.ctime) == 0) {
        console.log("文件被删除");
    } else if (Date.parse(cur.mtime) != Date.parse(prev.mtime)) {
        console.log("文件被修改");
    }
});
fs.watchFile(__dirname + "/test.txt", function (cur, prev) {
    console.log("这是第二个watch，监视文件有修改");
});



