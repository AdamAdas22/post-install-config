<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Post-Install Configuration</h1>
This tutorial outlines the post-install configuration of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>Post-Install Configuration Objectives</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Configuration Steps</h2>

<h3>Step 1: Accessing the Admin Login Page</h3>
<p>
Navigate to the osTicket admin login page by entering 
<a href="http://localhost/osTicket/scp/login.php" target="_blank">http://localhost/osTicket/scp/login.php</a> in your browser. 
Log in using the administrator credentials you created during installation. 
</p>
<p>
Once logged in, take a moment to acknowledge the <strong>Agent Panel</strong>, which serves as the interface for handling tickets. 
You can switch between the <strong>Admin Panel</strong> and the <strong>Agent Panel</strong> using the navigation bar. 
The <strong>Admin Panel</strong> provides full control over system settings, user roles, and permissions, while the <strong>Agent Panel</strong> is designed for support staff to manage and respond to tickets.
</p>

<h3>Step 2: Configuring Roles and Departments</h3>
<p>
The first step in setting up user access control is configuring <strong>Roles</strong>. In the <strong>Admin Panel</strong>, navigate to <em>Agents → Roles</em>. Here, you can create and customize roles based on the level of access needed.  
For example, if you create a role titled <strong>"Supreme Admin"</strong> and check all permission boxes, this role will have unrestricted access across the system.
</p>

<p>
Next, we will configure <strong>Departments</strong> to determine ticket visibility. When a ticket is assigned to a specific department, only agents within that department can view and manage it.  
To configure departments:
</p>

<ul>
  <li>Go to <strong>Admin Panel → Agents → Departments</strong>.</li>
  <li>Click <strong>"Add New Department"</strong>.</li>
  <li>Name the department <strong>"SysAdmins"</strong>.</li>
  <li>Adjust settings to define ticket visibility and departmental responsibilities.</li>
  <li>Save the changes.</li>
</ul>

<p>
Departments help organize ticket management, ensuring tickets reach the appropriate team, such as <em>Help Desk</em>, <em>SysAdmins</em>, or <em>Networking</em>.
</p>



<h3>Step 3: Configuring Teams and User Ticket Permissions</h3>

<p>
Now, we will configure <strong>Teams</strong> to group agents from different departments. Unlike departments, which control ticket visibility, teams allow agents from multiple departments to collaborate.
</p>

<ul>
  <li>Go to <strong>Admin Panel → Agents → Teams</strong>.</li>
  <li>Click <strong>"Add New Team"</strong>.</li>
  <li>Name the team <strong>"Online Banking"</strong>.</li>
  <li>Assign agents from different departments who will handle banking-related tickets.</li>
  <li>Save the changes.</li>
</ul>

<p>
Next, we will configure user ticket permissions by requiring users to register before submitting tickets.
</p>

<ul>
  <li>Go to <strong>Admin Panel → Settings → User Settings</strong>.</li>
  <li>UNCHECK the option: <strong>"Unregistered users can create tickets"</strong>.</li>
  <li>Enable: <strong>"Require registration and login to create tickets"</strong>.</li>
  <li>Save the changes.</li>
</ul>

<p>
By enabling registration requirements, only registered users can submit tickets, improving security and ensuring accountability.
</p>





<h3>Step 4: Configuring Agents (Workers)</h3>

<p>
Now, we will add agents to the osTicket system. Agents are the workers who will manage and respond to support tickets. Each agent will be assigned to a department and a team based on their role.
</p>

<ul>
  <li>Go to <strong>Admin Panel → Agents → Add New</strong>.</li>
</ul>

<h4>Adding Jane Doe</h4>
<ul>
  <li><strong>Name:</strong> Jane Doe</li>
  <li><strong>Email:</strong> jane.doe@gmail.com</li>
  <li><strong>Username:</strong> jane</li>
  <li><strong>Password:</strong> password1</li>
  <li><strong>Department:</strong> SysAdmins</li>
  <li><strong>Team:</strong> Online Banking</li>
  <li><strong>Role:</strong> Supreme Admin (Full permissions)</li>
</ul>

<h4>Adding John Doe</h4>
<ul>
  <li><strong>Name:</strong> John Doe</li>
  <li><strong>Email:</strong> john.doe@gmail.com</li>
  <li><strong>Username:</strong> john</li>
  <li><strong>Password:</strong> password1</li>
  <li><strong>Department:</strong> Support</li>
  <li><strong>Team:</strong> (None assigned)</li>
  <li><strong>Role:</strong> (Standard agent permissions)</li>
</ul>

<p>
Once both agents are added, click <strong>Save Changes</strong> to confirm the setup.
</p>


<h3>Step 5: Configuring Users (Customers)</h3>

