#include <stdio.h>
#include <wiringPi.h>
#include <lcd.h>

#define LCD_RS  25               //Register select pin
#define LCD_E   24               //Enable Pin
#define LCD_D4  23               //Data pin 4
#define LCD_D5  22               //Data pin 5
#define LCD_D6  21               //Data pin 6
#define LCD_D7  14               //Data pin 7
int main(){
	int i,count,op[100],j=0,k,sign[100],l,m=0,n=0;
	float h[100],res;
	char arr[100],num[100][100];		
	int lcd;               
    wiringPiSetup();        
    lcd = lcdInit (2, 16, 4, LCD_RS, LCD_E, LCD_D4, LCD_D5, LCD_D6, LCD_D7, 0, 0, 0, 0);
    while()
    {
    lcdPosition(lcd, 5, 0); 
    lcdPuts(lcd, "Simple");
	lcdPosition(lcd, 3, 1);
	lcdPuts(lcd, "Calculator");
	printf("Enter the Calculation\n");
	for(i=0;i<100;i++)
	{
		scanf("%c",&arr[i]);
		if(arr[i]=='=')
		{
			count=i;
		    break;
		}
	}
	lcdClear(lcd);
	for(i=0;i<count;i++)
	{
		lcdPosition(lcd, i, 0); 
		if(arr[i]=='+'||arr[i]=='-'||arr[i]=='*'||arr[i]=='/'||arr[i]=='=')
		{
			lcdPrint(lcd, "%c",arr[i]);
		}
		else
		{
			lcdPrint(lcd,"%c",arr[i]);
		}
	}
    
    for(i=0;i<count+1;i++)
	{
		if(arr[i]=='+'||arr[i]=='-'||arr[i]=='*'||arr[i]=='/'||arr[i]=='=')
		{
			op[j]=i;
			sign[j]=arr[i];
			j=j+1;
		}
	}	
	for(n=0;n<j;n++)
	{	
		if(n==0)
		{
			for(k=0;k<op[n];k++)
			{
				num[n][k]=arr[k];
			}
		}
		else 
		{
			for(k=0;k<op[n]-op[n-1]-1;k++)
			{
				num[n][k]=arr[op[n-1]+1+k];
			}
		}
		
	}
	
	for(i=0;i<j;i++)
	{
		if(i==0)
		{
			sscanf(num[i], "%g", &h[i]);
		}
		else 
		{
			sscanf(num[i], "%g", &h[i]);
		}	
	}
	k=0;
	for(i=0;i<j-1;i++)
	{
		switch(sign[k])
		{
		case '+':
			res=h[i]+h[i+1];
			break;
		case '-':
			res=h[i]-h[i+1];
			break;
		case '*':
			res=h[i]*h[i+1];
			break;
		case '/':
			res=h[i]/h[i+1];
			break;
		}
		h[i+1]=res;
		k=k+1;
	}
	printf("result=%g\n",res);
	lcdPosition(lcd, 0, 1); 
    lcdPrint(lcd, "Result:%0.6g",result);
    sleep(4);
	lcdClear(lcd);
	
		
	}
	return 0;
}
