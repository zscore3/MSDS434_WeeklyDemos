Week 4  
GCP  
1. Create new project and select it  
2. go into cloud shell  
3. follow instructions until 2015_12.csv  
cp 201501.csv 201501.bck  
rm *.csv  
python  
f = open('201501.bck').readlines()  
f[0]  
f[1]  
fout=open('201501.csv','w')  
for i in range(5000):  
	fout.write(f[i])  
exit()  
cat 201501.csv  
4. Create a bucket  
gsutil -m cp *.csv gs://jackcogswellweek4t3  
bq mk jcogsweek4  
bq load --autodetect --source_format=CSV jcogsweek4.flight_auto gs://jackcogswellweek4t3/201501.csv  
5. Go to BigQuery  
SELECT *  
FROM jcogsweek4.flight_auto  
WHERE Reporting_Airline = 'AA';  
  
AWS  
Click query data  
delete out tabs (start from scratch)  
click into sample data (tickit) to open the sample notebook  
run any one of them and present the result  
Create a new query notebook  
SELECT * FROM tickit.sales LIMIT 10;  
view schema  
delete connection just to be safe  
  
