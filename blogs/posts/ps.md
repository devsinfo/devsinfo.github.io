---
layout: post
title: "ps command"
categories: tutorial
---


## Understanding the `ps` Command and Its Options

The `ps` command in Linux is a powerful tool used to view information about running processes. Below, we outline some key options and provide useful examples for analyzing CPU and memory usage.

## Key Options

- **comm**: Displays only the executable name of the process.
- **cmd**: Shows the command name along with arguments and additional information.
- **user**: Indicates the owner of the process.
- **start**: Displays the start time of the process.
- **pid**: Process ID.
- **ppid**: Parent process ID.
- **%cpu**: CPU utilization percentage.
- **%mem**: Memory utilization percentage.

## Useful Examples

To find the top 15 processes consuming the most CPU, use:
```bash
#ps -eo user,pid,ppid,%mem,%cpu,start,cmd --sort=-%cpu | head -n 15
```
or
```bash
#ps -eo user,pid,ppid,%mem,%cpu,start,comm --sort=-%cpu | head -n 15
```
To identify the top 15 processes using the most memory, use:
```bash
ps -eo user,pid,ppid,%mem,%cpu,start,cmd --sort=-%mem | head -n 15
```
or
```bash
ps -eo user,pid,ppid,%mem,%cpu,start,comm --sort=-%mem | head -n 15
```
---
### Explanation

- **`-eo`**: Specifies the output format, allowing you to customize which columns to display.
- **`--sort=-%cpu`**: Sorts the output by CPU usage in descending order. Similarly, `--sort=-%mem` sorts by memory usage.
- **`head -n 15`**: Limits the output to the top 15 processes.

Using these commands, you can effectively monitor system CPU/MEM performance by identifying resource-heavy processes.

