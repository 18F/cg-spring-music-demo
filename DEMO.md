


---

# Demo

---

## PreDemo prep

New users at https://account.fr-stage.cloud.gov/signup
- Create a fname.lname+dummey@cao.gov user  
  - you'll use this to test all your demos going forward
- Create a fname.lname+demoadmin@cao.gov user
- Create a fname.lname+demodev@cao.gov user

Login to fr-stage as a superuser on CLI

Sub for `doj` below:

```
cf create-org demo-doj -q default
cf set-org-role peter.burkholder+dojadmin@cao.gov demo-doj OrgManager
cf create-space dev -o demo-doj
```


Sign in to staging dashboard as -demoadmin
Invite fname.lname+demodev@cao.gov

## Make sure your demo works



## Demo

Go to [dashboard](https://dashboard.fr-stage.cloud.gov), sign in as `+demoadmin`:
* Go to Org -> Space
* Invite user `+demodev` to org
* Add user to space
* Switch to termin

---

Check out code, checkout demo, open VSCode
```
cd ~/tmp
git clone git@github.com:18F/cg-spring-music-demo.git
cd cg-spring-music-demo
git co pdb/demo-doj
```

---

```
cf api https://api.fr-stage.cloud.gov
cf logout
cf login --sso
```

Login as `+dojdev@cao.org` w/ TOTP

```
cf target -o demo-de
cf apps
```

---

```
./gradlew clean assemble
cf push
```

---

![App Push](./app_push_flow_diagram_diego.png)

---

**Visit app**

---

Demo scaling

```
cf scale -i 2 spring-music
cf scale -i 0 spring-music
cf scale -i 1 spring-music
```

----

Find database

```
cf marketplace
cf marketplace -s aws-rds
```

---

Use a Database


```
cf create-service aws-rds shared-psql spring-music-psql
cf bind-service spring-music spring-music-psql
cf push
```

---

