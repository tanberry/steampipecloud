# QuickStart: Configure an integeration of Steampipe Cloud and Deepnote 

This Quickstart guide takes you through the process of integrating a Steampipe Cloud database instance with Deepnote, a science-centric, online notebook that provides a collaborative data dashboard.

## Sign up for a Steampipe Cloud account (https://cloud.steampipe.io/)

1. In the Steampipe Cloud UI, follow the prompts to:

    a. create a new **Workspace**
    b. create a **Connection** by selecting a plug-in. For this Quickstart, select Hackernews. Optionally, you can further define your connection to Hackernews by giving it a unigue name (handle) and limiting the number of items returned in any future queries. 
    c. add the new Connection to your Workspace.
For this Guide, you can skip the prompt to add a "mod".

Now that you have your Worspace defined in Steampipe Cloud, let's go to Deepnote and configure an integration with your Hackernews data in your Steampipe PostgreSQL database,

## Create an account on Deepnote (https://deepnote.com/sign-up)

1. In Deepnote, click **Integrations** in the left navigation pane.
  a. Select PostgreSQL from the (since your free Steampipe workspace uses Postgres).
  The Configure PostgreSQL integration modal box displays.
  b. Enter the required connection information, using the connection information from the Steampipe Cloud workspace (on the Connect tab).
  c. Click **Create** to save your connection information and close the modal box.
  
2. In Deepnote, create a new **Workspace**:
  a. In the left navigation area, click on the **plus sign** (+) beside **Workspace**.
  b. In the new workspace (by default called *Untitled*) go to the right navigation area and click on the **Integrations** tab.
  The existing integrations display in left navigatin pane.
  c. Click **Connect** on the Hackernews integration that you previously defined in Steampipe.
  d. Click **How to Use** on the Integration.
  e. Click the name of your Steampipe integration.
  A new pgsql query block displays on the main area of your workspace. Here, you can enter queries against the Hackernews data that is stored in your Steampipe Cloud database. Example: `select * from hackernewstb.hackernews_top limit 10;`
The returned data items display beneath the query.

Congratulations, you have successfuly integrated your Steampipe Cloud database with Deepnote!



FEEDBACK on fresh eyes observations:

1. I selected HackerNews as my plugin, renamed it hackernewstb, but then got an error that the plugin was not supported. Should I not have changed the name? [I now know that I cannot rename it, so why am I allowed to?] Other problem was there was no easy way to return quickly to the list of Plugins… I got dumped onto a page that showed my account (defaulted to the disturbingly empty Dashboards tab), but then had to drill down (using the Connect tab) to figure out how to go back and choose another plugin. My brain was looking for the word plug-in.. I had to deduce that “Connect” was the right place to go.
2. Where you enter your GitHub personal access token, it would help to specify that it is in the GitHub UI where you set the permissions scope.
3. There’s a sudden disconnect when I am thinking I am using Steampipe on the cloud, but I have to have a dashboard, and in order to build a dashboard I have to install Steampipe. So much for being all on the cloud. Yeah… the whole dashboard thing on Steampipe Cloud is confusing and disjointed… I am hung up on needing a dashboard, have to either pick one from a long list of seemingly unrelated dashboards, or build my own… I just want to get going,.,, gimme a n OoO dashboard please. I tried using the Terraform GCP compliance one, went down deep rabbit hole of figuring out where my TF state file resided... was ugly so I backed out and gave up on Dashboard. Now that  got through the whole exercise, I realize I relaly do not need a dashboard at all, since DeepNote will serve as my dashboard. The Steampipe cloud UI shold perhaps be more explanatory about dashboard being optional. 
In Deepnote, on the Configure PostgreSQL integration modal box, you have to fill out the required connection info in separate boxes (port, db name, etc)... it would be really nice if Deepnote let you just enter a connection string, hello
