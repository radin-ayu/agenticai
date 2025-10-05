---
layout: page
title: Lab 1
# permalink: /lab1/
nav_order: 2
---
# 🧑‍💼 Lab 1: Prebuilt Agents and Tools

## Objective
The IBM watsonx Orchestrate catalog serves as a vast repository of prebuilt AI agents and tools, tailored to address a wide array of use cases and requirements. This extensive collection helps you discover agents, tools, or a blend of both that align with your specific needs. In this lab, we will use one of the prebuilt agents to demonstrate how easy it is for a user to start the agent-building journey.

Each watsonx Orchestrate prebuilt agent and tool is connected to a service. Services require connections to be established. For this lab, we have already created the necessary connections.

## Key features of prebuilt agents include:
Pre-configured: Prebuilt agents come with pre-defined settings and configurations for easy setup.
Reusable: Prebuilt agents can be used across multiple workflows, reducing the need to recreate similar tasks.
Task-specific: Each prebuilt agent is designed to perform a specific task or set of tasks, such as data processing, API calls, or notifications.
    
In this lab, you will build a Procurement Agent using Watsonx Orchestrate. This agent will allow you to generate the information about all the accounts. You can also enquire about any specific account details.   

We are leveraging Prebuild agants and tools. The tools we are using in this lab, are from Salesforce. We have already integrated two tools here "Retrieve Salesforce accounts" and "Retrieve Salesforce contacts" to demonstrate the watsonx Orchestrate capabilities to connect with different third party tools. 
The IBM watsonx Orchestrate Catalog is your gateway to a rich collection of prebuilt AI agents and tools, designed to support a wide range of business functions and use cases. Whether you're looking to automate tasks, enhance productivity, or integrate with backend systems, the catalog helps you find the right solutions quickly and efficiently.

## Let's start our IBM watsonx Orchestrate learning journey: 

## Step by step instructions to build the Supplier Researcher Agent:

1. When you launch watsonx Orchestrate, you'll be directed to this page. Click on the hamburger menu in the top left corner:

    ![image](./imgs/imgs_a/step_1.png)

1. Click on the down arrow next to **Build**.  Then click on **Agent Builder**:

    ![image](./imgs/imgs_a/step_2.png)

1. Click on **Create agent +**:

    ![image](./imgs/imgs_a/step_3.png)

1. Select "Create from scratch", give your agent a unique name (make sure to identify yourself by your initials or name, since this is a shared instance), e.g. "[Your Initial]_Supplier_Researcher Agent", and fill in the description as shown below: 

    ```
    You are a helpful supplier researcher that uses tools to answer questions precisely after doing thorough research on google and document search. The google search tool can provide customer sentiment on the suppliers. The document search tool has the procurement requisition rules and past year supplier review.
    ```  

    Click on **Create**:

    ![image](./imgs/imgs_a/step_4.png)

1. We are going to build a knowledge base for the agent. Scroll down the screen to the **Knowledge** section and click on "Choose knowledge".

    ![image](./imgs/imgs_a/step_5.png)

1. Choose "Upload files" and click "Next".

    ![image](./imgs/lab-3a/hr_step_uploadfile.png)

1. Drag and drop the [Procurement Requisition Rules.docx](./pdfs/Procurement%20Requisition%20Rules.docx) and [Supplier Sales Report for Procurement.docx](./pdfs/Supplier%20Sales%20Report%20for%20Procurement.docx) and click on **Next**:

    ![image](./imgs/imgs_a/step_6.png)

1. Copy the following description into the **Description** section and click **Save**:

    ```
    This knowledge is used to provide requisition rules and supplier reviews. Assume that all the reviews selected are from the suppliers who are supplying Xtralife product.
    ```

    ![image](./imgs/lab-3a/hr_step_desc.png)

    The knowledge base will take some time to create. After the knowledge base is done, you will be brought back to the Agent Builder UI.

    ![image](./imgs/lab-3a/hr_step_kbase.png)


1. Scroll down to the **Behavior** section. Insert the instructions below into the **Instructions** field:

    ```
    Use your knowledge base to answer general questions about employee benefits. 
    ```

    ![image](./imgs/lab-3a/hr_step12.png)

1. Test your agent in the preview chat on the right side by asking the following questions and validating the responses.  They should look similar to what is shown in the screenshot(s) below:

    ```
    Which supplier out of Excelentia Supplies and Global Office Supplies is viable to buy product Xtralife from. Give a list of pros and cons of each supplier
    ```
    ```
    Which supplier should i choose? i want an urgent delivery.
    ```

    ![image](./imgs/lab-3a/hr_step13.png)



1. You can try the following sample questions as well:

    ```
    how many days of leave am i entitled to?
    ```
    ```
    can i work from home 3 times a week?
    ```
    ```
    does the company provide any assistance on loan repayments?
    ```
    Notice that you get a generic answers based on policy for all employees. You will see in the next lab how you can connect it to Employee Address Agent and Leave Management Agent from Lab 1 to do tasks for you.

**Congratulations! You've built your RAG Agent.**
