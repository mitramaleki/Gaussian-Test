# My Bilby Gaussian Test (Just Trying Things Out)

Okay so this is just me playing around with Bilby's parameter estimation. The whole idea comes from their example code - I just wanted to try it myself to see how it works.

## What This Does
Basically, we're trying to find:
- The average (μ)
- How spread out the data is (σ)

When we don't know these numbers, Bilby helps us make good guesses by:
1. Testing thousands of possible (μ, σ) combinations
2. Keeping the ones that match our data
3. Throwing out the bad ones
4. Showing us the most likely answers

## Where I Got This
All credit goes to the Bilby team's example:
[bilby/examples/core_examples/gaussian_example.py](https://git.ligo.org/lscsoft/bilby/blob/master/examples/core_examples/gaussian_example.py)

I just copied their idea and tweaked some things to understand it better.

## My Test Run
Made some fake data where:
- True average (μ) = 5
- True spread (σ) = 2
- 200 data points

Here's what Bilby found:

<img width="539" height="545" alt="{47BE6B35-AC51-4A56-B5F5-BC341B89DACD}" src="https://github.com/user-attachments/assets/f29c526e-8592-4c59-b71f-aa816a909263" />


*Results:*
- μ ≈ 4.86 (close to the real 5)
- σ ≈ 2.00 (exactly right!)

## What I Actually Did
1. Used their basic method but with my own numbers
2. Played with the code to see how it works
3. Changed some settings to see what happens
4. Added comments so I'd remember what everything does

## How To Run This Shit

1. **Install WSL** (Google it if you don't know - takes 3 reboots)

2. **Open Ubuntu terminal** and run these exact commands:
```bash
# Basic setup
sudo apt update
sudo apt install python3 python3-pip

# Get conda because pip will make you go crazy trust me
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh
source ~/.bashrc

 install what we need
conda install -c conda-forge bilby numpy matplotlib jupyter
#I prefer this sweetie
jupyter notebook
#google the rest and enjoy :D
