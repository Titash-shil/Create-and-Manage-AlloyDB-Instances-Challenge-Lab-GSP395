# Create and Manage AlloyDB Instances: Challenge Lab || [GSP395](https://www.cloudskillsboost.google/focuses/50123?parent=catalog) ||

# # Like, comment, share & Don't forget to subscribe [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN) 👍😄🤝

### Run the following Commands in CloudShell

---

```bash
export REGION=
```

```bash


gcloud beta alloydb clusters create lab-cluster \
    --password=Change3Me \
    --network=peering-network \
    --region=$REGION \
    --project=$DEVSHELL_PROJECT_ID

gcloud beta alloydb instances create lab-instance \
    --instance-type=PRIMARY \
    --cpu-count=2 \
    --region=$REGION  \
    --cluster=lab-cluster \
    --project=$DEVSHELL_PROJECT_ID

gcloud alloydb instances create lab-instance-rp1 \
  --cluster=lab-cluster \
  --region=$REGION \
  --instance-type=READ_POOL \
  --cpu-count=2 \
  --read-pool-node-count=2

gcloud beta alloydb backups create lab-backup --region=$REGION  --cluster=lab-cluster
```
---


### - Go tO `VM Instance` from [Here](https://console.cloud.google.com/compute/instances?referrer=search&project=)

### - Go to `AlloyDB` from [Here](https://console.cloud.google.com/alloydb/clusters?referrer=search&project=)



```bash
export ALLOYDB=
```

```bash
echo $ALLOYDB  > alloydbip.txt 
```


```bash
psql -h $ALLOYDB -U postgres
```

---
- ## **user's password** 

```
Change3Me
```
---

```bash
CREATE TABLE regions (
    region_id bigint NOT NULL,
    region_name varchar(25)
) ;
ALTER TABLE regions ADD PRIMARY KEY (region_id);
```

```bash
CREATE TABLE countries (
    country_id char(2) NOT NULL,
    country_name varchar(40),
    region_id bigint
) ;
ALTER TABLE countries ADD PRIMARY KEY (country_id);
```

```bash
CREATE TABLE departments (
    department_id smallint NOT NULL,
    department_name varchar(30),
    manager_id integer,
    location_id smallint
) ;
ALTER TABLE departments ADD PRIMARY KEY (department_id);
```

```bash
INSERT INTO regions VALUES ( 1, 'Europe' );
INSERT INTO regions VALUES ( 2, 'Americas' );
INSERT INTO regions VALUES ( 3, 'Asia' );
INSERT INTO regions VALUES ( 4, 'Middle East and Africa' );

```

```bash
INSERT INTO countries VALUES ('IT', 'Italy', 1 );
INSERT INTO countries VALUES ('JP', 'Japan', 3  );
INSERT INTO countries VALUES ('US', 'United States of America', 2  );
INSERT INTO countries VALUES ('CA', 'Canada', 2  );
INSERT INTO countries VALUES ('CN', 'China', 3  );
INSERT INTO countries VALUES ('IN', 'India', 3 );
INSERT INTO countries VALUES ('AU', 'Australia', 3  );
INSERT INTO countries VALUES ('ZW', 'Zimbabwe', 4  );
INSERT INTO countries VALUES ('SG', 'Singapore', 3 );
```

```bash
INSERT INTO departments VALUES (10, 'Administration', 200, 1700 );
INSERT INTO departments VALUES (20, 'Marketing', 201, 1800);
INSERT INTO departments VALUES (30, 'Purchasing', 114, 1700 );
INSERT INTO departments VALUES (40, 'Human Resources', 203, 2400);
INSERT INTO departments VALUES (50, 'Shipping', 121, 1500);
INSERT INTO departments VALUES (60, 'IT', 103, 1400);
```


---
---


# Congratulations ..!!🎉  You completed the lab shortly..😃💯

# *Well done..!* 👏

# Thank you for visiting.... :) 🗯️

# [Qwiklab_Explorers_ts](https://youtube.com/@titashshil?si=RgamNu1dc9jVIbJN)
