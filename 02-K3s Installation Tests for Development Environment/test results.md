## Instance Types

| Envirenment     | EC2 Type                     | vCPU | Mem     | Processor Type                   |
|-----------------|------------------------------|------|---------|----------------------------------|
| K3s Server-Node | t2.medium | 2    | 4 Gib   | 3.3 GHz Intel Scalable Processor |
| K3s Worker-Node1 | t3a.nano | 2    | 0,5 Gib | 2,5 GHz AMD EPYC  7000           |
| K3s Worker-Node2 | t4g.nano | 2    | 0,5 Gib | 2,5 GHz AWS Graviton2            |


* AMI types:
  Server Node:
    Ubuntu Server 18.04 LTS (HVM), SSD Volume Type - ami-026141f3d5c6d2d0c (64-bit Arm)

  Worker Node1:
    Ubuntu Server 18.04 LTS (HVM), SSD Volume Type - ami-026141f3d5c6d2d0c (64-bit Arm)

  * For t4g EC2 types (t4g.micro/nano)
  Only "64-bit Arm"  AMI's can be selected

## Resource Usage of Nodes

| * K3s succesfully installed  |                                                                   |
|------------------------------|-------------------------------------------------------------------|
| ** Before pod deployment :   |  Server Node uses 1,2-1,3 Gib (30% - 35%) memory and 3%-5% of CPU |
|                              | Worker t3a uses 240 Mi (52%) memory and 1% of CPU                 |
|                              | Worker t4g uses 238 Mi (53%) memory and 1% of CPU                 |
|                              |                                                                   |
| *** After 1 pod deployment : |  Server Node uses 1,4  Gib (37%) memory and 4% of CPU             |
|                              | Worker t3a uses 240 Mi (52%) memory and 1% of CPU                 |
|                              | Worker t4g uses 263 Mi (58%) memory and 1% of CPU                 
|

## Resource Usage of Podes

| Name          | CPU | Memory |
|---------------|-----|--------|
| Nginx-server1 | 0   | 2Mi    |
| Nginx-server2 | 0   | 4Mi    |
| Postgres      | 1m  | 32Mi   |
| webserver     | 1m  | 17Mi   |


## Cost of Nodes

| Envirenment     | EC2 Type   | Hourly | Daily | Monthly |
|-----------------|------------|--------|-------|---------|
| K3s Server-Node | t2.medium  | $0.0464  | $1.11 | $33.41  |
| K3s Worker-Node | t3a.nano   | $0.0047  | $0.11 | $3.38   |
| K3s Worker-Node | t4g.nano   | $0.0042  | $0.10 | $3.02   |