# Introduction to reinforcement learning

## Formalising the RL Problem

At each step t the agent:

- Receives observation $O_t$ (and reward $R_t$)
- Executes action $A_t$

The environment:

- Receives action $A_t$
- Emits observation $O_{t+1}$ (and reward $R_{t+1}$)

## Rewards

- A reward $R_t$ is a scalar feedback signal
- Indicates how well agent is doing at step t - defines the goal
- The agent's job is to maximize cumulative reward

$G_t = R_{t+1} + R_{t+2} + R_{t+1}+ ...$

- We call this **return** (**return** is all about the future, an action can only change the future, can't change the past)

## Values

- Because we can't exactly find $G_t$ so we call the expected cumulative reward, from a state **s**, the **value**

$v(s)=E[G_t|S_t=s]=E[R_{t+1}+R_{t+2}+R_{t+3}+...|S_t=s]$

- Goal is to **maximize value**
- Reward and values define **utility** of state and action
- Returns and values can be defined recursively

$G_t=R_{t+1} + G{t+1}$

$v(s)=E[R_{t+1}+v(S_{t+1})|S_t=s]$

## Maximising value by taking actions

- Goal: select actions to maximize value
- Actions may have long term consequences
- Reward may be delayed
- It may be better to sacrifice immediate reward to gain more long-term reward

- A mapping from states to actions is called **policy**

## Action values

- It is also possible to condition the value on actions:

$q(s, a)= E[G_t|S_t=s, A_t=a]=E[R_{t+1}+R_{t+2}+R_{t+3}+...|S_t=s, A_t=a]$


## Core concepts

- **Environment** (dynamics of the problem)
- **Reward** signal (specifies the goal)
- **Agent**, containing:
    - Agent state
    - Policy
    - Value function estimate
    - Model
