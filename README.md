# Query-Alert-LM
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">

	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
		<title>jQuery弹出层插件modal.js</title>
		<link rel="stylesheet" type="text/css" href="css/common.css"/>
		<link rel="stylesheet" type="text/css" href="css/modal.css" />
		<script src="js/jquery-1.8.3.min.js" type="text/javascript" charset="utf-8"></script>
		<script src="js/alert.js" type="text/javascript" charset="utf-8"></script>
	</head>

	<body>
		<div class="key-word">
			<a href="javascript:;" id="add-key" class="aaa" data-title="这个属性是控制弹窗的标题" data-url="">这个弹窗的内容是通过ajax请求的</a>
		</div>
		<div class="key-word">
			<a href="javascript:;" id="add-key2" data-title="这个属性是控制弹窗的标题">这个窗口的内容是通过传递html参数获得的</a>
		</div>
		<div class="key-word">
			<a href="javascript:;" id="add-key3" data-title="这个属性是控制弹窗的标题">这个窗口的内容是当前元素的内容</a>
		</div>
		<div class="key-word">
			<a href="javascript:;" id="add-key4" data-title="这个属性是控制弹窗的标题">这个可以在窗口里的元素中添加事件</a>
		</div>
		<!--data-url="ajax.txt"属性是设定ajax请求的路径-->
		<script>
			//document.oncontextmenu = function(e) { return false; }//防止右击弹出菜单
			$("#add-key").click(function() {
				$("#add-key").createModal({
					background: "#000", //设定弹窗之后的覆盖层的颜色
					width: "1000px", //设定弹窗的宽度
					height: "500px", //设定弹窗的高度
					resizable: true, //设定弹窗是否可以拖动改变大小
					html: "<p>你可以在这个属性里面写入任何的html代码！</p>"
				});
			});

			$("#add-key2").click(function() {
				$("#add-key2").createModal({
					background: "red", //设定弹窗之后的覆盖层的颜色
					width: "1000px", //设定弹窗的宽度
					height: "500px", //设定弹窗的高度
					resizable: true, //设定弹窗是否可以拖动改变大小
					bgClose: true,
					html: "<p>你可以在这个属性里面写入任何的html代码！</p>"
				});
			});

			$("#add-key3").click(function() {
				$("#add-key3").createModal({
					background: "blue", //设定弹窗之后的覆盖层的颜色
					width: "1000px", //设定弹窗的宽度
					height: "500px", //设定弹窗的高度
					resizable: false //设定弹窗是否可以拖动改变大小
				});
			});

			$("#add-key4").click(function() {
				$("#add-key4").createModal({
					background: "#000", //设定弹窗之后的覆盖层的颜色
					width: "600px", //设定弹窗的宽度
					height: "146px", //设定弹窗的高度
					resizable: true, //设定弹窗是否可以拖动改变大小
					move: false, //规定弹窗是否可以拖动
					bgClose: false, //规定点击背景是否可以关闭
					html: "<div class='modal-promot-mess'>确认要删除该产品吗？</div>" +
						"<p class='insure-btn-con'><span class='sure-btn'>确定</span><span class='cancel-btn modal-close'>取消</span></p>",
					addFunction: function() { //增加的方法
						$(".modal-promot-mess").click(function() {
							alert("addFunction");
						})
					}
				}, function() { //回调函数的方法
					$(".insure-btn-con").click(function() {
						alert("callback")
					});
				});
			})
		</script>
	</body>

</html>
