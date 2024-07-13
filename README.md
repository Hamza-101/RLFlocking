# Reinforcement Learning Based Flocking
Centralized Reinforcement Learning Based Flocking

## Cohesion Function
![image](https://github.com/user-attachments/assets/80fe8d3e-5dfb-487e-8a3a-99004cf4d37f)
![image](https://github.com/user-attachments/assets/22336301-e8b8-44d5-bf06-762d736917fc)
<div align="center">
  <img src="https://github.com/user-attachments/assets/65963f25-e4e0-472a-9f10-8aa24e252142" width="500" height="400" />
</div>


## Separation Function
![image](https://github.com/user-attachments/assets/95b0fd56-a86f-487e-87e3-852b8abe7cb5)


## Alignment Function
![image](https://github.com/user-attachments/assets/487c24fc-bafe-4e85-9fa2-6d621317d2b6)
<div align="center">
  <img src="https://github.com/user-attachments/assets/6dcd4b2d-7a80-4c97-8de7-ce0826914ef1" width="500" height="400" />
</div>

# Formulas

## Cohesion Reward Function

The cohesion reward function based on the distance \( d \) is defined as:

\[
R_{\text{Cohesion}}(d) =
\begin{cases} 
-10 & \text{if } d \leq \text{SafetyRadius} \\
\frac{10}{\text{CenterPoint} - \text{SafetyRadius}} \times (d - \text{SafetyRadius}) & \text{if } \text{SafetyRadius} < d < \text{CenterPoint} \\
- \text{CenterPoint} \times (\text{Radius} - d)  & \text{if } \text{CenterPoint} \leq d <  \text{NeighborhoodRadius}
\end{cases}
\]

## Separation Reward

If the agent moves too far away, out of any others' Neighborhood Radius:

\[
R_{\text{Separation}} = -10
\]

## Alignment Reward

The alignment reward \( R_{\text{Alignment}} \) is calculated based on the alignment angle \( \theta \) between the average velocity vector \( \vec{v}_{\text{avg}} \) of neighbors and the agent's velocity vector \( \vec{v}_{\text{agent}} \):

\[
\text{Alignment} = \frac{\arccos\left( \frac{\vec{v}_{\text{avg}} \cdot \vec{v}_{\text{agent}}}{\|\vec{v}_{\text{avg}}\| \cdot \|\vec{v}_{\text{agent}}\|} \right)}{\pi} \quad \theta \in [0, \pi]
\]

\[
R_{\text{Alignment}} = (-20 \times \text{Alignment}) + 10
\]



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
