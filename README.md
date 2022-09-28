---
title: Linux Cheat Sheet
author: "Julio Flores"
date: "2022-09-28"
output: flexdashboard::flex_dashboard
---

```{r setup, include=FALSE}
library(flexdashboard)
```

Column 1
--------------------------------------------------

### Chart A

```{r}
```

Column 2
--------------------------------------------------

### Chart B

```{r}
```

### Chart C

```{r}
```


# Linux Cheat Sheet

<!-- Tree image inline with html -->




This is a collection of notes about Linux. It is not a complete guide, perhaps this is a good place to remember some of the most important commands and concepts of Linux, and not an starting point for those who want to learn Linux from scratch.

## Table of Contents

- [Table of Contents](#table-of-contents)
- [Linux Achitecture](./achitecture-overview/README.md#linux)
  - [Levels and Layers in Linux](./achitecture-overview/README.md#levels-and-layers-in-linux)
    - [Hardware: Level 1](./achitecture-overview/README.md#hardware-level-1)
    - [Kernel: Level 2](./achitecture-overview/README.md#kernel-level-2)
    - [User Process: Level 3](./achitecture-overview/README.md#user-process-level-3)
  - [Hardware: Main Memory](./achitecture-overview/README.md#hardware-main-memory)
  - [Kernel: System Calls](./achitecture-overview/README.md#kernel-system-calls)
    - [Process Management](./achitecture-overview/README.md#process-management)
    - [Memory Management](./achitecture-overview/README.md#memory-management)
    - [Device Drivers](./achitecture-overview/README.md#device-drivers)
    - [System Calls](./achitecture-overview/README.md#system-calls)
    - [User Space](./achitecture-overview/README.md#user-space)
    - [Users](./achitecture-overview/README.md#users)
- [Linux Scentials Commands](./commands/README.md)
  - [The shell](./commands/README.md#the-shell)
  - [The standard input, output and error](./commands/README.md#the-standard-input-output-and-error)
    - [Standard input (stdin)](./commands/README.md#standard-input-stdin)
    - [Standard output (stdout)](./commands/README.md#standard-output-stdout)
    - [Standard error (stderr)](./commands/README.md#standard-error-stderr)
  - [Arguments](./commands/README.md#arguments)
    - [--help](./commands/README.md#help)
  - [Wildcards](./commands/README.md#wildcards)
  - [Commands](./commands/README.md#commands)
    - [Moving around](./commands/README.md#moving-around)
    - [Creating and removing files and directories](./commands/README.md#creating-and-removing-files-and-directories)
    - [Searching for Files](./commands/README.md#searching-for-files)
      - [Find](./commands/README.md#find)
      - [Grep](./commands/README.md#grep)
      - [Less](./commands/README.md#less)
      - [Pipe](./commands/README.md#pipe)
      - [Redirect](./commands/README.mdredirect)
      - [Some useful commands](./commands/README.md#some-useful-commands)
- [Change Password (passwd)](./change-password/README.md#change-password-passwd)

## 
