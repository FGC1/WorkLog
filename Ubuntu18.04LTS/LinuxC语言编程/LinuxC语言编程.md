# LinuxC语言编程

```C
#include <stdio.h>
#include <stdlib.h>

int main()
{
	char strCmd[100];
	int iCols, iRows;
	printf("请输入窗口大小（行 列）：");
	scanf("%d %d", &iRows, &iCols);
	sprintf(strCmd, "gnome-terminal --geometry=%dx%d", iCols, iRows);
	system(strCmd);
	system("clear");
	return 0;
}
```

