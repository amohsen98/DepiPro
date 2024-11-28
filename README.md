

SmartElectronics

Welcome to **SmartElectronics**, an e-commerce website for electronics built using **ASP.NET MVC Core**. This project is a practical application of my learning, featuring a fully functional platform with separate areas for customers and administrators.

---

Features

🛒 Customer Area  
- Browse a comprehensive catalog of electronics products.  
- Add items to the cart and proceed to secure checkout using **Stripe** integration.  
- Responsive design for a seamless shopping experience on all devices.

🛠️ Admin Area  
- Perform full **CRUD operations** on:  
  - Products  
  - Categories  
  - Orders  
  - Users  
- Access a **dashboard** to monitor and manage:  
  - Sales  
  - Inventory  
  - Customer activity.  

🔒 Authentication and Authorization  
- **Role-Based Access Control**:  
  - Customers can browse and shop.  
  - Admins can access the Admin Area for management tasks.  
- Implemented **ASP.NET Identity** for user authentication and authorization.  
- Password hashing and secure login mechanisms.  

---

Technologies Used  

- **ASP.NET MVC Core**: Framework for building the application.  
- **Entity Framework Core**: For database management.  
- **ASP.NET Identity**: For authentication and authorization.  
- **Stripe API**: For secure online payments.  
- **HTML5, CSS3, and Bootstrap**: For front-end design and responsiveness.  
- **SQL Server**: As the database engine.  
- **JavaScript and jQuery**: For enhanced interactivity.  

---

Database Setup  

Models Overview  
- **Product**:  
  - `ProductId` (int): Primary Key.  
  - `Name` (string): Name of the product.  
  - `Description` (string): Detailed description.  
  - `Price` (decimal): Price of the product.  
  - `ImageUrl` (string): URL of the product image.  
  - `CategoryId` (int): Foreign Key to Category.  

- **Category**:  
  - `CategoryId` (int): Primary Key.  
  - `Name` (string): Name of the category.  

- **Order**:  
  - `OrderId` (int): Primary Key.  
  - `UserId` (string): Foreign Key to Identity User.  
  - `OrderDate` (DateTime): Date of the order.  
  - `TotalAmount` (decimal): Total price of the order.  
  - **OrderDetails** (navigation property): Collection of ordered products.  

- **OrderDetail**:  
  - `OrderDetailId` (int): Primary Key.  
  - `OrderId` (int): Foreign Key to Order.  
  - `ProductId` (int): Foreign Key to Product.  
  - `Quantity` (int): Number of items ordered.  

Setup Instructions  
1. **Update Connection String**  
   Modify the `appsettings.json` file with your database connection string:  
   ```json
   "ConnectionStrings": {
       "DefaultConnection": "Server=YOUR_SERVER;Database=SmartElectronicsDB;Trusted_Connection=True;"
   }
   ```  

2. **Apply Migrations**  
   Use Entity Framework Core tools to create and apply migrations:  
   ```bash
   dotnet ef migrations add InitialCreate  
   dotnet ef database update  
   ```  

3. **Seed Data**  
   The application includes a database seeding feature to populate initial data for products, categories, and admin user.  

---

Installation and Setup  

1. **Clone the Repository**  
   ```bash
   git clone https://github.com/amohsen98/Electronics-Shop.git  
   cd Electronics-Shop  
   ```  

2. **Restore NuGet Packages**  
   Run the following command in the terminal:  
   ```bash
   dotnet restore  
   ```  

3. **Run the Application**  
   Launch the application:  
   ```bash
   dotnet run  
   ```  

4. Access the application in your browser:  
   - **Customer Area**: `http://localhost:5000`  
   - **Admin Area**: `http://localhost:5000/Admin`  

---

Authentication and Authorization  

- The application uses **ASP.NET Identity** to manage users.  
- Default roles:  
  - `Admin`: Has full access to the Admin Area.  
  - `Customer`: Can browse and purchase products.  
- Admin credentials can be seeded into the database for the first-time setup. Update the seeding logic in the `DbInitializer` class as needed.  

---

Future Enhancements  

- Add product reviews and ratings.  
- Implement advanced search and filtering.  
- Include promotional discounts and coupons.  
- Enhance the dashboard with detailed analytics and reports.  

---

License  

This project is licensed under the MIT License. Feel free to use and modify the code.  

---

Acknowledgements  

- Thanks to **Stripe** for providing excellent payment gateway integration.  
- Special appreciation to the **ASP.NET Core** community for their documentation and support.  

---
