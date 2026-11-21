\# PrintTrack — Project Proposal



\## 1. Title



PrintTrack: 3D Printing Product and Order Manager



\## 2. Project Overview



PrintTrack is a Blazor web application for small 3D printing business owners who need to organize their products and customer orders. Managing requests through messages or handwritten notes can make it difficult to track quantities, prices, deadlines, and production progress. PrintTrack will store this information in one place.



The target users are independent makers and small business owners who produce and sell 3D printed items. Each registered user will manage a private product catalog and customer orders. The application will help users identify pending work, update production progress, and find orders quickly.



The project is valuable because it addresses a practical business need with a manageable scope. It will demonstrate the use of C#, ASP.NET Core, Blazor, Entity Framework Core, NuGet packages, and the .NET CLI to build a usable application with authentication and database CRUD operations.



\## 3. Project Scope



\### Included



\- User registration, login, and logout.

\- Creating, viewing, editing, and deleting products.

\- Creating, viewing, editing, and deleting customer orders.

\- Tracking orders as Pending, In Production, or Delivered.

\- Searching orders by customer name and filtering by status.

\- Form validation and confirmation before deleting records.

\- A responsive interface for phones, tablets, and desktops.

\- Testing, basic user documentation, and cloud deployment.



Each order will contain one product and a quantity. Users can create separate orders for additional products.



\### Excluded



\- Online payments and checkout.

\- Customer accounts or a public storefront.

\- Shipping labels and carrier tracking.

\- Direct control of 3D printers.

\- Uploading images, STL files, or other attachments.

\- Inventory automation and accounting integrations.

\- Email or SMS notifications.

\- A summary dashboard.



These boundaries keep development realistic for the remaining four weeks.



\### Development Schedule



\- Week 4: Create the Blazor application, database, authentication, and product management.

\- Week 5: Implement order management and production statuses.

\- Week 6: Implement search and filters, test data isolation, and improve usability and accessibility.

\- Week 7: Complete testing, documentation, cloud deployment, and the demonstration video.



\## 4. App Features and User Stories



The following five features are recorded as cards on the public Trello board.



\### Feature 1: User registration, login, and logout



Users can create an account, log in, and log out. Authentication is required to access product and order management.



User story:

As a 3D printing business owner, I want to sign in securely so that only I can access my business records.



Requirements:

\- Register with an email and password.

\- Log in and log out.

\- Protect management pages from unauthenticated visitors.

\- Restrict records to their owner.



\### Feature 2: Product management (CRUD)



Users can create, view, edit, and delete their products. Product information includes name, description, material, color, and unit price.



User story:

As a 3D printing business owner, I want to manage my product catalog so that I can keep product details and prices organized.



Requirements:

\- Require a product name and a unit price greater than zero.

\- Display product lists and details.

\- Allow editing and deletion with confirmation.

\- Prevent deletion of products linked to orders.

\- Restrict access to the product owner.



\### Feature 3: Order management (CRUD)



Users can create, view, edit, and delete their customer orders. Each order records a customer name, product, quantity, order date, due date, notes, and a saved unit price.



User story:

As a 3D printing business owner, I want to manage customer orders so that I can keep track of requested products and delivery deadlines.



Requirements:

\- Select a product from the user's catalog.

\- Require customer name, product, positive whole-number quantity, and due date.

\- Calculate the total from quantity and the saved unit price.

\- Preserve existing order prices when catalog prices change.

\- Confirm deletion and restrict access to the order owner.



\### Feature 4: Order production status tracking



Users can change an order's status to Pending, In Production, or Delivered.



User story:

As a 3D printing business owner, I want to track each order's production status so that I know which orders need work and which have been delivered.



Requirements:

\- Start new orders as Pending.

\- Save status changes in the database.

\- Show the current status in order lists and details.

\- Allow changes only by the order owner.



\### Feature 5: Search and filter orders



Users can search orders by customer name and filter them by production status.



User story:

As a 3D printing business owner, I want to find orders by customer and status so that I can quickly locate the work that needs my attention.



Requirements:

\- Search by all or part of a customer name.

\- Filter by Pending, In Production, or Delivered.

\- Combine search and status filters.

\- Provide a Clear button and a message for empty results.

\- Return only the signed-in user's records.



\## 5. Technical Considerations



\### Technology Stack



The application will use C#, ASP.NET Core, Blazor, and Entity Framework Core. NuGet will manage dependencies, and the .NET CLI and Visual Studio Code will support development. GitHub will store source code, Trello will track tasks, and Microsoft Teams will support project communication.



\### Data Storage



A SQLite database will store application data through Entity Framework Core.



Main records:

\- User accounts managed by ASP.NET Core Identity.

\- Products: ID, owner ID, name, description, material, color, and unit price.

\- Orders: ID, owner ID, customer name, product ID, quantity, saved unit price, order date, due date, notes, and status.



Order totals will be calculated from quantity and saved unit price. Products referenced by orders cannot be deleted until those orders are removed.



\### User Accounts



Users will register and sign in through ASP.NET Core Identity. Each account will manage its own products and orders. Separate customer accounts and shared business accounts are outside the initial scope.



\### External Services and Deployment



No external business APIs are required. The application will be deployed to a cloud service with persistent storage for SQLite. The database will be kept outside temporary deployment folders so saved records survive application restarts and updates.



\### Device Compatibility and Accessibility



The interface will adapt to mobile phones, tablets, and desktops. Forms will use visible labels, clear validation messages, keyboard-accessible controls, and readable contrast. Accessibility will be checked against WCAG 2.2 Level AA using Lighthouse and axe DevTools.



\### Basic Security



ASP.NET Core Identity will handle password hashing and authentication. Server-side authorization will verify record ownership for every read and write operation. Forms will validate input, and database operations will use Entity Framework Core. The deployed application will use HTTPS. Credentials and private configuration will not be committed to GitHub.



\### Testing and Documentation



Testing will cover registration, login, logout, CRUD operations, validation, order totals, statuses, and combined search filters. Two test accounts will verify that users cannot access each other's records. Responsive layouts and accessibility will also be checked.



A README will provide setup and basic usage instructions. Code comments will explain decisions where needed.



\## 6. Project Links



GitHub repository:

https://github.com/Wilfredo-Marapacuto/CSE325-Team10-PrintTrack



Public Trello board:

https://trello.com/b/Chwb3R3h/cse325-team-10-printtrack



The GitHub repository and Trello board are public for instructor review. Wilfredo Jose Marapacuto Verastegui is currently the sole participant and repository owner. Any additional assigned team members will be invited as GitHub collaborators and Trello board members.

