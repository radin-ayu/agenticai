---
layout: page
title: Lab 1
# permalink: /lab1/
nav_order: 2
---
# 🧑‍💼 Lab 1: Prebuilt Agents and Tools

## Objective

Please refer to [Lab 1 Explanations](../pdfs/Lab%201-explanation.pdf) for additional information.

The IBM watsonx Orchestrate catalog serves as a vast repository of prebuilt AI agents and tools, tailored to address a wide array of use cases and requirements. This extensive collection helps you discover agents, tools, or a blend of both that align with your specific needs. In this lab, we will use one of the prebuilt agents to demonstrate how easy it is for a user to start the agent-building journey.

Each watsonx Orchestrate prebuilt agent and tool is connected to a service. Services require connections to be established. For this lab, we have already created the necessary connections.

### Key features of prebuilt agents include:
- **Pre-configured:** Prebuilt agents come with pre-defined settings and configurations for easy setup.
- **Reusable:** Prebuilt agents can be used across multiple workflows, reducing the need to recreate similar tasks.
- **Task-specific:** Each prebuilt agent is designed to perform a specific task or set of tasks, such as data processing, API calls, or notifications.
    
This lab introduces the Account Management Agent in Watsonx Orchestrate, which retrieves and reviews both general and specific account details. This is an out-of-the-box agent that utilizes Salesforce tools—specifically Retrieve Salesforce Accounts and Retrieve Salesforce Contacts—to demonstrate how Watsonx Orchestrate connects seamlessly with third-party systems. The Watsonx Orchestrate Catalog provides a rich collection of prebuilt AI agents and tools to automate tasks, boost productivity, and integrate with backend systems efficiently.

![image](./imgs/imgs_1/lab-architecture1.png)

## Let's start our IBM watsonx Orchestrate learning journey: 

### Step by step instructions to employ the Pre-built Account Management Agent:

1. When you launch watsonx Orchestrate, you'll be directed to this page. Click on the hamburger menu in the top left corner:

    ![image](./imgs/imgs_1/step_1.png)

2. From the hamburger menu on the top left corner, select “Discover”
    ![image](./imgs/imgs_1/discover.png)

3. You will be presented with this view
    ![image](./imgs/imgs_1/catalog_view.png)

    Currently, all the prebuilt agents and tools are separated into many domains/categories (in this view you can see aroud 12 different categories of the domain). In this lab, we will be using prebuilt agents and tools from the Procurement category.

4. On the search bar, search for “Account Management” and hit *Enter*. Click on the “Account Management” agent once the search result comes back.
   ![image](./imgs/imgs_1/account_management_agent.png)

5. Once you clicked on the “Account Management”, you will be presented with this view.
   ![image](./imgs/imgs_1/agent_view.png)

    You will be able to see what this agent is doing, the tools it is using. From this page, we will be able to assess if this agent is suitable for your use case.
6. To use this agent, click on the “Use as template” button on the top right.
    ![image](./imgs/imgs_1/use_template.png)

7. You will be presented with the Agent Builder page. Edit the name so that it is unique. Change the agent’s name to [Your Initial]_Account management.
   ![image](./imgs/imgs_1/agent_name.png)
   
8. Save the new name to the agent. 
   ![image](./imgs/imgs_1/save_name.png)

9. Now, it's all set. Your agent is ready. Keep the rest of the agent set up as it is and let’s explore the agent. You can see the "Model" at top and "Profile", "Knowledge", "Toolset", "Behaviour" and "Channel" at the left side. Just explore one by one to get an understanding on the different blocks of the agent.
    ![image](./imgs/imgs_1/agent_blocks.png)
   
10. Let's explore the "Preview" window given in the right side. In the “Preview” panel on the right, You can try some queries to test the performance of the agent at your local.
    ![image](./imgs/imgs_1/preview.png)

    ### Queries:
    ```
    Show all the accounts
    ```
    ![image](./imgs/imgs_1/preview_outcome.png)
    
    If you face any problem with step 11, please alert one of your friendly instructors.

## Add tools from the catalog
Prebuilt agents present an easy way to build an agent. However, we can also edit the prebuilt agent. Let’s explore a bit by adding an extra tool into this agent.

1. Click on "Toolset" from the leftside panel or Scroll down to the toolset and click on “Add tool”.
    ![image](./imgs/imgs_1/add_tool.png)

2. Click on “Add from catalog”.
     ![image](./imgs/imgs_1/ad_frm_catalog.png)

3. On the search bar, type in “salesforce”. Select “Get the list of users from Salesforce” from the search result.  
    ![image](./imgs/imgs_1/list_user_tool.png)
4. After you click on the tool, you will be able to see the input and output the tool is expecting. Once you’re ready, click on “Add to agent” on the bottom right.
    ![image](./imgs/imgs_1/add_tool_agent.png)

5. Once returned to the agent builder page, you will see the additional tool added to the tools list.
    ![image](./imgs/imgs_1/added_tool_list.png)

6. After building the agent, we can deploy our agent. Click the “Deploy” button on the top right. Keep all default settings when being asked.
    ![image](./imgs/imgs_1/deploy.png)

7. You will see the "Pre-deployment summary" to review all the changes / updates you made to your agent. You can also see the total connections, you created to the third party tools. In our example, it is "Salesforce".
    ![image](./imgs/imgs_1/pre_deployment.png)

8. Once the deployment is success, navigate to “Chat” from the left-hand hamburger menu.
    ![image](./imgs/imgs_1/chat.png)

9. From the dropdown menu, select your agent.
    ![image](./imgs/imgs_1/agent_selection.png)

10. Now, you can use use your agent. Try to ask some queries. "Show information about all accounts" 
    ### Queries:
    ```
    Show information about all accounts
    ```
    ![image](./imgs/imgs_1/generate_outcome.png)

    ```
    Show information about all contacts
    ```
    ![image](./imgs/imgs_1/generate_outcome1.png)


**Congratulations! You've built your first Procurement Agent using Pre-built agents and tools.**
