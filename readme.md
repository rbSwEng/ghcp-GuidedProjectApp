# Library App

## Description

Library App is a console-based library management system. It allows users to search for patrons, view and manage their book loans, and handle membership renewals. The application uses JSON files for data storage and is organized with clear separation between core logic, data access, and the user interface.

## Project Structure

- [`ghcp-GuidedProjectApp.sln`](ghcp-GuidedProjectApp.sln )  
  Visual Studio solution file

- [`readme.md`](readme.md )  
  This documentation file

- [`AccelerateDevGitHubCopilot`](AccelerateDevGitHubCopilot )
  - `src/`
    - `Library.ApplicationCore/`
      - `Library.ApplicationCore.csproj`
      - `Entities/`  
        Core domain entities (e.g., Patron, Loan, Book)
      - `Enums/`  
        Enumerations for application logic
      - `Interfaces/`  
        Repository and service interfaces
      - `Services/`  
        Business logic services
    - `Library.Console/`
      - `appSettings.json`  
        Application configuration
      - `CommonActions.cs`  
        Common user actions enum/logic
      - `ConsoleApp.cs`  
        Main console application logic
      - `ConsoleState.cs`  
        State management for the console UI
      - `Library.Console.csproj`
      - `Json/`  
        JSON data files (Authors.json, Books.json, etc.)
      - `Program.cs`  
        Application entry point
    - `Library.Infrastructure/`
      - `Library.Infrastructure.csproj`
      - `Data/`  
        Data access classes (repositories, JSON data loader)
  - `tests/`
    - `UnitTests/`
      - `LoanFactory.cs`  
        Test data factory
      - ...  
        Additional unit tests

## Key Classes and Interfaces

- **Console UI**
  - [`ConsoleApp`](AccelerateDevGitHubCopilot/src/Library.Console/ConsoleApp.cs ): Main application loop and user interaction logic
  - [`Program`](AccelerateDevGitHubCopilot/src/Library.Console/Program.cs ): Application entry point and dependency injection setup

- **Core Logic**
  - `Entities/`: Domain models such as Patron, Loan, Book, Author
  - `Enums/`: Enumerations for states and actions
  - `Interfaces/`: 
    - `IPatronRepository`, `ILoanRepository`: Data access contracts
    - `IPatronService`, `ILoanService`: Business logic contracts
  - `Services/`: Implementations of business logic

- **Data Access**
  - [`JsonData`](AccelerateDevGitHubCopilot/src/Library.Infrastructure/Data/JsonData.cs ): Loads and saves all data from JSON files
  - [`JsonPatronRepository`](AccelerateDevGitHubCopilot/src/Library.Infrastructure/Data/JsonPatronRepository.cs ): Patron data access
  - [`JsonLoanRepository`](AccelerateDevGitHubCopilot/src/Library.Infrastructure/Data/JsonLoanRepository.cs ): Loan data access

- **Testing**
  - `UnitTests/`: Unit tests for core logic and data access

## Usage

1. **Build the solution**  
   Open the solution in Visual Studio or run:
   ```sh
   dotnet build ghcp-GuidedProjectApp.sln
   ```

2. **Run the application**  
   Navigate to the `Library.Console` project directory and run:
   ```sh
   dotnet run --project AccelerateDevGitHubCopilot/src/Library.Console/Library.Console.csproj
   ```

3. **Interact via the console**  
   Follow on-screen prompts to search for patrons, view details, manage loans, and renew memberships.

## License

This project is provided for educational purposes as part of the Guided Project module. See individual files for license
