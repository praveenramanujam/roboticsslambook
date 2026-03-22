# Before You Begin

Welcome.

If you are here, you probably care about robots. Maybe you want to build a drone that navigates a warehouse. Maybe you want a mobile robot that maps a building. Maybe you are simply curious about how a self driving car knows where it is.

Whatever brought you here, we are glad you showed up.

Before we write a single equation or a single line of code, we want to share a story. It is about two ways of building things, and it will shape how you read every chapter in this book.

## The Carpenter and the IKEA Builder

You can build furniture in two ways.

### The IKEA Builder

You get a box.

Inside:
- Pre-cut pieces
- Standard screws
- Step-by-step instructions

You follow: 1 → 2 → 3 → done.

At the end, you have a table.
It works. It looks correct. You feel productive.

But:
- You don't know why it is stable
- You can't modify it
- You can't fix it if something is off
- You can't build a new design without instructions

You built it. But you didn't **understand** it.

### The Carpenter

A carpenter starts with:
- Raw wood
- Tools
- Understanding of structure

She asks:
- What load will this take?
- Where are the weak points?
- What joints will hold over time?

She can:
- Build without instructions
- Adapt to imperfect material
- Fix failures
- Design something new

She doesn't just build. She **understands**.

## Now Replace Furniture with Robotics

Many students approach robotics like IKEA:

1. Install ROS
2. Run a SLAM package
3. Use a perception model
4. Copy a planner

It works.

Until it doesn't.

## When Things Break

And they will.

- The robot drifts
- The map collapses
- The sensor gives noisy data
- The system behaves unpredictably

At that moment, there is no instruction manual.

**The IKEA Robotics Engineer says:**

> "SLAM is not working."
> "The model is bad."
> "The library has a bug."

They look for another package, another tutorial, another shortcut.

**The Carpenter Robotics Engineer says:**

> "My uncertainty model is wrong."
> "My transformation chain has an error."
> "My assumptions don't match reality."

They look for the root cause, the underlying concept, the correct model.

## What Are Your Carpenter Tools?

Not libraries.

| Tool | What it gives you |
|------|-------------------|
| **Probability** | Handling noise and uncertainty |
| **Linear algebra** | Understanding space and motion |
| **Optimization** | Solving for the best estimate |
| **Control and dynamics** | Making systems stable |

These are your chisels, saws, and measuring tools.

## The Trap

IKEA feels fast.

You build quickly. You get results. You feel confident.

But the moment you step outside the instructions, you are stuck.

## The Payoff

Being a carpenter feels slow at first.

You struggle more. You question more. You rebuild more.

But later:

- You debug faster
- You adapt easily
- You build things others cannot

## The Choice

You can assemble systems that work once.

Or you can build systems that work in the real world.

This book is for carpenters.

## How This Book Works

This book teaches you the carpenter's tools. Every chapter builds one more skill in your workshop. By the end, you won't need instructions. You will understand the material deeply enough to build systems that work in the real world, diagnose why they fail, and fix them.

Here is what we promise:

```{admonition} The approach
:class: tip

1. **We build from scratch.** No black boxes. You implement every algorithm yourself, from Bayes rule to bundle adjustment.
2. **We show you the real tools.** Each chapter lists the production libraries (ROS 2, OpenCV, GTSAM, ORB-SLAM3) so you know what engineers use in practice.
3. **We break things on purpose.** Failure modes, edge cases, and wrong assumptions are explored explicitly. You will see algorithms fail and learn why.
4. **We end with something you built.** Every chapter has a capstone exercise where you create something real and useful.

Start with raw material. End with understanding.
```

You don't need to be an expert to start. You need curiosity, a willingness to struggle through the math, and the patience to build understanding one layer at a time.

The first layer starts in {doc}`ch01_estimation_problem`.

Let's go.
