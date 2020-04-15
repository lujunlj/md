## Nginx config
1. 自定义变量：
	location a/ {
		return 200 $a
	}
	location b/ {
		set $a hello nginx
		return 200 $a
	}
声明规则:
	set $变量名 变量值
在不同层级设置标签中声明变量规则:
	可用范围 : http>server>location

