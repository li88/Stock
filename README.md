# Stock
Stock system

--------------------------------------------------------

测试效果好====通达信买了就涨很精准抄底指标公式

{买了就涨}
趋势线: 3*SMA((CLOSE-LLV(LOW,27))/(HHV(HIGH,27)-LLV(LOW,27))*100,5,1)-2*SMA(SMA((CLOSE-LLV(LOW,27))/(HHV(HIGH,27)-LLV(LOW,27))*100,5,1),3,1);
趋势参考:EMA(趋势线,3),COLORGREEN;
见底信号: 2;
买点准备: IF(趋势线<=10,50,0);
买入时间: IF(CROSS(趋势线,见底信号),100,0),COLOR0099FF,LINETHICK4;
VAR1:=REF((LOW+OPEN+CLOSE+HIGH)/4,1);
VAR2:=SMA(ABS(LOW-VAR1),13,1)/SMA(MAX(LOW-VAR1,0),10,1);
VAR3:=EMA(VAR2,10);
VAR4:=LLV(LOW,33);
VAR5:=EMA(IF(LOW<=VAR4,VAR3,0),3);
主力进场:STICKLINE(VAR5>REF(VAR5,1),0,VAR5,7,0 ),COLORRED;
洗盘:STICKLINE(VAR5<REF(VAR5,1),0,VAR5,7,0),COLORGREEN;

--------------------------------------------------------
同花顺超准超安全指标公式
2015年05月11日 【字体：大 中 小】 人气：215

 ema1:EMA(CLOSE,n1),colorwhite;

ema2:EMA(CLOSE,n2),coloryellow;

ema3:EMA(CLOSE,n3),colorff00ff;

BBI:=(MA(CLOSE,3)+MA(CLOSE,6)+MA(CLOSE,12)+MA(CLOSE,24))/4;

UPR:BBI+n1*STD(BBI,n2),colorred;

DWN:BBI-n1*STD(BBI,n2),colorblue;

var3:=LLV(HIGH,240);

var4:=100*(CLOSE-var3)/var3;

var5:=(CLOSE-LLV(LOW,528))/(HHV(HIGH,528)-LLV(LOW,528))*100;

var6:=(CLOSE-LLV(CLOSE,530))/(HHV(CLOSE,530)-LLV(CLOSE,530))*100;

var7:=0;

var8:=SMA(MAX(CLOSE-REF(CLOSE,1),0),34,1)/SMA(ABS(CLOSE-REF(CLOSE,1)),7,1)*100;

var9:=SMA(MAX(CLOSE-REF(CLOSE,1),0),13,1)/SMA(ABS(CLOSE-REF(CLOSE,1)),13,1)*100;

vara:=BARSCOUNT(CLOSE);

varb:=var8<20 AND var9<23 AND vara>35;

varc:=varb AND COUNT(varb,1)=1;

vard:=EMA(CLOSE,21)-EMA(CLOSE,8);

vare:=EMA(vard,5);

varf:=TROUGHBARS(3,6,1)<4 AND CROSS(vard,vare);

var10:=IF(TROUGHBARS(3,16,1)=0 AND HIGH>LOW+0.04,4,0);

var11:=ZIG(3,6)>REF(ZIG(3,6),1) AND REF(ZIG(3,6),1)<=REF(ZIG(3,6),2) AND REF(ZIG(3,6),2)<=REF(ZIG(3,6),3);

var12:=ZIG(3,6)<REF(ZIG(3,6),1) AND REF(ZIG(3,6),1)>=REF(ZIG(3,6),2) AND REF(ZIG(3,6),2)>=REF(ZIG(3,6),3);

var13:=ZIG(3,22)>REF(ZIG(3,22),1) AND REF(ZIG(3,22),1)<=REF(ZIG(3,22),2) AND REF(ZIG(3,22),2)<=REF(ZIG(3,22),3);

var14:=ZIG(3,22)<REF(ZIG(3,22),1) AND REF(ZIG(3,22),1)>=REF(ZIG(3,22),2) AND REF(ZIG(3,22),2)>=REF(ZIG(3,22),3);

