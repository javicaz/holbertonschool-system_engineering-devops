 <h2>Simple web stack<h2/>
 
 The flow from a user wanting to access the website www.foobar.com:

User enters "www.foobar.com" in their web browser.
The user's computer sends a request to the Domain Name System (DNS) server to resolve the IP address for "www.foobar.com."
The DNS server looks up the domain name and returns the corresponding IP address, which is 8.8.8.8 in this case.
The user's computer establishes a connection to the server at IP address 8.8.8.8.
Now, let's design the infrastructure:

Server: The server is a physical or virtual machine that hosts the entire infrastructure. It runs the necessary software and handles incoming requests. In our case, we have a single server to host the website.
Domain Name: The domain name (foobar.com) serves as a human-readable identifier for the website. It helps users locate and access the website easily. The "www" in www.foobar.com is a subdomain prefix commonly used to denote the World Wide Web.
DNS Record: The DNS record for www.foobar.com should be configured with a "www" subdomain record that points to the server's IP address (8.8.8.8). This record is typically an "A" record, which associates the domain/subdomain with an IP address.
Web Server (Nginx): The web server software, such as Nginx, handles incoming HTTP requests from users. It receives requests from the user's computer and responds with the appropriate content. The web server's role is to serve static files, handle routing, and communicate with the application server.
Application Server: The application server runs the application's code base, which contains the website's dynamic functionality. It executes the necessary logic, retrieves data from the database, and generates dynamic content for the user's request. In this setup, the application server communicates with the web server to process user requests.
Application Files (Code Base): The application files contain the website's code, including HTML, CSS, JavaScript, and any server-side code or frameworks. These files reside on the server and are executed by the application server in response to user requests.
Database (MySQL): The database stores and manages the website's data. In this case, we are using MySQL as the database management system. The application server communicates with the database to retrieve and store data required for the website's functionality.
Communication with User's Computer: The server uses the HTTP protocol to communicate with the user's computer. When a user requests a webpage, the server sends an HTTP response containing the requested content back to the user's computer, which is then rendered by their web browser.
Now, let's address the issues with this infrastructure:

Single Point of Failure (SPOF): Since we have a single server, it becomes a single point of failure. If the server goes down due to hardware failure or other issues, the website will become inaccessible. To mitigate this, redundancy measures like using multiple servers or implementing failover mechanisms can be employed.
Downtime during Maintenance: When maintenance or deploying new code is required, the web server needs to be restarted. During this period, the website might experience downtime, causing interruptions in service. To minimize the impact, techniques like rolling deployments or using a load balancer with multiple servers can be utilized.
Scalability Limitations: With a single server, it becomes challenging to handle a significant increase in incoming traffic. The infrastructure might struggle to handle the load, leading to slower response times or even crashes. Scaling can be achieved

<h2><h2/>