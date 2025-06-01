# 🤝 Team 25DIGIBP4: transforming an order-to-shipment process in customer service within F&B machinery industry

# 🧑‍🔧 Team Members

| Name                    | Email                                        |
|-------------------------|----------------------------------------------|
| Ellona Tsap             | ellona.tsap@students.fhnw.ch                 |
| Lukas Janotka           | lukas.janotka@students.fhnw.ch               |
| Patricia Abel           | patricia.abel@students.fhnw.ch               |
| Ramona Steinauer        | ramona.steinauer@students.fhnw.ch	         |

# 💡 Coaches

- Andreas Martin
- Charuta Pande 
- Devid Montecchiari

# 📝 Introduction

Our project is a real-life process within a global food&beverage machinery manufacturer and is a key supporting process to the company´s core sales process of selling food&beverage machinery including its repair and maintenance parts. This order-to-shipment process involves 4 departments and covers the work ranging from processing the purchase order (PO) to preparing and shipping the ordered goods. With over 600 customers and 2500 orderlines processed monthly, the process requires a close followup across all involved departments to fulfill custoemer orders as soon as possible as a main driver behind customer satisfaction.

# 🧩 Challanges of the Process

One of the major challenges is manual work related to the processing of PO and manual checks of goods availability which negatively affects the performance and efficiency. Process also relies on manual communication when checking the availability of orderd goods eespecially at the point when the goods availability check has been performed by cutomer service who, depending on the outcome of this availability check, must inform the relevant colleagues (either Procurement or Dispatch) to carry on with the execution of the process. Such level of manual and back-and-forth communication leads to a substantial amount of time spent on iterative and tidious messaging and ultimately generates time wastes especially if not followed up immediately by customer service or other departments. This might ultimately lead to dissatisfaction of customers and revenue losses.

For a breakdown of specific challenges relative to this process see the below overview. 

- **Fragmented and manual Communication**  
  Coordination between departments depends on manual notifications, leading to delays and errors.

- **Manual goods availability Check**  
  POs are received by email, validated, and entered into the system manually.

- **Inefficient Follow-Up**  
  Manual follow-ups are time-consuming and prone to being overlooked.

- **Lack of Workflow Automation**  
  The absence of automated decision-making especially in terms of checking the availability of ordered goods leads to unnecessary workload and time losses.
  
# 🎯 Goal and Vision

Our goal is to transform the current process by introducing a partial automation that will lead to removing a substantial part of the workflow within Customer Service, specifically the need to carry out goods availability check manually while reducing the chance of possible human erros. By achieving this partial automation, we will save time for parties involved that can be dedicated on continuos improvement elsewhere. Our Vision is not not only deliver a partial automation but also improve customer experience by introducing a way for customers to check the order status or ask for instructions on how to place and order. 

# 📦 AS-IS Process
* https://github.com/DigiBP/25DIGIBP4/blob/main/order_to_shipping_as-is_23_05.bpmn
*  [As-Is BPMN Model – Order to Shipping](As-Is%20Process/order_to_shipping_as-is_23_05.bpmn)

This order-to-shipping process can be broken down into two main parts: (1) processing incoming POs and performing a goods availability (see tasks highlighted in green) and (2) preparing goods for shipment. The first part involves several user tasks within customer service all of which involve non-automated workflow and manual communication. First, an incoming PO is processed retreived manually from a mailbox and PO data entered into the system. after this, customer service manually checks the goods availability which is done by looking up the ordered goods in a stock database and depending on the result, customer service notifies the respective colleague to proceed with the process. If goods are available, Dispatch is notified to prepare the goods for shipment. If goods are not available, customer service notifies procurement to purchase the missing goods. (for both paths see "token videos" below). Such manual availability check and communication is tidious and leads to time wastes in the process which is further excacerbated by loose follow-ups further down the process by other process participants. 

![As-Is Process Part 1](Pictures/As_is_process_part_1.png)

**Roles involved in the process**:

**Internal**
- Customer Service (CS): handles the incoming PO including the check of availability of ordered goods and informs other process participants of the outcome
- Procurement: involved in procuring ordered items which are out-of-stock
- Planner: involved in planning the production of out-of-stock items
- Dispatch: performs warehouse jobs (picking and packing) in preparation to shipping goods

