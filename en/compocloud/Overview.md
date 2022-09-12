___

# Compocloud Overview
___

This document serves as a user-manual for monitoring and controlling a COMPOcloud-plant over the mandy-userinterface. 


To read more about how to login and select a plant/device, please read:

[Mandy - Setup and first steps](/#/help?folder=mandy&page=setup)

The overview-screen of a COMPOcloud-application opens after click on a COMPOcloud-plant at the `Selection`-page.
On the initial page, a header for navigation is displayed at the top and windrows of a plant are displayed below. If the plant is equipped with a biofilter, it will be displayed after the windrows.
___

## Header
___

In the overview of COMPOwatch you can switch between different views via a header bar. The current view is highlighted in color (dark red).

![Compocloud Overview](/assets/images/Docs/Compocloud/Uebersicht.png)

Basically, the following views (pages) are available, depending on the role of the currently logged in user:

- **OVERVIEW**: Displays the status of all windrows. This page is accessible to every user.
- **LOGS & EXPORT**: On this page, the recorded measured values of all windrows can be displayed in a chart. This page is accessible to all users except visitors.
- **SETTINGS**: General settings can be done here. This page is only accessible to users with the operator, manager, and administrator roles.
- **SYSTEM (ADMIN)**: Here system commands can be sent to the IoT client. Users of the administrator group can open this page.
- **ACKNOWLEDGE**: Confirmation of alarms.
- **SIGNAL STRENGTH and NETWORK OPERATOR**: On the right, the signal strength of the 3G/4G modem and the name of the network operator are being displayed. The signal strength value should be higher than -82dbm.
- **TEMPERATURE OUTSIDE**: If irrigation is available, the outside temperature is displayed next to the network information.

Additional to the header-bar, the sidebar-menu can be used to navigate between views.
___

## Active Alarms
___

All currently active error-messages, not related to a sub-area like a windrow or biofilter, are displayed in the overview of windrows below the header-bar. The description of the message is displayed followed by the timestamp of the message raised.

![Error Message](/assets/images/Docs/Compocloud/COMPOcloud_Overview-Alarms_EN.PNG)

By pressing the `ACKNOWLEDGE`-button in the header or by pressing the reset button on the control cabinet, the alarm can be confirmed and reset.
___

## Logs & Export
___

On this page, the measured temperatures of all windrows can be output and exported for a time period defined by the user. The user can define a “from” and “to” date by himself. Pressing DAY, WEEK, MONTH sets the desired duration with the current date as the 'to' date.

After selecting the time period, the data can be displayed in preview by pressing 'LOGS & EXPORT'. With 'DOWNLOAD' they can be stored on the external device.

___

## Settings
___

General settings can be made on this page. The transfer of a value takes place by pressing SAVE.

- **Transmission interval**: Time interval for reading and transferring data variables to the Mandy platform. Displayed only for older systems with IoT Client v1. 
- **Irrigation - Drainage time**: The duration of drainage (emptying) after an irrigation cycle. Drainage is only carried out when the outside temperature is below 5°C to prevent frost damage to the system. It will only be displayed if irrigation is available.
- **Irrigation - Number of valves**: Maximum number of irrigation valves, which can be opened at the same time. Depending on the available water pressure, too many open valves can lead to a very low pressure in the system and more distant windrowd are not properly irrigated. Set this value so that with this number there is enough water pressure even in the most distant windrow. It will only be displayed if irrigation is available.

___

## Windrows
___

If a desired windrow is clicked in the overview, the view of a windrow is opened. This view can also be opened by pressing the “Windrow” submenu of a windrow. The windrow widget is displayed in the overview of a windrow. Other submenus include CHART, NOTIFICATIONS and PARAMETERS. 
___

## Biofilter
___

If the system is equipped with a biofilter and a biofilter blower, the widget for the biofilter is displayed after the windrow widgets.
By clicking on the biofilter widget in the light grey area the biofilter section is being opened.

