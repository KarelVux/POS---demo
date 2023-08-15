
# General db migration

~~~bash
 dotnet ef database drop  --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext -f
 dotnet ef migrations remove --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext -f
 
 
 dotnet ef migrations add Initial  --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext
 dotnet ef database update --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext




~~~
V2
~~~bash
 dotnet ef database update --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext
 dotnet ef migrations add Initial  --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext
 
 dotnet ef migrations remove --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext -f
 dotnet ef database drop  --project DAL.EF.App --startup-project WebApp --context ApplicationDbContext -f
~~~

# Docker local run
~~~bash
# 2:12:00
docker build -t pos_webapp .
docker run --name pos_webapp --rm -it -p 8000:80 pos_webapp


docker build -t pos_webapp .
docker tag pos_webapp kavuks/pos_webapp:latest
docker push kavuks/pos_webapp:latest