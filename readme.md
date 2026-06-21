# Wrench & Homebrew — example repository

## Highlights

To publish wrench on homebrew, we have only 2 ways: create our own `tap` or use `homebrew-core`.
Both methods allow users to download wrench via `brew install wrench`, but there are differences.

1. Using `homebrew-core`, we give access to wrench to users from all over the world, but for this we need to open PR in
   the
   `Homebrew/hombrew-core` repository with our hands or using **CI** after each update, and wait for merge from the
   organization's maintainers.
   <br><br>
   Since manual verification can take a long time, we can avoid `homebrew-core` using by
   our own **tap repository**. An example of such a repository — `scobca/homebrew-wrench`
   <br><br>

2. For the second method, we need to take a few steps:
    - Create special `homebrew-wrench` repo (as an example you can watch this one)
    - Create GitHub PAT-token with access to this repo and add it as secret to `ryukzak/wrench` with name
      `HOMEBREW_TAP_TOKEN`

   After creating the repository work with it will be completed, and then CI from `ryukzak/wrench` will do everything
   for you

---

## Installation from custom homebrew tap

In order to install wrench on your PC, you need to do the following:

```bash
# Add the tap
brew tap ryukzak/wrench

# Install wrench
brew install wrench

# Verify installation
wrench --version
```
#### NB: for the test you can use `brew tap scobca/wrench`, I'm build and published wrench v0.0.4.7 here


## Updates

The tap is automatically updated when new releases are published on GitHub.

---