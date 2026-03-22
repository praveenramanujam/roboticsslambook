# Chapter 1: The Estimation Problem in Robotics

## 1.1 What localization and mapping are really solving


```{admonition} What you will understand
:class: tip

- Why robots cannot rely on a single "best guess" and must maintain beliefs over possible states
- The three types of truth in robotics: kinematic, sensed, and estimated
- Why estimation is unavoidable in any real robotic system

**Real world application:** You will be able to explain why a GPS reading of (37.7749, -122.4194) does not mean the robot is exactly there, and what a robot should do instead.
```

A robot moving through the world faces a deceptively simple question: *where am I?*

To answer it, the robot must reason about three things simultaneously: its own motion (what it commanded its motors to do, and how much to trust that), its sensors (what it measured about the world, and how noisy those measurements are), and the world itself (what is out there, and where).

Localization is the problem of estimating the robot's pose (position + orientation) given a known map. Mapping is the problem of building that map given a known trajectory. **SLAM** (Simultaneous Localization and Mapping) is solving both at once, with neither given.

## 1.2 State, observation, control, and belief

We formalize the robot's situation with four concepts.

The **state** $\mathbf{x}_t$ captures everything about the world we care about at time $t$. Typically this is the robot's pose, and possibly landmark positions. The **control** $\mathbf{u}_t$ is the action the robot took (e.g., "move forward 1m, turn 30°"), which drives the state from $\mathbf{x}_{t-1}$ to $\mathbf{x}_t$. The **observation** $\mathbf{z}_t$ is what the sensors reported (a laser range measurement, a camera image feature) and serves as evidence about the state.

The **belief** $\text{bel}(\mathbf{x}_t)$ is the robot's probability distribution over all possible states. This is the actual answer the system maintains: not *"I am at (3.2, 1.7)"* but *"I am probably near (3.2, 1.7) with this uncertainty."* The key insight is that we never know the state exactly. We maintain a belief.

## 1.3 Deterministic world vs uncertain world

Consider a robot that drives forward 1 meter. In a deterministic model:

$$\mathbf{x}_t = \mathbf{x}_{t-1} + \Delta x$$

This is simple and clean, but wrong. Real wheels slip. Motors have friction. The floor is uneven. After 100 steps of "1 meter forward," the robot could be anywhere from 95m to 105m from its start.

A probabilistic model acknowledges this reality:

$$\mathbf{x}_t \sim p(\mathbf{x}_t \mid \mathbf{x}_{t-1}, \mathbf{u}_t)$$

The state at time $t$ is drawn from a distribution conditioned on where we were and what we did. This is the **motion model**, and it has noise built in by design.

## 1.4 Geometry vs probability and why both are required

Geometry and probability are not alternatives. They work together. Geometry tells us *what* the measurements mean: if a laser sees a wall at 3.2m at bearing 45°, where is that wall in the world frame? Probability tells us *how much to trust* those measurements and the motion commands.

Without geometry, you cannot interpret sensor data. Without probability, you cannot fuse noisy data or propagate uncertainty through a sequence of measurements. SLAM needs both in equal measure.

## 1.5 Kinematic truth, sensed truth, and estimated truth

There are three distinct realities in a SLAM system:

| Truth | Description |
|-------|-------------|
| **Kinematic truth** | Where the robot actually is (never known) |
| **Sensed truth** | What the sensors reported (noisy, biased) |
| **Estimated truth** | Our best inference given all evidence so far |

The goal is to make estimated truth as close to kinematic truth as possible. Sensors give us access to *some* information about kinematic truth, but always corrupted by noise. Estimation is the process of reasoning backward from sensed truth to an informed belief about kinematic truth.

## 1.6 Failure of naive deterministic thinking

Suppose we ignore uncertainty and simply integrate odometry commands:

$$\mathbf{x}_t = \mathbf{x}_0 + \sum_{i=1}^{t} \mathbf{u}_i$$

This approach is called **dead reckoning**. It works for short distances, but errors accumulate. Small per-step errors add up, and because they compound, the total error grows faster than linearly. After enough steps, the robot's estimate of its own position can be completely wrong.

The failure mode is silent: the robot has high confidence in a position that is far from the truth. A probabilistic estimator, by contrast, grows its uncertainty ellipse over time. It *knows* it does not know, and communicates that honestly.

## 1.7 Why estimation becomes unavoidable

There is no way around uncertainty in real systems. It enters from multiple directions: every physical sensor has noise (thermal, quantization, calibration error); our motion model is an approximation of real physics; we can only measure projections of the world, not the full state; and even if we could model everything perfectly, we cannot store infinite precision.

Estimation is the discipline that tells us how to act rationally under these constraints. The next chapters build the mathematical tools (linear algebra, geometry, and probability) needed to do this precisely.
