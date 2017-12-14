


---

# Demo

```
./gradlew clean assemble
cf push
```

---

![ATOs](./cg-faster-atos.png)


---

```
cf create-service aws-rds pgsql-shared spring-music-pgsql
cf bind-service spring-music spring-music-pgsql
cf restage spring-music
```

---

# Case Studies

- FDIC
- Dept of Ed
- FEC

---

# Next

- Try a sandbox
- Learn more: DigitalGov videos
- Sign a prototyping IAA

git@github.com:18F/cg-spring-music-demo.git