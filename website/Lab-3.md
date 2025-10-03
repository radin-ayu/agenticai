---
layout: page
title: Lab 3
# permalink: /lab3/
nav_order: 5
---
🧑‍💼 AskProcurement Lab 3: Introduction to Flows for Agents
=================================================================================

In this lab, we will focus on a new way to create a tool - Flows!

**Why do we need flows?** **Agentic AI seems to be able to perform what I want, I don't want to design any flows**

While agents seems like they are able to perform tasks to fulfill users' requests using the tools available to them, there are still situations where a deterministic flow is important. For example in a procurement scenario, the agent must take necessary steps and put out a suitable alert if the order is over the company's agreeable amount. 

In this lab, we will design a flow which will take in reorder quantity and supplier's unit price from previous labs and determine if the order is over the approved amount (as stated in the procurement requisition documents). The flow will also generate emails addressed to relevant parties for approval if necessary.

A summary of the flow we are going to perform is as below:

<img src="./imgs/imgs_3/lab3_flow.png" alt="image" width="700" />



Step-by-step instructions
=========================

1.  Go to "Manage Agents"  
    <img src="./imgs/imgs_3/lab3_manage.png" alt="image" width="500" />

1.  Click "Create Agent"

    <img src="./imgs/imgs_3/lab3_create.png" alt="image" width="500" />

1.  Type the following:  
    Name: \[Your Initials\]\_askProcurement

    Description:

    ```
    You are an agent who specializes in procurement processes.
    You help the procurement officer with processes such as supplier research, calculating reorder amount and placing orders.
    Example of command: I want to reorder product Xtralife.
    ```
    <img src="./imgs/imgs_3/lab3_step1.png" alt="image" width="700" />
1.  Once the \[Your Initials\]\_askProcurement has been created, scroll down to Toolset > Add Tool and click on **Create an agentic workflow**.
    <img src="./imgs/imgs_3/lab3_createflow.png" alt="image" width="500" />
    
1.  You will see the following UI once the tool settings are loaded.

    <img src="./imgs/imgs_3/lab3_flowui.png" alt="image" width="500" />

    **TIPS:**
    If your menu pane does not appear, you can click on the **+** button to bring it out.

    <img src="./imgs/imgs_3/lab3_menu.png" alt="image" width="500" />
1.  Just like an agent, we will also need to name and describe our tool. Click on the pencil icon on the top left corner.

    <img src="./imgs/imgs_3/lab3_createflow1.png" alt="image" width="500" />
1.  Fill up the following fields:

    Name: \[Your Initials\]_Check reorder quantity

    Description: The flow to check reorder quantity and generate relevant email templates or message

    <img src="./imgs/imgs_3/lab3_createflow2.png" alt="image" width="500" />
1.  After that, move downwards where we can define inputs to the flow. Click on **Add input**  

    <img src="./imgs/imgs_3/lab3_createflow3.png" alt="image" width="500" />
1.  We are creating 2 inputs. Follow details shown in the table below

    | Type     | Name            | Description                               | Required        |
    |----------|-----------------|-------------------------------------------|-----------------|
    | Decimal  | supplier_price  | The unit price of Xtralife for a supplier | On              | 
    | Integer  | reorder_quantity| Amount to reorder                         | On              |
    
    Example of how to create inputs:

    <img src="./imgs/imgs_3/lab3_createflow4.png" alt="image" width="500"/>

    <img src="./imgs/imgs_3/lab3_createflow5.png" alt="image" width="500" />

1. You will have a resulting table as below. Click on **Save** when you're done.

    <img src="./imgs/imgs_3/lab3_createflow6.png" alt="image" width="700" />

1. Next, we will also need to create a variable to keep track of the total reorder value. Click on the green triangle to get the following pop out. Click on the pencil icon next.
    <img src="./imgs/imgs_3/lab3_createvar.png" alt="image" width="500" />

1. Then click on **Add** and **Decimal**
    <img src="./imgs/imgs_3/lab3_createvar1.png" alt="image" width="500" />

1. Input the following

    Name: total_value
    Description: Total reorder value

    Click **Add**
    <img src="./imgs/imgs_3/lab3_createvar1.png" alt="image" width="500" />
    
1. We will start creating the flow by inserting a branch to check the total reorder value. We will need to multiply both the inputs.<br>From the tools menu, drag out a **Code Block**. Ensure that the tool snaps on the flow.

    <img src="./imgs/imgs_3/lab3_createcode.png" alt="image" width="500" />

1. Click on the code block tile  and click on Open code editor. 

    <img src="./imgs/imgs_3/lab3_createcode1.png" alt="image" width="500" />

1. In the empty space, start typing `flow` and there will be suggestions appearing. Select `flow.private.total_value`.

    <img src="./imgs/imgs_3/lab3_createcode2.png" alt="image" width="500" />

1. Continue to type out the expression until you get the following.

    <img src="./imgs/imgs_3/lab3_createcode3.png" alt="image" width="500" />

1. Now let's have different action for different situation. Drag out a **Branch** tool on to the flow. 

    <img src="./imgs/imgs_3/lab3_createflow7.png" alt="image" width="500" />

    <img src="./imgs/imgs_3/lab3_createflow8.png" alt="image" height="500" />

