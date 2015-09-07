# Article
//利用node.js返回静态页面的方法：
//1、将html代码与JavaScript代码写在一起进行请求
	server=http.createServer(function(req,res){
		res.writeHead(200,{'content-Type':'text/html'});
		res.write('<h1>Hello world</h1>');
		res.end();
	})
//2、利用express模块返回静态页面
	var express=require('express'),
			app=express(),
			server=require('http').createServer(app);
	app.use('/',express.static(__dirname + '/www'));
	server.listen(80);