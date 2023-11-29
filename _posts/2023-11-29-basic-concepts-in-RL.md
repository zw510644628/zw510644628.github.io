> State： 一个agent相当于environment的一个状态
>
> State space：状态空间，即状态值的集合
>
> Action：对于每个state的可能的动作
>
> Action space of a state：动作集合，但依赖于状态
>
> State transition：当采取一个action时，agent可以从一个state移动到另一个state，定义了agent和environment的一种交互行为，可以用表格表示存在的所有行为，但是只能表示确定性的情况，即deterministic
>
> State transition probability：用概率描述state transition
>
> Policy：策略，一般用$\pai$表示，策略可能是不确定的，stochastic，可以用表格表示
>
> Reward：采取action之后所获得的一个实数，可以用正数代表encouragement，负数表示punishment；reward可以被理解成一种human-machine interface
>
> Trajectory：a state-action-reward chain
>
> Return：沿着trajectory所得到的所有reward总和，通过return可以评价哪个policy好
>
> Discounted return：discount rate $\gamar$，折扣率，避免return发散掉，控制短视和远视
>
> Episode：也是一个trajectory，有限步的，会stop，这样的任务也被称为episode tasks，有些任务是没有terminal states，意味着agent和environment的交互将会永远持续下去，这样的任务称为continuing tasks
>

### Markov decision process (MDP)

Key elements of MDP

1. Sets：state、action、reward
2. Probability distribution：state transition probability、reward probability
3. Policy
4. Markov property：和历史无关的性质

<img width="219" alt="image" src="https://github.com/zw510644628/zw510644628.github.io/assets/50043212/05e4308a-d6dd-4641-84ee-dc0e4b7fe803">
