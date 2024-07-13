# Reinforcement Learning Based Flocking
Centralized Reinforcement Learning Based Flocking

## Cohesion Function

$$
R_{\text{Cohesion}}(d) =
\begin{cases} 
-10 & \text{if } d \leq \text{SafetyRadius} \\
\frac{10}{\text{CenterPoint} - \text{SafetyRadius}} \times (d - \text{SafetyRadius}) & \text{if } \text{SafetyRadius} < d < \text{CenterPoint} \\
- \text{CenterPoint} \times (\text{NeighborhoodRadius} - d)  & \text{if } \text{CenterPoint} \leq d <  \text{NeighborhoodRadius}
\end{cases}
$$

## Separation Function
If the agent moves too far away, out of any others' Neighborhood Radius:

$$
R_{\text{Separation}} = -10
$$

## Alignment Function

$$
\text{Alignment} = \frac{\arccos\left(\frac{\vec{v}_{\text{avg}} \cdot \vec{v}_{\text{agent}}}{\|\vec{v}_{\text{avg}}\| \cdot \|\vec{v}_{\text{agent}}\|} \right)}{\pi} \quad \theta \in [0, \pi]
$$

$$
R_{\text{Alignment}} = (-20 \times \text{Alignment}) + 10
$$



## Architecture
<div>
      <img src="https://github.com/user-attachments/assets/25fd4d5f-ccd3-4e45-a8a6-2a5eef10627f" />
</div>

- OS: Windows-10-10.0.22631-SP0 10.0.22631
- Python: 3.11.4
- Stable-Baselines3: 2.2.1
- PyTorch: 2.0.0+cpu
- GPU Enabled: False
- Numpy: 1.23.5
- Gymnasium: 0.29.1
- OpenAI Gym: 0.15.7
