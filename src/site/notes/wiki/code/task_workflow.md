---
{"dg-publish":true,"permalink":"/wiki/code/task_workflow/","title":"待办、记录、日历的工作流","tags":["life"],"created":"2025-06-21T17:59:44.128+08:00"}
---


# 基于warriors的工作流

我是指taskwarrior 和 timewarrior

## cal

khal 添加新任务

```
Usage: khal new [OPTIONS] [START [END | DELTA] [TIMEZONE] [SUMMARY] [::
                DESCRIPTION]]

  Create a new event from arguments.

  START and END can be either dates, times or datetimes, please have a look at
  the man page for details. Everything that cannot be interpreted as a
  (date)time or a timezone is assumed to be the event's summary, if two colons
  (::) are present, everything behind them is taken as the event's
  description.

Options:
  -a, --calendar CAL
  -i, --interactive      Add event interactively
  -l, --location TEXT    The location of the new event.
  -g, --categories TEXT  The categories of the new event, comma separated.
  -r, --repeat TEXT      Repeat event: daily, weekly, monthly or yearly.
  -u, --until TEXT       Stop an event repeating on this date.
  -f, --format TEXT      The format to print the event.
  --json TEXT            Fields to output in json
  -m, --alarms TEXT      Alarm times for the new event as DELTAs comma
                         separated
  --url TEXT             URI for the event.
  --help                 Show this message and exit.
```

example

```sh
khal new -g cat1,cat2 -m 15m 2025-06-22 12:00 2025-06-23 13:00 "cmdline summary" :: descrpition after double colons
```
