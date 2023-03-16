# CS611-Assignment #5
## Fancy Bank
---------------------------------------------------------------------------


## Files
---------------------------------------------------------------------------
### Enums package
1. `AccountEnum` ->  Enum Class for enumerating all possible types of accounts that a user in the bank can create and maintain
2. `LoanEnum` ->  Enum Class for enumerating all possible types of loans that a user can take from the bank
3. `CurrencyEnum` ->  Enum Class for enumerating all possible types of currencies- currently 3 that a user in the bank can deposit and maintain

### Utils package
1. `DatabaseManager` ->  Query collection for Database. All the queries- to insert, select and update data for front end as well as backend functionality is updated in this file.
2. `Utils` ->  Common Tools that is public to all classes. Any function with generic functionality should be updated here.
3. `ColorConstants` ->  Class of Constants that defines each color with a name and corresponding r,g,b values for ease of use in Views
4. `SimpleCollection` ->  An abstract collection class used for storing items. @param <T>
5. `Constants` ->  Constant variables used throughout the system is stored here for clean reuse. For updating any of the values, only this file should be changed

### Factories package
1. `AccountFactory` ->  Factory that generates Account of the required type using the appropriate classes
2. `UserFactory` ->  Factory that generates Users of the required type using the appropriate classes

### Model package
    ### Loan package
    1. `LoanBean` ->  Concrete class that contains all the attributes and methods required to maintain a loan in the bank
    2. `NormalLoan` ->  Concrete class for maintaining functionality related to normal loans. This classes uses the functionality defined in the AbsLoan class
    3. `EducationLoan` ->  Concrete class for maintaining functionality related to education loans. This classes uses the functionality defined in the AbsLoan class
    4. `AbsLoan` ->  Concrete class that holds common properties possessed by each loan record
    
    ### Balance package
    1. `BalanceBean` ->  Concrete class that contains all the attributes and methods required to maintain a bank balance in the Bank
    2. `Deposits` ->  Each Account has this class, this class is responsible for managing the currencies
    
    ### Stocks package
    1. `StockBean` ->  Concrete class that contains all the attributes and methods required to maintain stocks in the Bank
    2. `UserStock` ->  Concrete class for maintaining functionality that associates the user to the stock owned by them.
    3. `StockMarket` ->  Concrete class that contains all the attributes and methods required to transact in the stock market through bank
    
    ### Transactions package
    1. `TransactionBean` ->  Concrete class that contains all the attributes and methods required to perform transactions in the Bank
    2. `Transaction` ->  Concrete class that maintains functionality for performing transactions
    
    ### Accounts package
    1. `SavingAccount` ->  Concrete class for maintaining a Saving account. This classes uses the functionality defined in the AbsAccount class
    2. `AccountBean` ->  Concrete class that contains all the attributes and methods required to maintain an Account in the Bank
    3. `CheckingAccount` ->  Concrete class for maintaining a Checking account. This classes uses the functionality defined in the AbsAccount class
    4. `IAccount` ->  Interface for maintaining an account. This interface defines all the common functionality that is required for each user with an account in the bank
    5. `SecurityAccount` ->  Concrete class for maintaining a Security account. This classes uses the functionality defined in the AbsAccount class
    6. `AbsAccount` ->      Concrete class that holds common properties possessed by each account
    
    ### Collateral package
    1. `ICollateral` ->  Interface for maintaining a collateral. This interface defines all the common functionality that is required for each user with a collateral in the bank
    2. `CollateralBean` ->  Concrete class that contains all the attributes and methods required to maintain a Collateral in the Bank
    3. `CollateralProperty` ->  Concrete class that contains all the attributes and methods required to maintain a Collateral Property in the Bank in case user is unable to repay loan
    4. `AbsCollateral` ->  Concrete class that holds common attributes possessed by each collateral object
    
    ### Users package
    1. `IUser` ->  Interface for maintaining a user in the bank. This interface defines all the common functionality that is required for each user to have in the bank
    2. `NormalUser` ->  Concrete class for maintaining functionality related to a regular user of the bank. It extends the UserEntity class.
    3. `UserEntity` ->  Abstract class for maintaining functionality related to qll users
    4. `UserBean` ->  Concrete class that contains all the attributes and methods required to be a user in the Bank
    5. `SuperUser` ->  Concrete class for maintaining functionality related to a superuser of the bank. It extends the UserEntity class.
    
    ### Currency package
    1. `AbsCurrency` ->  Concrete class that holds common properties possessed by each currency
    2. `EUR_Currency` ->  Concrete class for maintaining functionality related to european currency. This classes uses the functionality defined in the AbsCurrency class
    3. `JPY_Currency` ->  Concrete class for maintaining functionality related to japanese yen currency. This classes uses the functionality defined in the AbsCurrency class
    4. `USD_Currency` ->  Concrete class for maintaining functionality related to US dollars currency. This classes uses the functionality defined in the AbsCurrency class
    5. `ICurrency` ->  Interface for maintaining a currency currency is a collection of a certain type of currency, and can only be converted to us dollars or from us dollars.

