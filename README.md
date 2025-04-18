# MTT CoHack Challenge: Tracking ISS (International Space Station) with Microsoft Fabric

## Introduction

In this hack, you will track the ISS International Space Station in real-time with Microsoft Fabric. You will learn to use Event Stream, KQL database and get insights from the data in real time. You will also hack a Power BI Report together that displays the current location in real-time. This hack will help you to gain skills for for [DP-603 Implement Real-Time Analytics with Microsoft Fabric](https://learn.microsoft.com/en-us/training/paths/explore-real-time-analytics-microsoft-fabric/). 

![iss space station](./images/iss.png)

## Requirements

You will need contributor access to an Azure Subscription and a Microsoft Fabric tenant with sufficient permissions to create a workspace. On top of this, you'll also need to have Power BI Desktop installed on your (Windows) PC.

## Set up the resources

<img width="1184" alt="Drawing" src="https://github.com/user-attachments/assets/502e8224-7283-49b2-a245-5ab48b9ab046" />


1. **Azure Logic App** (consumption tier)
    - Set up a recurring trigger every 10 seconds
    - Add an HTTP GET action to the following URL: https://api.wheretheiss.at/v1/satellites/25544
    - Add a Send to Event Hub action and fill in the name + connection string. Make sure to send the body of the HTTP Get action as the event payload.
2. **Event Hub**
3. **Eventstream**
4. **Eventhouse** / **KQL DB**
    - Create a new table

## Get insights by using KQL

Create KQL queries that help you to:

1. See how many ISS location data records there are in the table.
2. Show a preview of 100 records in a table layout.
3. Determine the timerange of the ISS location data you have in the KQL database. Hint: use unixtime_seconds_todatetime and min() max()
4. Render a map that displays the ISS trajectory for the last 100 seconds
5. The International Space Station (ISS) takes approximately 90 minutes to complete one orbit around the Earth. Show this on a map.
6. Determine whether the ISS was visible during the last 90 minutes? 

## Create a Power BI Report 

1. Use Power Desktop or Fabric.
2. Leverage a Map Visual.
4. Configure Auto Page Refresh.
5. Publish / Validate in Fabric.


## Optional: Create a Dashboard

Optional excercise (challenge!): In conjunction with your report, create a dashboard that will update in RT.

## Supporting links
- [Stream real-time events from a custom app to a Microsoft Fabric KQL database](https://learn.microsoft.com/fabric/real-time-analytics/event-streams/stream-real-time-events-from-custom-app-to-kusto)

- [Create an example Consumption logic app workflow using the Azure portal](https://learn.microsoft.com/azure/logic-apps/quickstart-create-example-consumption-workflow)

- [Query data in a KQL queryset](https://learn.microsoft.com/fabric/real-time-analytics/kusto-query-set?tabs=kql-database)

- [Create geospatial visualizations](https://learn.microsoft.com/azure/data-explorer/kusto/query/tutorials/create-geospatial-visualizations)

- [Azure Data Explorer: Kusto: unixtime_seconds_todatetime()](https://learn.microsoft.com/azure/data-explorer/kusto/query/unixtime-seconds-todatetime-function)

- [Azure Data Explorer: Kusto: toreal()](https://learn.microsoft.com/azure/data-explorer/kusto/query/toreal-function)

- [Get data for Data Activator from Eventstreams](https://learn.microsoft.com/fabric/data-activator/data-activator-get-data-eventstreams)
