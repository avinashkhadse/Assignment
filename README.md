Instructions to Run the C# Client Application Locally

Requirements:

1. Install .NET SDK:
   - Download and install the [.NET SDK](https://dotnet.microsoft.com/download) (version 6.0 or higher).

2. Install Node.js:
   - Ensure you have [Node.js](https://nodejs.org/) (version 16.17.0 or higher) installed.  
   - Verify the version by running:
    node -v/node -version
     
   - If not installed, download it from the Node.js website and follow the installation instructions.

3. Download the ABX Exchange Server:
   - Unzip the provided 'abx_exchange_server' zip file.

4. C# Project Setup:
   - Clone or download the C# client application code (from the GitHub repository you create) to your local machine.


Steps to Run

1. Start the ABX Exchange Server:
   - Open a terminal or command prompt.
   - Navigate to the folder where the 'abx_exchange_server' was extracted.
   - Run the following command to start the server:
     node main.js
   - The server will start and listen on port '3000'.

2. Build and Run the C# Client:
   - Open the C# project in your preferred IDE (e.g., Visual Studio or Visual Studio Code).
   - Build the project to restore dependencies and compile the code.
   - Run the project using the IDE's run/debug functionality or via the terminal with the following command:
     dotnet run

3. Check the Output:
   - After the program completes, a JSON file named 'output.json' will be generated in the same directory as the executable.
   - Open the 'output.json' file to verify the contents. It will include an array of stock ticker data packets, with no missing sequences.


Example Output

The 'output.json' file will look something like this:

json
[
  {
    "Symbol": "MSFT",
    "BuySell": "B",
    "Quantity": 100,
    "Price": 250,
    "Sequence": 1
  },
  {
    "Symbol": "AAPL",
    "BuySell": "S",
    "Quantity": 50,
    "Price": 145,
    "Sequence": 2
  }
]


Notes

- Error Handling:
  - If the server is not running or unavailable, the client will log an error message.
  - Ensure the server is started before running the C# client.

- Resending Missing Packets:
  - The client will automatically detect missing sequences, request them from the server, and include them in the JSON output.