1. Now, we will add the branching condition. Click on the purple diamond shape and a menu will pop out for you.  
    <img src="./imgs/imgs_3/lab3_createflow9.png" alt="image" height="500" />
    
1. Hover on **Branch1** and click on the pencil icon. Rename Branch 1 to **Total Value Check** and click the tick icon.
     <img src="./imgs/imgs_3/lab3_createflow10.png" alt="image" width="500" />

1. Now let's add the different conditions based on this flow.

    <img src="./imgs/imgs_3/lab3_flow.png" alt="image" width="400" />

    Click on **Edit Condition**

    <img src="./imgs/imgs_3/lab3_createflow11.png" alt="image" width="500" />


    <img src="./imgs/imgs_3/lab3_createflow12.png" alt="image" width="500" />

1. Click on the **+** beside the if and switch to **Flow variable** and select **total_value**

    <img src="./imgs/imgs_3/lab3_createflow13.png" alt="image" width="500" />
    

    <img src="./imgs/imgs_3/lab3_createflow14.png" alt="image" width="500" />

    Select the **>** sign from the drop down and change the value to 150000.

    <img src="./imgs/imgs_3/lab3_createflow15.png" alt="image" width="500" />

    <img src="./imgs/imgs_3/lab3_createflow16.png" alt="image" width="500" />

1. You can also try to rename the path by clicking on Path 1 and Path 2

     <img src="./imgs/imgs_3/lab3_createflow17.png" alt="image" height="200" />

    <img src="./imgs/imgs_3/lab3_createflow18.png" alt="image" height="200" />

1. Click anywhere to return to the canvas. For the path with more than 150k, we want the flow to assist in generating an email template to seek approval from senior management.

    From the menu, drag and snap **Generative prompt** tile on to the flow.

    <img src="./imgs/imgs_3/lab3_createflow19.png" alt="image" width="500" />

    You will be presented with a UI where you can design prompts.

    <img src="./imgs/imgs_3/lab3_createflow20.png" alt="image" width="500" />

1. Create a input variable

1. Copy and paste the following into the system prompt and User prompt

    System prompt:

    ```
    You are a helpful system assistant. Your task is to help a purchasing officer to craft an email.
    
    ```

    User prompt:

    ```
    Based on the reorder value {reorder_value}, you are to generate an email to your sales manager, Mr Wong, to seek approval this reorder value. This reorder value is over the approved budget of $150000. You can create a reason for this order such as nearing festivities and you foresee that there is a surge in sales for the product Xtralife. Be professional and avoid long-winded explanation.
    
    ```

    <img src="./imgs/imgs_3/lab3_createflow21.png" alt="image" width="500" />

1. Now we need to associate the calculated total reorder value with the input variable for our prompt to generate the email.

   Click on the Generative Prompt tile on our flow and then click on Data Mapping

   <img src="./imgs/imgs_3/lab3_createflow22.png" alt="image" width="500" />

   <img src="./imgs/imgs_3/lab3_createflow23.png" alt="image" width="500" />

   As you can see, we can actually leave the mapping to AI. However, since we want to be very sure that the input is captured correctly, we will map it manually.

1. Once you hover on the input bar, click on the variable icons. 

    <img src="./imgs/imgs_3/lab3_createflow24.png" alt="image" width="500" />

    Switch to **Flow variables** and select **reorder value**.

    <img src="./imgs/imgs_3/lab3_createflow25.png" alt="image" width="500" />

1. After the email is being generated by the LLM, we want to display it to the user. We will drag in a **User activity** tile into the flow.

    <img src="./imgs/imgs_3/lab3_createflow26.png" alt="image" width="500" />   

1. Hover in the green box and click on the **+**.

    <img src="./imgs/imgs_3/lab3_createflow27.png" alt="image" width="500" />   

1. Select **Display to user** and the **Message** tile.

    <img src="./imgs/imgs_3/lab3_createflow28.png" alt="image" width="500" />   

    <img src="./imgs/imgs_3/lab3_createflow29.png" alt="image" width="500" />  

1. Click on the **Message** tile to get the following pop out.

    <img src="./imgs/imgs_3/lab3_createflow30.png" alt="image" width="500" />  

1. Click on the variable icon, switch to **Generative prompt** and click on **value**

    <img src="./imgs/imgs_3/lab3_createflow31.png" alt="image" width="500" />  

1. Next, let's repeat the above steps to create a notification to let user know that their order has been placed when their order is below $150,000.

    Click on the **Add** icon and select **User activity**.

    <img src="./imgs/imgs_3/lab3_createflow32.png" alt="image" width="500" />  

1. Hover in the green box and click on the **+**.

    <img src="./imgs/imgs_3/lab3_createflow27.png" alt="image" width="500" />   

1. Select **Display to user** and the **Message** tile.

    <img src="./imgs/imgs_3/lab3_createflow28.png" alt="image" width="500" />   

    <img src="./imgs/imgs_3/lab3_createflow29.png" alt="image" width="500" />  

1. Click on the **Message** tile to get the following pop out.

    <img src="./imgs/imgs_3/lab3_createflow30.png" alt="image" width="500" />  

1. Copy and paste the following message.

    ```
    Your order is approved. You can proceed to place your order.
    ```

    <img src="./imgs/imgs_3/lab3_createflow33.png" alt="image" width="500" />  

1. Now that our flow is done, we can click on **Done** on the top right corner.

