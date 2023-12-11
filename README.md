# Welcome to Mergify interactive demo! 🦾

## How to use this repository?

This repository is a live, forkable demo of Mergify where you can start various
scenario.

In order to make it work, you'll need to follow those steps:

1. [Fork the repository](https://github.com/Mergifyio/demo/fork);
2. Go to the [Mergify dashboard](https://dashboard.mergify.com/);
3. Add Mergify to your organization and select the demo that you just forked;
4. If you already had Mergify installed, click on "Edit repository list" at
   the top of the dashboard and add the demo repository.

Need more help to deploy Mergify on your forked repository? [Check our getting
started docs](https://docs.mergify.com/getting-started/).

Now you can test the various scenarios offered by this repository.

## Introduction to Merge Queue

If you never heard of a merge queue, the first thing to do is to take a look at
[merge queue introduction](https://docs.mergify.com/merge-queue/) which will
cover the basics of a merge queue.

## Repository Merge Queue Setup

This repository has [3 different merge
queues](https://docs.mergify.com/merge-queue/multi/) configured, to make it
more spicy.

This is also close to typical real world scenario, where you might have pull
requests being merged with different policies.

You can read the full configuration in the [`.mergify.yml`](.mergify.yml) file
of this repository.

The 3 queues are:

1. `hotfix`: this is the queue where you would typically route pull requests
   that are urgent and needs to be merged as soon as possible. Pull request can
   enter this queue if they have the `hotfix` label attached.

2. `default`: the default queue for routing any pull request. The pull requests
   entering this queue are tested in parallel using [speculative
   checks](https://docs.mergify.com/merge-queue/speculative-checks/), with up
   to 5 running tests in parallel.

3. `lowprio`: the queue for routing low priority PRs. The pull requests
   entering this queue are tested in
   [batches](https://docs.mergify.com/merge-queue/batches/).
