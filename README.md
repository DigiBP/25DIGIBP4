# Team Members

| Name                    | Email                                        |
|-------------------------|----------------------------------------------|
| Ellona Tsap             | ellona.tsap@students.fhnw.ch                 |
| Lukas Janotka           | lukas.janotka@students.fhnw.ch               |
| Patricia Abel           | patricia.abel@students.fhnw.ch               |
| Ramona Steinauer        | ramona.steinauer@students.fhnw.ch	         |

# Coaches

- Andreas Martin
- Charuta Pande 
- Devid Montecchiari

# 🎯 Project Goals

The goal of the assignment is to develop a solution that applies the DigiBP approach to a business process, demonstrating how digital technologies can improve process performance. 

# 📦 AS-IS Process

This order-to-shipment is a key supporting process to a sales process. It involves 4 departments and covers the work ranging from processing the purchase order (PO) to preparing and shipping the ordered goods. With over 600 customers and 2500 orderlines processed monthly, the process requires 

![As-Is Process](As_Is_Process.png)

The Order-to-Cash process begins when a customer places an order via google form with their assigned Customer Service (CS) agent. The CS agent manually opens SAP, fills in the order header, and — when available — uses a reference from a prior quotation to simplify order entry. If no quotation match is found, the agent must manually input all items into SAP. CS agents periodically check order statuses in SAP (without automated alerts) and request dispatch once the order is ready. For orders involving assembly (product type "F"), planners are involved. Throughout the process, CS agents manually track important information (e.g., orders without confirmed shipping dates) in Excel spreadsheets. Communication with customers regarding order status or delays is manual, and customers often inquire directly with CS agents.

📹 [Watch the process video Camunda Token](as-is%20Route%201.mp4)

**Roles involved into the process**:

Internal
- Customer Service (CS): handles the incoming PO, the availability of ordered goods and informs other process participants of the outcome
- Procurement: involved in procuring ordered items which are out-of-stock
- Planner: involved in planning the production of out-of-stock items
- Dispatch: performs warehouse jobs (picking and packing) in preparation to shipping goods

External:
- Client
- Vendor

# 🧩 Challanges of the Process

One of the major challenges are a manual work relative to processing of PO and performing manual checks of goods availability which negatively affects the performance and efficiency. Process relies on manual communication in checking the availability of orderd goods and especially at the point when a goods availability check is performed, customer service team has to inform the relevant colleagues which is dependent on the result (see tasks marked green). 
Such level of manual coordination leads to a substantial amount of time spent on iterative and tidious messaging and ultimately generates time losses especially if not followed up immediately. This might ultimately lead to dissatisfaction of customers.  

- **Fragmented Communication**  
  Coordination between departments depends on manual notifications, leading to delays and errors.

- **Manual Document Preparation**  
  POs are received by email, validated, and entered into the system manually.

- **Inefficient Goods Availability Check**  
  Manual stock checks are performed, and customer service must inform other departments accordingly.

- **Inefficient Follow-Up**  
  Manual follow-ups are time-consuming and prone to being overlooked.

- **Process Bottlenecks**  
  Delays often occur when missing goods require procurement and production coordination.

- **Lack of Workflow Automation**  
  The absence of automated decision-making and notifications leads to unnecessary workload and time losses.

  
# TO-BE Process

As the company grows, we seek to **reduce the amount of user tasks and manual work** needed to perform them especially the goods availability check. By achieving this partial automation, we will save time for parties invovled that can be dedicated on continuos improvement elsewhere. Our process solution will introduce a pratial automation eliminating the need to check goods manually while also reducing manual communication.

Our Vision is not not only deliver a partial automation but also improve customer experience with the improved process.

We aim to:

- Reduce manual tasks
- Improve customer experience
- Save time for the customer service team
- Enable the team to focus on continuous improvement

Technologies Used

| Component                    | Purpose                                        |
|-------------------------|----------------------------------------------|
| Camunda 7            |Modeling the business process |
| BPMN 2.0       |Used Modeling-Language            |
| DMN         |             |
| Google Form      |        |
| Google Sheet     |As database for testing simulated orders|
| Post             | 
| Make                |
| Voiceflow             |Used to design and deploy the conversational interface


# Google Form
https://docs.google.com/forms/d/e/1FAIpQLSfrZuLGhWxTEj_86DGCYEw97wCztB8QaVXKZe03wEM6Rq_qEA/viewform
https://docs.google.com/spreadsheets/d/1acwL_7EVOsgsh5U8FepiyN8VsF1C-bmWOzAxlu0-zZ8/edit?gid=0#gid=0

# Make Scenarios

# Email Notification

Certainly. Here's a concise and professionally worded documentation section for your GitHub repository:

# 💬 Voiceflow Chatbot – Digital Customer Support Assistant

As part of the digitalization of the Order-to-Cash process, a chatbot was implemented to handle customer inquiries related to order status. The solution is designed to reduce manual communication, improve response times, and enhance customer satisfaction. The chatbot also guides the customer through inquiries concerning the changing the order, the order process and return inquiries.
The chatbot enables customers to receive real-time answers on their questions by entering a valid order ID. It retrieves order information from Google Sheets databases. The chatbot operates through a voice or text interface and is accessible 24/7.

The benefits of offering a chatbot as a service include the following:
* Reduces manual workload for the Customer Service team.
* Delivers consistent, fast, and reliable customer communication.
* Enhances process transparency and customer satisfaction.
* Easily scalable to cover additional services (e.g., delivery updates, FAQs).

The chatbot is complements the Camunda-driven digital process and MAKE automated process flow by serving as a human-centric interface at the customer touchpoint.

# Process Improvements
What got improved?

- Reduce manual tasks
- Improve customer experience
- Save time for the customer service team
- Enable the team to focus on continuous improvement

The following deliverables are mandatory: 
- Link to GitHub repositories containing: 
    - Modelling artefacts (such as BPMN or DMN) and, if required, other project arte
      facts (such as configuration files, source code, etc.) 
    - Documentation about the project and processes (as GitHub markdown files (e.g., 
      Readme and interlinked .md files)) 
- Link to a running workflow(s) and/or instantiation(s) of a: 
   - Link to start form(s) and/or cloud-based deployment(s) 
- Link to presentation slides
