# Lecture 5.2: Decentralized Scheduling

![DecentralizedScheduling](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/DecentralizedScheduling.png)

- For centralized: Everything is centralized.
- For distributed: Only knowledge is distributed, not control.
- For decentralized: No sort of centralized control at all. 

As we go from centralized to distributed to decentralized, the complexity increases. Each consumer has their own control and this is a distribution between the consumer and the provider. In the figure you see above, each one of them has their own local scheduler (scheduling is part of control). Consumers have their own scheduler as well. This is a given.

### Interdependency: 
Consider the following example:
- We have two entities, A and B
- Each entity has their own resources that can be used to achieve a goal based on private objective and knowledge to the specific entity
- In some cases, for entity A to achieve a specific goal, it needs to use resources from entity B
- In such a setting, B must coordinate with A to reach an agreement
- In this example, we observe the interdependency between A and B to achieve a specific goal.

This can be between consumers-providers or providers-providers. There is a goal / relevant interrelationship between entities. 

Interdependency is viewed as a goal relevant interrelationship among actions performed by various entities. 
- For instance ID may exist between two or more entities when each has a specific knowledge or data acquisiition that can only be achieved through the use of a shared resource.
- Another ID that may exist is when an entity attempts to acquire specific knowledge or data that is beyond its capabilities, but can be achieved with the help of another entity.

The solution to the ID problem is known as coordination. 

### Coordination
The solution to ID. Coordination between entities is a class of solutions that provides structure and mechanism to the system to deal with the ID problem. 
- Structure: Entity's pattern of communication and decision making that are related to coordination
- Mechanism: Composition of decision points, coordinated control and interaction devices directed to resolve problems associated with IDs.

### Mechanism Design
A field in economics and systems theory that focuses on designing rules, protocols and incentives so that individual entities each acting in their own self-interest will behave in a way that leads to a desired overall system outcome. MD provides rules, communication structures and design protocols that align the entities' local decisions with the global goal. 

**Incentive Compatible Mechanism**: 

Assume that participants are rational. 
- Have a defined valuation function over the possible outcomes (The valuation function depends on their private data)
- Will always act in a way that maximizes their utility

A mechanism determins an outcome and also charges payments from the participants. A mechanism is inceptive compatible: 
- If payments provide incentive to all participants to always truthfully report all private data.

- It's sort of like a penalty, you have to obey the rules.
- "Knowledge" so that global and local solutions do not drift from each other too much
- Car example: No crashes should happen, so you work in your best interest and others. No fines, no die. 

### Formal Mechanism Design Problem
Goal: Implementation of the SCF $f$ (social choice function). 
- Social Choice Function: The is the ultimate goal. The SCF is a function that maps the true types $\theta$ of all agents to the socially optimal outcome $x^*$ and a set of corresponding transfers (payments, $t$). True types are the requirements needed by the consumer. Information provided by an agent. In an auction: valuation in a bid is your true type. Agents are assumed to be rational and are capable of making their own decision. All participants must agree to the SCF.
- Problem: The mechanism design knows the SCF $f$, but cannot directly observe the true types $\theta$. The mechanism must instead rely on the agents' reported strategies, $s$, to determine the final outcome $g$. Valuation in auction: does not reveal the private strategy, but we would know how much it's valued at. We don't know how they decided on a value, but we know what the value is. 
- Implementation: A mechanism successfully implements $f$ if the equilibrium outcome of the game defined by the mechanism results in the outcome $f(\theta)$ for every possible true type profiel $\theta$. We need to prove or disprove that everyone is satisfied with the outcome for themselves.


### Constraints
To ensure that the outcome matches the desired SCF, the mechanism must govern agent behavior. 
- Incentive Compatibility (IC): ensures that agents are **honest**. It forces the designer to align individual self-interest with the social goal. We want to make sure that we get the true values. 
    - Principle: Agents must be incentivized to reveal their true type $\theta_i$ rather than misrepresent it $\tilde{\theta_i}$.
    - Format statement (direct mechanism): Reporting the true type $\theta_i$ must yield a utility $u_i$ greater than or equal to the utility from reporting any other type $\tilde{\theta_i}$. This is basically the same as operating on the Pareto front.
    - Goal: Prevent agents from lying to maximize their own gain.
 
![SCFSummary](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/SummarySCF.png)

### Vickrey-Clarke-Groves (VCG) Mechanism
A general mechanism in MD.
- Its purpose is to solve the problem of private information by designing a system that **ensures agents reveal their true valuations** and that the outcome is **socially optimal (efficient)**.
- The VCG mechanism is a cornerstone because it achieves the **strongest incentive guarantee: Dominant Strategy Incentive Compatibility (DSIC)**.

Defined by two key rules that depend on agents reporting their private valuation $\tilde{v_i}$ for every possible outcome $x$. 
- The allocation rule (efficiency): The mechanism always chooses the outcome that maximizes the sum of agetns' reported valuations (the total social welfare).

$$argmax_{x \in X} \sum_{i=1}^n \tilde{v_i}(x) $$
- Goal: Ensure the outcome is efficient. It creates the largest possible total economic value for society. How does this provide incentive for them to give us true valuations?

The payment rule (IC): The core of VCG is the payment rule, often referred to as the Clarke Pivot Rule. Each agent $i$ is charged a payment $t_i$ equal to the harm or negative externality their participation imposes on the rest of the group. 

$$t_i(\tilde{v}) = [\max_{x \in X} \sum_{j \neq i} \tilde{v_j}(x)] - \sum_{j \neq i} \tilde{v_j}(x^{*})$$
- First term: The highest welfare the rest of the group could've achieved if agent $i$ was absent.
- Second term: The actual welfare the rest of the group achieves under the chosen outcome $x^*$.

![MechDesign1](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/MechDesign1.png)
![MechDesign2](https://github.com/DaraVaram/Cloud-Computing-Infrastructure/blob/main/figures/MechDesign2.png)

