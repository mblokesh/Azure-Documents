# How to Create Alerts in Azure

    1.	Create a Log Analytics Workspace
    2.	Create a Storage Account to store the Logs
    3.	Enable Insights (Select Log Analytics Workspace created in the Previous Steps).
    4.	Go to  Diagnostic Setting  Enable guest-level monitoring.
    5.	After enable step:4 Go to Diagnostic Setting  Agent  Log Level  Changed to ALL
    6.	After enable step:4 Go to Diagnostic Setting  Sinks  Azure Monitor  Enabled.
    7.	Go to Log Analytics Workspace  Agents Configuration  Windows Performance Counter  Add Performance Counter (LogicalDisk(*)\% Free Space, Memory(*)\Available Mbytes).

## To Create a RAM Alert Rule:

    1.	Go to Log Analytics Workspace  Logs  Copy and Paste the Alert Query and Run that (If query gets result the create a new alert rule).

## To Create a CPU Alert Rule:

    1.	Go to Alerts  Create an Alert Rule  Signal type(ALL) – Monitor Service(ALL) – Search by signal name(Percentage CPU)  Greater than – Average – 80% - Granularity(5 Minutes) – Frequency of evaluation(1 Minute)  Select Action Groups  Severity(Warning) – Enable (Enable Upon Creation and Automatically Resolve Alerts)  Review and Create.
