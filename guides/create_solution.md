## Create a Solution

Next you need a place to deploy HVAC solution code. 

### Web UI

To create a solution using the Web UI:

1. From the *Solutions* tab (https://www.exosite.io/business/solutions), click "+ NEW SOLUTION." 

   ![new solution](assets/new_solution.png)

2. Select *Start from scratch* and click the "ADD" button.

   ![new solution](assets/new_solution_popup.png)

Once you have created a solution, you will need to find the Solution ID.

1. In Murano select *Solutions*.

2. Select the solution you just created.

3. Copy the Solution ID on this page.

   ![solutions tab](assets/solutions_tab.png)

### Murano CLI

To create a solution using the Murano CLI:

```sh
$ murano solution create <name>
```

This command will return the ID of your solution for the next step.

### Configure Your Solution

To configure Murano CLI to work with your newly created solution, use the config command of the Murano CLI tool.

```sh
$ murano config solution.id <solutionid>
```