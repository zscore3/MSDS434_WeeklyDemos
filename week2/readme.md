GCP:  
sudo apt update  
sudo apt install git  
git clone https://github.com/zscore3/MSDS434_Final_Project.git  
cd MSDS434_Final_Project  
cat test.html  
git init  
git branch -M main  
git remote remove origin  
git remote add origin https://zscore3:<<TOKEN>>@github.com/zscore3/MSDS434_Final_Project.git  
vi test.html  
>> ENTER ESC  
:wq  
git config --global user.email "jrcogsw@gail.com"  
git config --global user.name "Jack Cogswell"  
git commit -a -m "check the html"  
git push -u origin main  
  
  
  
Git Token:  
<<TOKEN>>  
  
  
  
AWS:  
sudo yum install git  
git clone https://github.com/zscore3/MSDS434_Final_Project.git  
cd MSDS434_Final_Project  
cat test.html  
git init  
git branch -M main  
git remote remove origin  
git remote add origin https://zscore3:<<TOKEN>>@github.com/zscore3/MSDS434_Final_Project.git  
vi test.html  
>> ENTER ESC  
:wq  
git config --global user.email "jrcogsw@gmail.com"  
git config --global user.name "Jack Cogswell"  
git commit -a -m "check the html"  
git push -u origin main  
  
