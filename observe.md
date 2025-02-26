---
layout: default
title: "Observability"
category: "Life Sciences"
---
Grafana, an interactive data visualization platform, enables you to query your application's log data and – in turn – retrieve query results presented as logs, charts, graphs, and dashboards.
The Observability Stack uses three tools:
* Loki
   * Arguably the most important tool, Loki includes customer application data ranging from server performance to your application log data. Grafana uses Loki to store and query logs. Promtail – an agent that collects logs – integrates with Kubernetes, which is where your customer application resides. Promtail collects data from logs along with certain runtime system data.
* Grafana
   * The visualization user interface (UI) or dashboard.

This Observability Stack provides visibility into your application.

**NOTE**: <br/>
This content is specific to a use case that enables customers to understand how Grafana uses their deployed data. The user persona is a client application engineer, and this content represents how someone in this role navigates Grafana to view customer-specific deployed data. Since the user persona represents someone with the capacity to understand technical concepts and terminologies, this content does not provide insight into basic Grafana functions.

## Getting Started
You can access Grafana via the IL2 Development (DEV) and Production (PRD) environments using your Game Warden Keycloak SSO or Platform One (P1) SSO credentials.

### Access Environment
1.	Access Grafana via Game Warden IL2 Dev (link removed) or Grafana via Game Warden IL2 PRD (link removed).
    
    The **Welcome to Grafana Enterprise** window opens.
1. Click **Sign in with Game Warden SSO**.
1. Enter your Game Warden Keycloak SSO credentials or your P1 login credentials and subsequent Multi-factor Authentication (MFA) code.

   After you successfully enter your login credentials, you will have access to the Grafana **Home** page.
1. Click the right-facing arrow near the top left pane to expand the navigation area.

## Permissions
Customers only have access to dashboards in their folder along with a **General** folder, which will contain generalized queries and templates developed by the Site Reliability Engineering (SRE) team. The Observability Stack – Loki, Prometheus, and Grafana – provides access only to application log data and metrics in your Kubernetes application namespace.

Users are associated with teams. These teams have permission solely to access their customer folder and datasources, which pull data from the Kubernetes clusters into Grafana. Datasources also include some of the Prometheus runtime metrics associated with the application.

## View Dashboards
1. Select **Dashboards** then **Browse** from the left navigation pane.
   
   Grafana displays your customer folder.
1. Select your customer folder then choose a dashboard.
1. Double-click the selected dashboard.
   
   Grafana provides a graphical visualization. The related dashboard data and links will vary, as this content is unique to each customer’s application data and services. You can select links near the lower section of the page, if applicable, to view additional panels of data from Docker containers or Kubernetes pods. In some cases, you might have access to logs along with metadata associated with each log entry.
1. Double-click the selected dashboard.
   
   Grafana provides a graphical visualization. The related dashboard data and links will vary, as this content is unique to each customer’s application data and services. You can select links near the lower section of the page, if applicable, to view additional panels of data from Docker containers or Kubernetes pods. In some cases, you might have access to logs along with metadata associated with each log entry.

# Create Queries and Dashboards
You can create, edit, and execute queries using **Explore**.
To create queries:
1. Select **Explore** from the left navigation pane.
   The **Query Editor** opens.
1. Select the drop-down arrow near the top left section of the page to choose the datasource you want to query if, in fact, you have configured more than one datasource. 
   
   For example, you can select {ORG}-prd-customer.
1. Create a LogQL query, using format:
   {log-stream-selector} | log-pipeline
   The stream selector should always include the application namespace and can include additional options. This query section narrows the logs your query searches. The log pipeline contains functions or transformations that are performed on the logs you specify with the stream selector.

   **EXAMPLE QUERY**: This query searches for log entries that contain “400”.
   {namespace="YOUR_APPLICATION_NAMESPACE", container="CONTAINER_NAME"} |= '400'
   **EXAMPLE LOG ENTRY**: This entry is in a common access log format (used by nginx).
   127.0.0.6 - - [09/Jan/2023:22:40:17 +0000] "POST /api/request-path HTTP/1.1" 400 2 "-" "HTTP-AGENT/1.0.0"

   Your application logs must use consistent formats across an application. This allows queries to capture relevant information more easily and ensures no logs are missed by a given query.


   You can use fields such as **Metrics**, **Label Filters**, **Operations**, and **Legends** to help build queries. As you enter information in these fields, Grafana provides auto-complete suggestions based on your input.
1. Review the query statement(s) to ensure accuracy.
1. Click **Run Query** to execute.
   Grafana displays the query results on the lower section of the page.
1. Click **Add to Dashboard** near the top right of the page.
1. Click **Open dashboard**.
   The dashboard opens.
1. Click the **Save dashboard** icon near the top right of the page.
1. Enter a **Dashboard name** and use the drop-down arrow to select a Folder.
1. Click **Save** to store changes.
   
   Grafana contains the new dashboard panel. You can search the dashboard name for quick access. You also can view this dashboard on your **Home** page under **Recently viewed dashboards**. Here, you can select the **Star** icon next to the entry, making it a **Favorite** under **Starred dashboards**. Starring the dashboards allows faster and more efficient access.
11.	Edit the panel and customize visualization settings as preferred, using the **Switch to table** and **Open visualization suggestions** options.

As noted in the steps above, you can create a query and add this query to a dashboard. Similarly, you also can select **Dashboards | New dashboard** from the left navigation pane on the **Home** page, add a panel, create a query, then add this query to a new dashboard – repeating most of the previous steps.

## Sample Query Editor Workflow
1. Make certain the **loki-datasource** corresponds to your company’s datasource name. For example: ORG-dev-customer or ORG-prd-customer.
1. Enter the namespace that corresponds with your Kubernetes application namespace in the **Query Editor** text box, which resides next to **Label browser**.
1.	Click **Add to dashboard** to save the query as a panel in your dashboard.





