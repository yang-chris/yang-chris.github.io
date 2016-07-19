---
title: node创建文件
date: 2016-07-12 15:07:28
---
#1.node新建JSON文件
####var fs = require('fs');
####var obj={
    name:"yxw",
    age:10,
    hobby:["read","play","sleep"]
};
####fs.writeFileSync('./output.json', JSON.stringify(obj));
####var JsonObj = JSON.parse(fs.readFileSync('./output.json'));
####console.log(JsonObj);
#2.node重命名

#####var fs=require("fs");
#####fs.rename(__dirname+"/fsDir",__dirname+"/fs",function(err){
    if(err){
        console.log(err);
        return;
    }
    console.log("重命名成功");
});
#3.node删除空目录
####var fs=require("fs");
####fs.rmdir(__dirname+"/test/test",function(err){
    if(err){
        console.log("删除空目录失败，可能原因：1.目录不存在，2.目录不为空");
        console.error(err);
        return;
    }
    console.log("删除目录成功！");
});
#5.读取文件
####var fs=require("fs");
####var path=require("path");

######//1.读取文件readfile函数
####fs.readFile(__dirname+"/test.txt",{flag:"r+",encoding:"utf-8"},function(err,data){
    if(err){
        console.log(err);
        return;
    }
    console.log(data);
})