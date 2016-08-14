# dsd_debug
c语言调试宏
## 代码示例
```c
int main(int argc, char const *argv[]) {
	int num = 34;

	dsd_set_log_level(DSD_ERR|DSD_NOTICE|DSD_WARN|DSD_DEBUG|DSD_INFO);

	dsdl_notice("this is a test\n");
	dsdl_notice("num = %d\n", num);
	dsdl_info("this is a test\n");
	dsdl_info("num = %d\n", num);
	dsdl_debug("this is a test\n");
	dsdl_debug("num = %d\n", num);
	dsdl_warn("this is a test\n");
	dsdl_warn("num = %d\n", num);
	dsdl_err("this is a test\n");
	dsdl_err("num = %d\n", num);

	return 0;
}
```
## 输出内容
![打印输出](1.png)


终端的字符颜色是用转义序列控制的，是文本模式下的系统显示功能，和具体的语言无关。
转义序列是以 ESC 开头,可以用 \033 完成相同的工作（ESC 的 ASCII 码用十进制表示就是 27， = 用八进制表示的 33）。

\033[显示方式;前景色;背景色m

显示方式:0（默认值）、1（高亮）、22（非粗体）、4（下划线）、24（非下划线）、5（闪烁）、25（非闪烁）、7（反显）、27（非反显）
前景色:30（黑色）、31（红色）、32（绿色）、 33（黄色）、34（蓝色）、35（洋红）、36（青色）、37（白色）
背景色:40（黑色）、41（红色）、42（绿色）、 43（黄色）、44（蓝色）、45（洋红）、46（青色）、47（白色）

\033[0m 默认
\033[1;32;40m 绿色
033[1;31;40m 红色

printf( "\033[1;31;40m 输出红色字符 \033[0m" )