### Service package
1. `ATMService` ->  Concrete class for Service that extends the implementation
2. `IService` ->  Interface for Service

### Controllers package
1. `SecurityApplicationController` ->  Controller Class for handling security accounts, connection between user accounts in front end, validation using bankJudge and data in the backend
2. `LoanController` ->  Controller Class for handling connection between loans for user accounts in front end, validation using bankJudge and data in the backend
3. `UserControllerManager` ->  Controller Class where Manager has several controllers and controls all users actions
4. `RegistryController` ->  Controller Class for handling registered users and for connecting between user accounts in front end, validation using bankJudge and data in the backend
5. `AccountController` ->  Controller Class for handling connection between user accounts in front end, validation using bankJudge and data in the backend
6. `TransactionController` ->  Controller Class for handling transactions between user accounts and to connect transactions in front end, validation using bankJudge and data in the backend
7. `LoginController` ->  Controller Class for handling login functionality of user accounts in front end, validation using bankJudge and data in the backend
8. `StockController` ->  Controller Class for handling stocks by connecting stocks in user accounts in front end, validation using bankJudge and data in the backend

### Views package
1. `SecurityApplication` ->  This class allows us to create a page for the customer to open a new Security account. This page takes input from the user to open an account and verifies if the user is an old user with the bank. If yes, it would prompt the user to log in This page lets the customer navigate through different pages.
2. `LoanInformation` ->  This class allows us to create a template for Loan Information bank page. This page is interactive with user. The user can input data to check by when he can pay off the loan based on the interest, type of collateral. This page allows user to navigate through other bank pages.
3. `ManagerViewTransactions` ->  This class allows us to create template for create a bank page for the manager to see all the Bank transactions. This page displays all the transaction details including the time, the type of transaction and customer details. The manager can navigate to other page where he can see all the bank customers.
4. `AccountWithdraw` ->  This class allows us to create a page to display Customer to withdraw the cash in dollars. The amount entered when exceeded shows the user to input amount less than or equal to his balance amount. This page also allows the user to navigate to other pages of Savings Account and Customer Dashboard.
5. `HomePage` ->  This Class allows us to create a template for creating a Home Page for the bank. This page contains details about the bank and the type of bank accounts the bank has to offer The Customer can choose to log in through the Bank's Home page.
7. `ManagerViewOfCustomerLoan` ->  This class allows us to create a template for creating a page for the manager to see a specific customer's loan details. This page prints read only information about the current loan of the customer. The manager can choose to navigate to view all customers.
8. `SecurityTransfer` -> This class allows us to create a page for the customer's security account Transfer Details. The customer can navigate to other bank pages.
9. `BankViewFunctionality` ->  This is a public interface for Bank View Functionality. This is a part of Views Package. This is the first layer of Abstraction.
10. `ImgPanel` ->  This is a class which extends the JPanel to read the images in the project to create a part of the Bank Page.
11. `ViewContainer` ->  This is a class which allows us to create instances of all the web pages previously called. This allows the time taken to load the page reduce drastically. We only return the instances when the pages are called and the data is filled in the template accordingly. The page's visibility is then set to true, until then the previously opened pages can't be seen by the user.
12. `ManagerViewCustomers` ->  This class allows us to create a template for a page to allow the manager to see few of his customers who have a loan with the bank The manager can navigate through pages where he can see the transaction history of the bank.
13. `CheckingsTransfer` ->  This class helps us create a template for a Transfer details page for the Checkings Account. It helps the customer transfer money through wire transfer in 3 different currencies. This page allows user to navigate to other Checkings Page including Account Activity, Account Details and Customer Dashboard.
14. `ParentFrame` ->   This class allows us to create a new form BankJFrame
15. `AccountActivity` ->  This is a class to create a savings activity page for the logged in customer. The customer can view his account balance in dollars. The Transaction history is also being displayed. The customer can navigate to Savings Withdraw and Savings Transfer page. He/She can also go back to the Customer Dashboard.
16. `ManagerViewOfCustomerAccounts` ->  This class allows us to create a template for the page which allows the manager to see a single customer's details. Three options presented on the page - Savings, Security and Checkings. When chosen he can view the specific customer details who have an account with us based on the account type. This page allows the manager to navigate back to viewing all customers.
17. `SellStocks` ->  This class allows us to create a template to create a bank page for the customer to view the stocks he/she holds. The page gives an option to the user to select the stock and enter the number of stocks to sell The customer can also navigate to his dashboard.
18. `StockInfo` ->  This class allows us to create a template for displaying the stock information that bank allows the user to invest in. This page contains read only information. The customer can navigate through the stocks he/she owns page and dashboard.
19. `LoanDetails` ->  This class gives us template to fetch details of the active loan of the customer with the bank The information is read-only. The user can only go back to the dashboard.
20. `SecurityActivity` ->  This class allows us to create an activity page for the customer's security account.The customer can navigate to other bank pages.

