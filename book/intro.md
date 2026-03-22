# Estimation, Mapping & Localization

An interactive textbook on the mathematics and algorithms behind robot localization, mapping, and SLAM. Every concept is implemented from scratch in Python, running directly in your browser.

No installation. No black boxes. Just understanding.

---

## Who is this for?

You are curious about how robots know where they are. Maybe you want to build a drone that navigates a warehouse, a mobile robot that maps a building, or you simply want to understand how a self driving car localizes itself.

You have some background in linear algebra and basic programming. Everything else, we build together from the ground up.

## How to read this book

Each chapter combines **written explanations** with **live, editable code** that runs directly in your browser through JupyterLite.

- **Read** the theory and intuition
- **Run** the code cells to see results
- **Edit** the code, change parameters, break things, build intuition
- **Build** the capstone exercise at the end of each chapter

The chapters build on each other. Start from the beginning. If you skip ahead, you may miss a concept that later chapters assume you know.

Before diving into the math, read the {doc}`Prologue <chapters/ch00_the_carpenter>`. It explains the philosophy behind this book and why we build everything from scratch.

---

## Structure

| Part | Chapters | What you will learn |
|------|----------|-------------------|
| Prologue | 0 | Why we build from scratch |
| I | 1 | The estimation mindset |
| II | 2, 3, 4 | Linear algebra, coordinate frames, 3D rotations |
| III | 5, 6, 7, 8 | Probability, Gaussians, sampling, uncertainty, observability |
| IV | 9, 10 | Bayes filter, optimization view of estimation |
| V | 11, 12, 13, 14 | Motion models, sensor models, data association, simulation |
| VI | 15, 16, 17, 18 | Discrete Bayes, Kalman filter, EKF/UKF, particle filters |
| VII | 19, 20, 21, 22 | SLAM structure, maps, EKF-SLAM, FastSLAM |
| VIII | 23, 24, 25, 26 | Nonlinear least squares, factor graphs, graph SLAM, loop closure |
| IX | 27, 28, 29, 30 | System architecture, real time vs batch, multi-session, alignment |
| X | 31, 32, 33 | Camera models, multiview geometry, visual front end |
| XI | 34, 35, 36, 37, 38 | Visual odometry, monocular/stereo SLAM, ORB-SLAM, bundle adjustment |
| XII | 39, 40 | IMU modeling, visual inertial fusion |

---

Start with the {doc}`Prologue <chapters/ch00_the_carpenter>`, then continue to {doc}`Chapter 1 <chapters/ch01_estimation_problem>`.
