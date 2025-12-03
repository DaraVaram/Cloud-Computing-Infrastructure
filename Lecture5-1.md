# Lecture 5.1: Optimization Problem Modeling

Optimization can exist in different domains. That's pretty much it. 

Optimization problems --> Find the optimum solution subject to the constraints of the problem. 

Def. Linear Programming: A technique that helps us model and find the optimum solution for a given problem. 

The goal is to first understand the problem, and then convert it to an optimization program. 

A company manufactures and sells 2 types of products ‘A’ and ‘B’.
- The cost of production of each unit of ‘A’ and ‘B’ is 200AED and 150 AED
respectively.
- Each unit of ‘A’ yields a profit of 20AED and each unit of ‘B’ yields a profit of
15AED on selling.
- Company estimates the monthly demand of ‘A’ and ‘B’ to be at a max of
500 units.
- The production budget for the month is set at 50,000AED.
- How many unites should the company manufacture in order to earn
maximum profit from its monthly sales of ’A’ and ‘B’

----------------------------------
### Solution: 
1. The "Bang for Your Buck" Test
First, we need to see which product is actually a better money-maker.

* **Product A:** You spend **200 AED** to make **20 AED** profit.
    * *(20 ÷ 200 = 10% return)*.
* **Product B:** You spend **150 AED** to make **15 AED** profit.
    * *(15 ÷ 150 = 10% return)*.

**The Reality:** Both products are exactly the same in terms of value. For every dirham you spend, you get the exact same amount of profit back. It doesn't matter if you buy A or B; the profit will be the same as long as you spend all your money.

2. The "Limit" Test (Budget vs. Demand)
You have two walls that stop you from making infinite products:
1.  **The Money Wall:** You only have 50,000 AED.
2.  **The Demand Wall:** You can only sell 500 units total.

Let's see which wall you hit first.

If you spent *all* your money on the cheapest item (Product B):
* 50,000 AED ÷ 150 cost = **333 units**.

**The Conclusion:** Even if you buy the cheapest item, you can only afford to make 333 units. You will run out of money long before you reach the "500 units" sales limit.
* Because you never get close to 500, **we can completely ignore the "x + y < 500" rule.** It doesn't affect the answer.

3. The Solution
Since both products give the same 10% return, your only goal is to **spend the entire 50,000 AED budget** without leaving any leftover cash sitting uselessly in the bank.

* **Try Product B:** 50,000 ÷ 150 = 333.33 units. You can't make 0.33 of a unit. If you make 333, you have money left over that isn't earning profit.
* **Try Product A:** 50,000 ÷ 200 = **250 units exactly**.

Because Product A fits perfectly into your budget with zero wasted cash, it is the "cleanest" and best answer.

**Final Answer:**
You should manufacture **250 units of A**. This uses exactly 50,000 AED and gives you exactly 5,000 AED profit.

### Essential Elements of Optimization
- Decision Variables
- Objective Function (Such as maximize profits, minimize cost, minimize time)
- Constraints

### Mapping into Scheduling Problem
- Requests: A set of tasks to be executed by resources. It can be logical or physical. Each operation may have its own requirements.
- Resources: Logical / physical elements, provided with capabilities to execute requests according to the tasks requirements
- Constraints: Conditions that must be considered in scheduling requests into the resources. They may be task-based, request-based, resource-based, or a combination
- Objective: Criterion for which the scheduling problem performance is evaluated.
    - This is the quality to achieve. Constraints are environment related. From the environment, you derive constraints. Break down to understand constraints.
 
Task: Creating a VM, for example. 


### Example Scheduling Optimization Problem
- Objective: Minimize energy consumption
- Constraint 1: min. number of cores required is satisfied
- Constraint 2: min. CPU speed required as satisfied
- Constraint 3: min. memory capacity is satisfied
- Constraint 4: min. processor architecture is satisfied
- Constraint 5: Tasks demand for storage resources type is satisfied
- Constraint 6: Storage speed
- Constraint 7: Storage capacity
- Constraint 8: Network bandwidth
- Constraint 9: Only one computational resource
- Constraint 10: Storage allocation to storage resource
- Constraint 11: Network allocation to task
- Constraint 12: Meeting deadline
- Constraint 13: Resource cannot execute two tasks at a specific timeframe

Big objective function. Big constraints written mathematically as well. I think that what will come in the final is a written problem where you'd have to derive the constraints, the objective, etc... based on the notation. 

A task requiring a VM with 6 cores and 128GB memory cannot be assigned to another VM with less specifications. 


## Example from the class: 
Assume I have two hosts with the following specs: 
- Host A contains 10 processing elements (PE) and 48GB RAM
- Host B has 20 PEs and 64GB RAM
- The cost for using PE/Hour is 1AED and the profit is 0.5AED (PE/Hour)
- 3 VMs have the following requirements and are to be allocated on the available hosts.
   - VM1: 5 PE, 16GB
   - VM2: 10 PE, 24GB
   - VM3: 5 PE, 24GB

Write the constraints that ensures the allocation of the host PE and RAM resource to meet the minimum requirement of a VM. Provide your answer in a general constraint modeling form. 

Solution: You want the following objective. First, we use an indicator function which will be our decision variable x. 

If a VM is assigned to a host, then x = 1. Otherwise, 0. We want to ensure that 5VM1 + 10VM2 + 5VM3 <= 10 and 5VM1 + 10VM2 + 5VM3 <= 20. Similarly, we have 16VM1 + 24VM2 + 24VM3 <= 48 and <= 64. 
