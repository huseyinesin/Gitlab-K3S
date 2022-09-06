| Node |AMI             |Memory Usage         |     Available   | RAM| Type       | CPU   |    RAM  |
|--------------|-----------------------|-------------|--------|-----|----------|---|------|
|              | Alpine-linux          | 57mb        | 930mb  | 1gb | t2.micro | 1 | 1gb  |
| Agent        | Alpine-userdata       | 132mb       | 854mb  | 1gb | t2micro  | 1 | 1gb  |
|              | Amazon linux2         | 192mb       | 767mb  | 1gb | t2micro  | 1 | 1gb  |
|              | Ubuntu                | 248mb       | 595mb  | 1gb | t2micro  | 1 | 1gb  |
|              |                       |             |        |     |          |   |      |
| Server       | Alpine-linux          | 485mb       | 501mb  | 1gb | t2.micro | 1 | 1gb  |
|              | Alpine-linux+1node    | 602mb       | 384mb  | 1gb | t2.micro | 1 | 1gb  |
|              | Alpine-linux+2nodes   | 701mb       | 285mb  | 1gb | t2.micro | 1 | 1gb  |
|              | Alpine-userdata       | 618mb       | 368mb  | 1gb | t2.micro | 1 | 1gb  |
|              | Alpine-userdata+1node | 705mb       | 281mb  | 1gb | t2.micro | 1 | 1gb  |
|              | Amazon linux2         | 950mb       | 928mb  | 2gb | t2.small | 1 | 2 gb |
|              | Ubuntu                | Not working |        | 1gb | t2.micro | 1 | 1gb  |
|              | Ubuntu                | 869mb       | 1000mb | 2gb | t2.small | 1 | 2 gb |
|              | Ubuntu+1node          | 927mb       | 948mb  | 2gb | t2.small | 1 | 2 gb |
|              | Ubuntu+2node          | 1070mb      | 789mb  | 2gb | t2.small | 1 | 2gb  |