<p>
Now, we will add an end user to simulate real-life support tickets. End users are the customers who will submit tickets for support.
</p>

<ul>
  <li>Go to <strong>Agent Panel → Users → Add New</strong>.</li>
</ul>

<h4>Adding Karen (Test Customer)</h4>
<ul>
  <li><strong>Name:</strong> Karen</li>
  <li><strong>Email:</strong> karen.doe@gmail.com</li>
  <li><strong>Phone Number:</strong> (555) 123-4567</li>
  <li><strong>Username:</strong> karen</li>
</ul>

<p>
After filling out Karen’s details, click <strong>Add User</strong> to create the customer profile. This user will be used to simulate ticket submissions in the next steps.
</p>

<p>
Now that we have created a test user, we will proceed to configure SLA (Service Level Agreements) for managing ticket response times.
</p>




<h3>Step 6: Configuring SLA (Service Level Agreements)</h3>

<p>
Service Level Agreements (SLAs) define the urgency, response time, and resolution time for different types of support tickets. We will create three SLA plans: 
</p>

<ul>
  <li><strong>Sev-A:</strong> Critical issues that need immediate attention (1-hour response time, 24/7 support).</li>
  <li><strong>Sev-B:</strong> Moderate issues that require attention within a few hours (4-hour response time, 24/7 support).</li>
  <li><strong>Sev-C:</strong> Low-priority issues that can be addressed during business hours (8-hour response time, business hours only).</li>
</ul>

<h4>Creating SLA Plans</h4>

<ul>
  <li>Go to <strong>Admin Panel → Manage → SLA</strong>.</li>
  <li>Click <strong>Add New SLA Plan</strong> and enter the following details:</li>
</ul>

<h4>Sev-A (Critical Issues)</h4>
<ul>
  <li><strong>Name:</strong> Sev-A</li>
  <li><strong>Grace Period:</strong> 1 hour</li>
  <li><strong>Schedule:</strong> 24/7</li>
</ul>

<h4>Sev-B (Moderate Issues)</h4>
<ul>
  <li><strong>Name:</strong> Sev-B</li>
  <li><strong>Grace Period:</strong> 4 hours</li>
  <li><strong>Schedule:</strong> 24/7</li>
</ul>

<h4>Sev-C (Low-Priority Issues)</h4>
<ul>
  <li><strong>Name:</strong> Sev-C</li>
  <li><strong>Grace Period:</strong> 8 hours</li>
  <li><strong>Schedule:</strong> Business Hours</li>
</ul>

<p>
Once all SLA plans have been created, they will be applied to tickets based on priority levels. Now, we will proceed to ticket automation and workflow configurations.
</p>





<h3>Step 7: Configuring Help Topics</h3>

<p>
Help Topics allow users to categorize their support tickets when submitting a request. This helps streamline ticket management and ensures that requests are routed to the correct department. We will create five help topics in osTicket.
</p>

<h4>Creating Help Topics</h4>

<ul>
  <li>Go to <strong>Admin Panel → Manage → Help Topics</strong>.</li>
  <li>Click <strong>Add New Help Topic</strong> and fill in the following details:</li>
</ul>

<h4>Help Topic: Business Critical Outage</h4>
<ul>
  <li><strong>Title:</strong> Business Critical Outage</li>
  <li><strong>Parent Topic:</strong> Report a Problem</li>
</ul>

<h4>Help Topic: Personal Computer Issues</h4>
<ul>
  <li><strong>Title:</strong> Personal Computer Issues</li>
  <li><strong>Parent Topic:</strong> Report a Problem</li>
</ul>

<h4>Help Topic: Equipment Request</h4>
<ul>
  <li><strong>Title:</strong> Equipment Request</li>
  <li><strong>Parent Topic:</strong> General Inquiry</li>
</ul>

<h4>Help Topic: Password Reset</h4>
<ul>
  <li><strong>Title:</strong> Password Reset</li>
  <li><strong>Parent Topic:</strong> Report a Problem</li>
</ul>

<h4>Help Topic: Other</h4>
<ul>
  <li><strong>Title:</strong> Other</li>
</ul>

<p>
Once these Help Topics are set up, users will be able to select the appropriate category when creating a support ticket, improving efficiency and ticket resolution.
</p>




<h3>Final Note</h3>

<p>
Congratulations! You have successfully configured osTicket with roles, departments, teams, agents, users, SLAs, and help topics. With these settings in place, your help desk system is now structured and ready to manage support tickets efficiently.
</p>

<p>
In the next lab, we will focus on <strong>working with tickets and understanding the ticket lifecycle</strong>. This includes creating, assigning, responding to, and closing tickets while following the workflows we have set up.
</p>

<p><strong>Stay tuned as we dive into real-world ticket management scenarios!</strong></p>


























<br />

<br />
