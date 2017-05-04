<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>test</title>
		<style type="text/css">
		    #top{
		    	width: 400px;
		    }
			#must{
				color: #FF9933;
			}
			#count{
				float: right;
			}
			#a{
				margin-top: 10px;
				width: 400px;
				height: 100px;
				border-color:darkgrey;
			}
			#error{
				color: red;
				font-size: 15px;
				height: 30px;   
				margin-top: 10px;              
			}
		</style>
		<script type="text/javascript">
			function load(){
				var obj=document.getElementById("a");
				obj.style.color="#A9A9A9";
				obj.value="只能输入200个字符";
			}
			function del(){
				var obj=document.getElementById("a");
				if (obj.value=="只能输入200个字符") {
				    obj.style.color="#000000";
					obj.value="";
				} 
			}
			function addhint(){
				var obj=document.getElementById("a");
				if(obj.value==""||obj.value==null){
					load();
				}
			}
			function checkNum(len){
				var b=document.getElementById("b");
				var s=document.getElementById("a");
				var count=a.value.length;
				if(count>=len){
					b.innerText=len;
				}
				else
				b.innerText=count;
				var show=document.getElementById("error");
				if(s.value.replace(/[^\XPathNamespace0-\xff]/g,"aa").length>=len){
					s.value=s.value.substring(0,len);
					show.innerText="最多只能输入200个字";
					return false;
				}
			}
		</script>
	</head>
	<body onload="load()">
		<div id="top">
		<span id="must">*</span>
		<label>请填写备注</label>
		<span id="count">
			(<label id="b" size="2" disabled>0
		</label>/200)</span>
        </div>
		<textarea id="a" onkeydown="checkNum(200)" onkeyup="checkNum(200)" onfocus="del()" onblur="addhint()">
			
		</textarea>
		<br />
		<span id="error"></span>
	</body>
</html>