**External**:
- Customer (interaction with customers not modelled)
- Vendor (interaction with vendors not modelled)
  
## 📋 Process Description


| Process Step | Description                        | Comments                                                                                                                                                     | Lane                            |
|--------------|------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------|
| 1 | Receipt and processing of PO       | PO is received by email<br>PO is validated and entered into system manually                                                                                  | Customer Service                |
| 2            | Goods availability check           | Manual availability check is performed.<br>Order item quantity is checked for availability in Stock database.<br>If order item in stock, CS informs Dispatch to request the preparation of order for shipping.<br>If order item is out of stock, CS informs Procurement to purchase missing components. | Customer Service (green tasks) |
| 3            | Purchase of missing order items    | Procurement creates a purchase request and when the delivery date is confirmed by the vendor, procurement notifies a planner to plan the production         | Procurement                     |
| 4            | Planning of production of purchased goods                            | Create a production order based on the delivery timeline.                                                                                                    | Planner                         |
| 5            | Missing order items are planned in for production | As soon as the delivery date from vendor is available, Customer Service is notified and informs Dispatch                                         | Customer Service                |
| 6            | Picking and packing                | Goods are prepared for shipment.                                                                                                                             | Dispatch                        |


**Overview of full as-is process**

![As-Is Process](Pictures/As_is_process.png)



