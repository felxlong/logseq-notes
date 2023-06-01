- #OS #Interview
- Ctrl-C 通常发送 [[SIGINT]] 中断信号，程序不能响应，可能有以下原因：
	- 信号被程序忽略，附录一展示
	  logseq.order-list-type:: number
	- 程序异常处理不当
	  logseq.order-list-type:: number
	- 程序处于阻塞或忙碌状态，无法立即响应中断信号
	  logseq.order-list-type:: number
- ### 附录一
- 如下代码展示程序捕获 Ctrl-C 执行自定义函数
	- ```c
	  #include <stdio.h>
	  #include <signal.h>
	  
	  void sigint_handler(int sig)
	  {
	      printf("\nCaught SIGINT\n");
	  }
	  
	  int main()
	  {
	      signal(SIGINT, sigint_handler);
	      while (1) {}
	      return 0;
	  }
	  ```