21. `CustomerDashboard` ->  This class allows us to template a page for the Customer to see his dashboard. This page allows user to choose to navigate to his/her Savings, checkings and Loan applications. The Customer can also view his current loans. The customer can also open a security account and stock information. This is the first page a customer will see after logging into his account.
22. `SecurityDetails` -> This class allows us to create a page for the customer's security account details.The customer can navigate to other bank pages.
23. `LoanApplication` ->  This is a class which allows us to create a template for the Loan Application Bank Page. The customer can add his/her details including SSN to apply for a loan We are checking if the details mentioned are present in our database prompting the user to login before he/she proceeds with the application The customer can also upload documents as a collateral. This page allows user to navigate to other pages.
24. `CheckingsWithdraw` ->  This class allows us to create a page to display Customer to withdraw the cash in dollars. The amount entered when exceeded shows the user to input amount less than or equal to his balance amount. This page also allows the user to navigate to other pages of Checkings Account and Customer Dashboard.
25. `LoginPage` ->  This class allows us to create a template for a customer to log in to his bank page. This page wants the user to enter his Username and Password. We check if these credentials match in our database. If not, we prompt the user to enter the right details. The user cannot navigate further without entering the right details. Hence, can only move backward to the Home Page.
26. `AccountTransfer` ->  Account Transfer Page - Used to transfer amount from one bank account to the other within or outside the bank This class helps us create a template for a Transfer details page for the Savings Account. It helps the customer transfer money through wire transfer in 3 different currencies. This page allows user to navigate to other Savings Page including Activity, Account Details.
27. `CheckingsActivity` ->  This is a class to create a savings activity page for the logged in customer. The customer can view his account balance in dollars. The Transaction history is also being displayed. The customer can navigate to Checkings Withdraw and Checkings Transfer page. He/She can also go back to the Customer Dashboard.
28. `ManagerViewOfCustomerSecurity` ->  This class allows us to create a template for the page which a manager views specific customer's security account details. This page prints read only information about the specific customer security account. The manager can also navigate through other pages where he can see all the other customers.
29. `ManagerViewOfCustomerSavings` ->  This class allows us to create a template for the page which a manager views specific customer's saving account details. This page prints read only information about the specific customer saving's account.
30. `CheckingsDetails` ->  This class allows us to create a Details page for Checkings Account. This page displays the current account type, account balance, account number and routing number. This page also allows us to navigate to other pages of the Checkings Account and the user Dashboard.
31. `StocksOwned` ->  This class allows us to create a template to create a bank page for the customer to see the stocks he own The customer can navigate to a the page where he can sell the stocks he own and the Customer Dashboard. This page displays read only information for the customer.
32. `SavingsApplication` ->  This class allows us to create a page for the customer to open a new Savings account. This page takes input from the user to open an account and verifies if the user is an old user with the bank. If yes, it would prompt the user to login This page lets the customer navigate through different pages.
33. `ManagerViewAllCustomers` ->  This class allows us to create template for create a bank page for the manager to see all the Bank customers. This page displays all the bank customer details. The manager can navigate to other page where he can see all the recent bank transaction.
34. `AccountDetails` ->  Account Details page is the view/page that the user can use to view the details of the specific account they have chosen This class allows us to create a Details page for Savings Account. This page displays the current account type, account balance, account number and routing number. This page also allows us to navigate to other pages of the Savings Account and the user Dashboard.
35. `SecurityWithdraw` ->  This class allows us to create a page for the customer's security account withdraw details.The customer can navigate to other bank pages.

### Validation package
1. `BankJudge` ->  Validation classs for all components This class handles all required checks - including those for integer components,verifications required from database

## Notes
---------------------------------------------------------------------------
1. Notes to grader -> NIL

## How to compile and run
---------------------------------------------------------------------------
1. Navigate to the directory `src` after unzipping the files
2. Run the following instructions:
>`javac -Xlint:unchecked -d bin com\ood\Main.java`
>`java -cp bin com.ood.Main`