🎥 [As-Is Route 1 Video](https://github.com/DigiBP/25DIGIBP4/blob/main/As-Is%20Process/Route%20Videos/as-is%20Route%201.mp4)
🎥 [As-Is Route 2 Video](https://github.com/DigiBP/25DIGIBP4/blob/main/As-Is%20Process/Route%20Videos/as-is%20Route%202.mp4)

  
# TO-BE Process

To tackle the current challenges of the AS-IS Process the following technologies have been used and applied:

| Component                    | Purpose                                        |
|-------------------------|----------------------------------------------|
| Camunda 7            |Modeling the business process |
| BPMN 2.0       |Used Modeling-Language            |
| Make                |Used to automate tasks using different Modules |
| Post                 | 
| Voiceflow             |Used to design and deploy the conversational interface|


# Google Form 
Our Order to Ship process starts when an order is entered into the Google form (note: the process can not be started manually in Camunda Engine! – which is as expected). As soon as the order has been submitted via google form, the tasks appear in Camunda Engine and may then be completed.

**Links**:
Google Form: https://docs.google.com/forms/d/e/1FAIpQLSeRJk72AsnS4mkPVHtKpz_k9PAM2kjObPrT1Gb0I1208mLp5A/viewform 
Response Sheet: https://docs.google.com/spreadsheets/d/1gB6kCeueMDYXXfVU8TTvKkFgIYxz8RYR0I0wL8L1RyQ/edit?usp=sharing 
Inventory Sheet: https://docs.google.com/spreadsheets/d/1YS6Ev_YT5LyQp5M6MQcl2YjBbLnjlQEp5IqUemB4uAU/edit?gid=0#gid=0 

# Make Scenario 1

To eliminate manual tasks, increase efficienty and to incorporate workflow automation and automated decision making the first Make Scenario offers a reliable solution:

![Receive Order & Inventory Check](Pictures/Make_scenario_receiveOrder_inventoryCheck.png)

The created Make Scenario automates all user tasks (below in green) from customer service and is able to make manual user tasks obsolet.
It takes over the following tasks:

-	Retrieve/check PO from an email
-	enter PO data into the system manually
-	perform Goods Availability check 
-	request goods shipment with Dispatch
AND
-	contact procurement to backorder and out of stock item
  
![Obsolet Manual Tasks](Pictures/Obsolet_manual_tasks.png)

To create the Scenario, the following Modules have been used:

| Module                    | Purpose                                        | Description |
|-------------------------|----------------------------------------------|------------------|
| Google Sheets          |Watch Rows |Triggers with each new order and starts Camunda Process once an order is entered via Google form
| Google Sheets      |Search Rows           |Checks inventory based on Product ID|
| Router         |    Checks if stock is available or not         |Will direct to the corresponding route |
| Update a Row     | Updates Order Status in Google Sheets  |Shows that the order is either with Dispatch or Procurement |
| Gmail |Send Email     |Sends either a "thank you for your order" email or a notification that the item is currently out of stock and delivery will take longer as it will be re-ordered |
| HTTP Module | Camunda Integration | https://digibp.engine.martinlab.science/engine-rest/process-definition/key/Process_0ad1ggy/tenant-id/25DIGIBP29/start |

Example of the auotmated messages created:
![Order Confirmation](Pictures/Gmail_module.png)
![Thank You Mail](Pictures/Thank_you_mail.png)

![GMail Module](Pictures/GMail_module_description.png)
![Backorder Confirmation](Pictures/Backordermessage.png)

# Make Scenario 2

![Service Task: Send PO to vendor](Pictures/Make_scenario_send_PO_to_vendor.png)

The second Make Scenario has been created  to replace another manual task and is automatically triggered after the User Task "Purchase Request" when stock is unavailable.
It creates and sends a new purchase order to vendor via email.

![Send PO to vendor](Pictures/Send_PO_to_vendor_task.png)
![Purchas Order to Vendor](Pictures/Backorder_message.png)

The scenario was created by using a Custom Webhook and the GMail Module (Send Email). 

After the Service Task a Message Intermediate Catch Event was created as the Vendor needs to confirm the delivery date. 
As soon as the vendor replies with a confirmation via email, Postman Triggers to Camunda (manually triggered) - Postman should show a green 204 No Conent message and in Camunda the next task available should be visible (Create Production Order). 

![Intermediate Event](Pictures/Message_intermediate_catch_event.png)

# Recap of the integrated Flow

1. Customer submits PO → Google Form
2. InventoryCheck Make Scenario runs:
   - Checks inventory
   - Updates Google Sheet
   - Notifies customer
   - Starts Camunda process
3. If stock is not available, Camunda waits for delivery confirmation (message event).
4. Vendor receives email → sends delivery date manually
5. Professor triggers message via Postman (token continues in Camunda)

![To-be Process](Pictures/As_is_process.png)


# 💬 Voiceflow Chatbot – Digital Customer Support Assistant

As part of the digitalization of the Order-to-Cash process, a chatbot was implemented to handle customer inquiries related to order status. The solution is designed to reduce manual communication, improve response times, and enhance customer satisfaction. The chatbot also guides the customer through inquiries concerning the changing the order, the order process and return inquiries.
The chatbot enables customers to receive real-time answers on their questions by entering a valid order ID. It retrieves order information from Google Sheets databases. The chatbot operates through a voice or text interface and is accessible 24/7.

The benefits of offering a chatbot as a service include the following:
* Reduces manual workload for the Customer Service team
* Delivers consistent, fast, and reliable customer communication
* Enhances process transparency and customer satisfaction
* Easily scalable to cover additional services (e.g., delivery updates, FAQs)

The chatbot is complements the Camunda-driven digital process and MAKE automated process flow by serving as a human-centric interface at the customer touchpoint.

# Process Improvements
These two major improvements deliver 

| Challange                    | Solution                                        |
|-------------------------|----------------------------------------------|
| Manual PO checks           |Google Forms + automated trigger |
| Manual stock checks      |Inventory lookup in Google Sheets         |
| Delayed communication                |Emails sent automatically via Make |
| No decision automation                 | Camunda decision based on stock status |
| Process errors             |Eliminates human input at routing points|
| Slow vendor coordination           |Email automatically generated and sent|

By integrating the two Make Scenarios the involvement of Customer Service within this process got eliminated completly. These now free resources may be allocated to other important business tasks.

# Future Steps and Recommendations
The current solution is not able to auto-generate Order ID's. This should be tackled bevore implementing the improvements for the process in real life.




The following deliverables are mandatory: 
- Link to GitHub repositories containing: 
    - Modelling artefacts (such as BPMN or DMN) and, if required, other project arte
      facts (such as configuration files, source code, etc.) 
    - Documentation about the project and processes (as GitHub markdown files (e.g., 
      Readme and interlinked .md files)) 
- Link to a running workflow(s) and/or instantiation(s) of a: 
   - Link to start form(s) and/or cloud-based deployment(s) 
- Link to presentation slides
