# Control Center

## Summary

Control Center will be software that allows for on-demand deployment of a variety of software packages on GCE. Software will be a django app that's checked into GitHub.

## Purpose

This is to have fun, and show activity on GitHub, and practice something I enjoy just because. It doesn't matter that no one will ever use it.

## High Level Architecture

![HLA](C:\Users\zmcneilly\workspace\control-center\docs\HLA.png)

## Repository Structure

``` repository structure
control-center/
../LICENSE      # License for all projects in repo
../docs         # Common documentation
../salt         # Common salt states, pillars, etc.
../project-name # Project sub-folder
../../docs      # Project documentation
../../salt      # Project salt states, pillars, etc.
```

## Technical Design Decisions

- 2018-07-01 - This will use Django for RESTful API and a web front end
- 2018-07-01 - This will use SaltStack because it's what I'm most familiar with
- 2018-07-01 - This will use GCE because they give a $300 credit.