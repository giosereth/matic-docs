---
id: validator-performance-overview
title: Performance Metrics Overview
sidebar_label: Overview
description: Learn about the validator performance metrics that help validators self-regulate
keywords:
  - docs
  - matic
  - polygon
  - validator
  - performance
  - behavior
  - dashboard
  - staking
slug: validator-performance
image: https://wiki.polygon.technology/img/polygon-wiki.png
---

 # **Validator performance framework** 

### **Parameters**

Individual validator performance is measured based on checkpoints signed over a specified period, performed on a rolling basis at each new checkpoint. This is then measured against a benchmark of the total network performance in that same period, as detailed below:

* Monitoring Period (“MP") = previous 700 checkpoints, updated every new checkpoint.
* Take % of checkpoints signed by each validator in the MP and find the median average.
* Multiply the median average by an agreed multiple = Performance Benchmark (PB).
* At each checkpoint, calculate the % of checkpoints signed in the MP by individual validators and measure against the PB.

### **Performance Benchmark**

To transition validators into the process requiring the satisfaction of the proposed potential parameters, there will be a slightly lower benchmark around the first two months while validators become accustomed to the parameters.

* PB1 → 95% of the median average of the last 700 checkpoints signed by the validator set (first 2,800 checkpoints)
* PB2 → 98% of the median average of last checkpoints signed by validator set (continues thereafter)
 
### **Deficient Validator Process:**

* If validator <PB in the MP → Grace Period (“GP”).
* If validator in GP <PB after 700 checkpoints → Notice of Deficiency (“NOD”), enters into Grace Period 2 (“GP2”).
* If the validator in GP2 <PB after 700 checkpoints → Final Notice (“FN”), the validator will be unstaked.

The GP is 700 checkpoints long and allows a validator time to bring its performance back above the PB. If the deficiency is corrected within the GP, there will be no further action. Failure to comply with the GP would result in issuing a public NOD from the Performance Monitor (“PM”). 

The operator would have a 700 checkpoint period to correct the deficiency in GP2. If the deficiency is fixed within the NOD period, then no further action will occur. However, the NOD would remain public. Failure to comply with the GP2 would result in issuing an FN of the community's intent to implement a forced exit procedure by offboarding the validator from the network by unbonding their stake.

### **Forced Unstaking**

The unstaking of the deficient validator would be done as follows:

Call `ForceUnstake` function in Polygon Commitchain Contract: 0xFa7D2a996aC6350f4b56C043112Da0366a59b74c


