# xConnect Release Notes
[TOC]

# Release 13: June 23rd, 2020

## Enhancements
- Event Feed alterations to the navigation links.
  - Modified the way the event feed links navigate a user to the appropriate device dashboard and event log listing.
  
  ![Side Navigation](images/event_log_r13_enhancement.png "Event Listing")
  
  Upon clicking the device name (i.e. Server01) a user will be taken to the device dashboard. Clicking the table icon (![Side Navigation](images/r13_table_icon.png "Event Listing")) will navigate to the filtered event logs for this particular device.
  
- Company Abbreviation added to all alerting e-mails
  - Enables xConnect support to easily identify which e-mail alerts originated from a particular xConnect customer. 
  
  ![Side Navigation](images/r13_cust_abbreviation.png "Customer abbreviation")
  
- Release version # added to the home page, which links to release notes. 

- Maintenance mode: prevents potential spamming of alerts in the occurrence of a scheduled maintenance window. Enhancement prevents users from logging on during the maintenance. 

![Side Navigation](images/R13_maintenancemode.png "Customer abbreviation")

- User preferences now preserves your selections for expanding or collapsing panels on your dashboards. 


## Bug Fixes
- Event logs now include custom outage duration notices instead of default 60 minute outage windows. 