var15:=ZIG(3,51)>REF(ZIG(3,51),1) AND REF(ZIG(3,51),1)<=REF(ZIG(3,51),2) AND REF(ZIG(3,51),2)<=REF(ZIG(3,51),3);

var16:=ZIG(3,51)<REF(ZIG(3,51),1) AND REF(ZIG(3,51),1)>=REF(ZIG(3,51),2) AND REF(ZIG(3,51),2)>=REF(ZIG(3,51),3);

var17:=ZIG(3,72)>REF(ZIG(3,72),1) AND REF(ZIG(3,72),1)<=REF(ZIG(3,72),2) AND REF(ZIG(3,72),2)<=REF(ZIG(3,72),3);

var18:=ZIG(3,72)<REF(ZIG(3,72),1) AND REF(ZIG(3,72),1)>=REF(ZIG(3,72),2) AND REF(ZIG(3,72),2)>=REF(ZIG(3,72),3);

var19:=EMA(CLOSE,2)-EMA(CLOSE,150);

var1a:=EMA(var19,100);

var1b:=2*(var19-var1a);

var1c:=POW(var1b,3)*0.1+POW(var1b,1);

var1d:=SQRT(SQRT(LOW*HIGH*OPEN*CLOSE));

var1e:=EMA(var1d*0.97,3);

var1f:=(HIGH+LOW+CLOSE)/3;

var20:=(var1f-MA(var1f,14))/(0.015*AVEDEV(var1f,14));

var21:=CROSS(var1e,LOW);

买1:=var10;

买:=(var11+var13+var15+var17);

卖:=(var12+var14+var16+var18);

var22:=买1 AND varf AND varc AND var21 AND var4<0 AND var5=0 AND var6=0 AND var20<(-110);

var1:=MA(CLOSE,5);

var2:=MA(CLOSE,10);

var3a:=MA(CLOSE,30);

var4a:=MA(CLOSE,60);

var5a:=EMA(COST(85),7);

var6a:=EMA(COST(15),7);

var7a:=SUM(CLOSE*VOL*100,4)/SUM(VOL*100,4);

var8a:=INTPART(var7a*100)/100;

var9a:=SUM(CLOSE*VOL*100,7)/SUM(VOL*100,7);

varaa:=INTPART(var9a*100)/100;

varba:=SUM(CLOSE*VOL*100,28)/SUM(VOL*100,28);

varca:=INTPART(varba*100)/100;

varda:=EMA(CLOSE,5)-EMA(CLOSE,10);

varea:=EMA(varda,9);

varfa:=(-100)*(HHV(CLOSE,5)-CLOSE)/(HHV(CLOSE,5)-LLV(LOW,5))+100;

var10a:=(-100)*(HHV(CLOSE,10)-CLOSE)/(HHV(CLOSE,10)-LLV(LOW,10))+100;

var11a:=(-100)*(HHV(CLOSE,20)-CLOSE)/(HHV(CLOSE,20)-LLV(LOW,20))+100;

var12a:=(-100)*(HHV(CLOSE,30)-CLOSE)/(HHV(CLOSE,30)-LLV(LOW,30))+100;

var13a:=REF(varea,1);

var14a:=varea;

var15a:=var14a-var13a;

var16a:=REF(varda,1);

var17a:=varda;

var18a:=var17a-var16a;

var19a:=OPEN;

var1k:=CLOSE;

DRAWTEXT(买>0,LOW-0.1,'b'),colorff00ff,;

DRAWTEXT(卖>0,HIGH+0.1,'s'),coloryellow,;

a:=TROUGH(3,10,1);

b:=TROUGHBARS(3,10,1)=0;

底线:DRAWLINE(b,a,b,a,1),colorff00ff;

d:=PEAK(3,10,1);

e:=PEAKBARS(3,10,1)=0;

顶线:DRAWLINE(e,d,e,d,1),coloryellow
--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------

--------------------------------------------------------
