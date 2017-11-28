study("TD Sequential 0.1", overlay=true)

tdSetupShort=(((close>close[4]?nz(tdSetupShort[1])+1:0)-1) % 9) + 1
tdSetupLong=(((close<close[4]?nz(tdSetupLong[1])+1:0)-1) % 9) + 1

tdPerfectSetupLong=(tdSetupLong==9 and (low<nz(low[1]) or low<nz(low[2])))
tdPerfectSetupShort=(tdSetupShort==9 and (high>nz(high[1]) or high>nz(high[2])))

tdGoLong=(nz(tdSetupLong[2])==9 and close>nz(high[1]))
tdGoShort=(nz(tdSetupShort[2])==9 and close<nz(low[1]))

plotchar(tdSetupLong==1,char='1',color=red,location=location.abovebar)
plotchar(tdSetupLong==2,char='2',color=red,location=location.abovebar)
plotchar(tdGoLong,char='L',color=green,location=location.belowbar)
plotchar(tdSetupLong==3,char='3',color=red,location=location.abovebar)
plotchar(tdSetupLong==4,char='4',color=red,location=location.abovebar)
plotchar(tdSetupLong==5,char='5',color=red,location=location.abovebar)
plotchar(tdSetupLong==6,char='6',color=red,location=location.abovebar)
plotchar(tdSetupLong==7,char='7',color=red,location=location.abovebar)
plotchar(tdSetupLong==8,char='8',color=red,location=location.abovebar)
plotshape(tdSetupLong==9 and not tdPerfectSetupLong,style=shape.arrowup,text="9",color=green,location=location.belowbar,size=size.auto)
plotshape(tdPerfectSetupLong,style=shape.arrowup,text="9P",color=green,location=location.belowbar,size=size.auto)

plotchar(tdSetupShort==1,char='1',color=green,location=location.abovebar)
plotchar(tdSetupShort==2,char='2',color=green,location=location.abovebar)
plotchar(tdGoShort,char='S',color=red,location=location.belowbar)
plotchar(tdSetupShort==3,char='3',color=green,location=location.abovebar)
plotchar(tdSetupShort==4,char='4',color=green,location=location.abovebar)
plotchar(tdSetupShort==5,char='5',color=green,location=location.abovebar)
plotchar(tdSetupShort==6,char='6',color=green,location=location.abovebar)
plotchar(tdSetupShort==7,char='7',color=green,location=location.abovebar)
plotchar(tdSetupShort==8,char='8',color=green,location=location.abovebar)
plotshape(tdSetupShort==9 and not tdPerfectSetupShort,style=shape.arrowdown,text="9",color=red,location=location.abovebar,size=size.auto)
plotshape(tdPerfectSetupShort,style=shape.arrowdown,text="9P",color=red,location=location.abovebar,size=size.auto)
