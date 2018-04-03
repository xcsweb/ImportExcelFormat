# ImportExcelFormat

```
        /*
			String: obj[excelData] 表格数据
			Array:type[check] 校验规则，可以自定义,
			Fn:type[format] 格式话对应的列，一般为生成select
			String:bgColor 默认错误提示颜色
			Fn:validateRules["isTel"] 为自定义的校验规则
		*/
		/*调用方法*/
		new excelBuild({
			excelData:str,
			type:{
				0:{
					check:['require'],
					format:function(v){
						var $sel=$("<span><select><option value='1'>1</option><option value='1'>1</option><option value='1'>1</option><select></span>");
						v.append($sel);
						ret=$sel.find("select").val();
					}
				},
				1:{
					check:['require'],
				},
				2:{
					check:['require'],
				},
				3:{
					check:['require','isPhone'],
				},
				4:{
					check:[],
				},
				5:{
					check:[],
				}
			},
			bgColor:"#f4afafd4",
			validateRules:{
				"isTel":function(v){
					var re=/(\d{3,4}\-)?\d{7,8}/;
					if(re.test(v)){
						return true
					}else{
						return false
					}
				}
			}
		})
	}
```
# 该组件借用了sheetjs官方的代码,该插件支持校验，自定义定制单元格，现在免费开源

# 线上地址有默认参数，现在传了也没用，自己下载下来，自己配置后方可使用
# 预览地址[https://xcsweb.github.io/ImportExcelFormat/]()，有部分样式有点问题，自己调整下