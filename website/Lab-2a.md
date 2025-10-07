---
layout: page
title: Lab 2a
# permalink: /lab1/
nav_order: 3
---
# 🏦 AskProcurement Lab 2a: Building a Supplier Research RAG Agent

Please refer to [Lab 2 Explanations](../pdfs/Lab%202a-explanation.pdf) for additional information.
    
In this lab, you will build a Supplier Researcher Agent using Watsonx.ai Agent Lab. This agent will allow you to research the suppliers for procuring Xtralife based on past supplier performance, procurement rules and customer reviews.

![image](./imgs/imgs_2a/lab-architecture2a.png)

Files used in lab can be downloaded from the following links:
-  [Procurement Requisition Rules_update.pdf](/Lab_2a_Files/Procurement%20Requisition%20Rules_update.pdf)
- [Supplier Sales Report for Procurement_update.pdf](/Lab_2a_Files/Supplier%20Sales%20Report%20for%20Procurement_update.pdf)
## Step by step instructions to build the Supplier Researcher Agent:

1. When you launch watsonx Orchestrate, you'll be directed to this page. Click on the hamburger menu in the top left corner:

    ![image](./imgs/imgs_2a/step_1.png)

1. Click on the down arrow next to **Build**.  Then click on **Agent Builder**:

    ![image](./imgs/imgs_2a/step_2.png)

1. Click on **Create agent +**:

    ![image](./imgs/imgs_2a/step_3.png)

1. Select "Create from scratch", give your agent a unique name (make sure to identify yourself by your initials or name, since this is a shared instance), e.g. "[Your Initial]_Supplier_Researcher Agent", and fill in the description as shown below: 

    ```
    You are a helpful supplier researcher that uses tools to answer questions precisely after doing thorough research on google and document search. The google search tool can provide customer sentiment on the suppliers. The document search tool has the procurement requisition rules and past year supplier review.
    ```  

    Click on **Create**:

    ![image](./imgs/imgs_2a/step_19.png)

1. We are going to build a knowledge base for the agent. Scroll down the screen to the **Knowledge** section and click on "Choose knowledge".

    ![image](./imgs/imgs_2a/step_5.png)

1. Choose "Upload files" and click "Next".

    ![image](./imgs/imgs_2a/step_6.png)

1. Drag and drop the [Procurement Requisition Rules_update.pdf](/Lab_2a_Files/Procurement%20Requisition%20Rules_update.pdf) and [Supplier Sales Report for Procurement_update.pdf](/Lab_2a_Files/Supplier%20Sales%20Report%20for%20Procurement_update.pdf) and click on **Next**:

    ![image](./imgs/imgs_2a/step_7.png)

1. Copy the following description into the **Description** section and click **Save**:

    ```
    Use this knowledge base when you need to understand the procurement requisition rules and information related to Xtralife suppliers. 
    ```

    ![image](./imgs/imgs_2a/step_8.png)

    The knowledge base will take some time to create. After the knowledge base is done, you will be brought back to the Agent Builder UI.

    <!-- ![image](./imgs/lab-3a/hr_step_kbase.png) -->


1. Scroll down to the **Behavior** section. Insert the instructions below into the **Instructions** field:

    ```
    You are a helpful supplier researcher that uses information available to you to answer questions.
    When you receive a user question, you are to use the knowledge source to look for relevant information. Then you must use Tavily search tool to enrich your information on the suppliers. 
    You must gather information from both knowledge source and search tool before generating an answer.
    You must use information from both search methods to generate a complete and comprehensive answers. 
    ```

    ![image](./imgs/imgs_2a/step_9.png)

1. lets see how to add the web crawl tool to your agent, go to **Toolset** section and click **Add tool**.

     ![image](./imgs/imgs_2a/step_10.png)

1. Click **Add from file or MCP server**.

     ![image](./imgs/imgs_2a/step_11.png)

1. Click **Import from MCP server**

     ![image](./imgs/imgs_2a/step_12.png)

1. Click **Add MCP server**  

     ![image](./imgs/imgs_2a/step_13.png)

1. Name, description fill in as you like. Select Connection, click **Workshop_tavily**, Install Command : ``` npx -y tavily-mcp@0.2.1 ```, and Click **Connect**

     ![image](./imgs/imgs_2a/step_18.png)

1. Once connected turn **ON** the **tavily-search** tool.

    ![image](./imgs/imgs_2a/step_17.png)
    
1. Test your agent in the preview chat on the right side by asking the following questions and validating the responses.  They should look similar to what is shown in the screenshot(s) below:

    ```
    Which supplier out of Excelentia Supplies and Global Office Supplies is viable to buy product Xtralife from. Give a list of pros and cons of each supplier
    ```
    ```
    Which supplier should i choose? i want an urgent delivery.
    ```
    ```
    Give me a list of pros and cons Excelentia Supplies and Global Office Supplies
    ```
    ```
    Which supplier should i choose? i want an urgent delivery.
    ```
    ```
    How are the reviews for Excelentia Supplies?
    ```
    ![image](./imgs/imgs_2a/step_16.png)


**Congratulations! You've built your first RAG Agent.**