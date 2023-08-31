# Plot a gas concentration figure by daily mean and monthly mean.

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import datetime

temp=pd.read_csv('/Users/ashley071010/s2_0428.csv',usecols=['temp'])
RH=pd.read_csv('/Users/ashley071010/s2_0428.csv',usecols=['rh'])
PM25=pd.read_csv('/Users/ashley071010/s2_0428.csv',usecols=['PM2.5'])

TP=np.array(temp['temp']) 
RH2=np.array(RH['rh']) 
PM252=np.array(PM25['PM2.5']) 

fig=plt.figure(figsize=(12,6))
labals=['13:47:47','13:48:17','13:48:47','13:49:17','13:49:47']  
x=[0,30,60,90,120] #Time label of figure
plt.xticks(x,labels)
ax = plt.gca()
ax.grid(which='major', axis='both', linestyle='-') 
plt.title('Temperature of S2 at 13:47:47-13:49:47')
plt.xlabel('Time')
plt.ylabel('Temperature($^o$C)')
plt.plot(TP)
#plt.plot(RH2, label="RH(%)")
#plt.plot(PM252, label="PM2.5")
plt.legend(loc = "best", fontsize=15)

#-------------------------------------------------------------------------------------------------#

fig=plt.figure(figsize=(12,6))
labels=['13:47:47','13:48:17','13:48:47','13:49:17','13:49:47']
x=[0,30,60,90,120]
plt.xticks(x,labels)
ax = plt.gca()
ax.grid(which='major', axis='both', linestyle='-') 
plt.title('Humidity of S2 at 13:47:47-13:49:47')
plt.xlabel('Time')
plt.ylabel('Humidity(%)')
plt.plot(RH2)
plt.legend(loc = "best", fontsize=15)
