# Full Stack .NET Developer

https://docs.google.com/document/d/1i8nRo7XrtgP86mnXO9Zw2s5JHBZ_ZMoBllSy_QZR15o

https://docs.google.com/document/d/1afLe-ByAAQgjaDozCf2mn5Cu8h-95if3WCew1HMe8g0

# English Special Characters
https://www.webopedia.com/definitions/special-character/

# Tech Stack
* Windows 11
* Windows Server 2022
* Visual Studio 2022
* Visual Studio Code
* IIS 10
* .NET Framework (1.1, ..., 4.8)
* .NET Core (5, 6, 7, 8, 9, 10)
* ASP.NET 4.8
* ASP.NET MVC 5
* ASP.NET Web API 2
* ASP.NET Core 10.0
* ASP.NET Core MVC
* ASP.NET Core Web API
* ASP.NET Core Blazor
* EF 6.x
* EF Core
* C#
* Blazor
* SignalR
* LINQ
* WPF
* WCF
* Web Services
* Azure Functions and App Services integration
* SQL Server
* T-SQL
* ADO.NET
* Stored Procedure
* Dapper
* CsvHelper
* Log4Net
* Serilog
* PowerShell
* HTML
* CSS
* Bootstrap
* Google Fronts
* JavaScript
* jQuery
  * jQuery Datatables
  * jQuery Plugins
* Git for Windows
* GitHub
* Node.js
* Java
* Solr
* Python
* Ember.js
* Chrome
* Firefox
* Azure
* AWS
* Search Engine
* Email Knowledge Management System Since 2004

# Tools, Libraries & Frameworks
* **Robocopy** (Command Line)
* [**Image to Text Converter: An online image to text converter to extract text from images**](https://www.imagetotext.info/)
* ShareX
* Sourcetree
* Postulate Zinger
* Beyond Compare
* Baretail
* ZZZ Projects's Find and Replace (FNR)
* POCO Generator
* EzDbCodeGen
* DbUp
* Starter Kit
* Github Pages Template
* Boilerplate Template
* HTML5 Boilerplate
* HTML5 UP! Responsive HTML5 and CSS3 Site Templates
* ASP.NET Boilerplate
* Clean Architecture Solution Template
* Clean Code for .NET Coding Craftsman
* Umbraco
* Codemaid
* PoorMansTSqlFormatter
* ICsharpCode Code Converter (ICSharpCode.CodeConverter)
* SharpDevelop Code Converter
* Fortify Static Code Analyzer (SCA)
* Fortify Software Security Center (SSC)
* Wireshark
* Firebug
* Fiddler
* Burp Suite
* OWASP Zed Attack Proxy (ZAP)
* Source Generators in C#
* Free AI Code Generation
* Free AI-Powered .NET Code Generator: Build Enterprise-Ready Apps Fast
* OWASP Top 10 Vulnerabilities
* SOLID
* OOP
* Clean Code
* Unit Testing
* **pdevito3 craftsman** (Wrapt)

# Exception Handling

## System.IO.PathTooLongException

The specified path, file name, or both are too long. The fully qualified file name must be less than 260 characters, and the directory name must be less than 248 characters.

* Use **AlphaFS** if you need **symbolic link support**, deeper file system operations, and are working only on Windows.
* Use ZetaLongPaths if you need **cross-platform support**, a simpler API, and just need basic file handling with long paths.

## Boilerplate List
* [Boilerplate List](https://boilerplatelist.com)
* [Next Boiler Plate - Black Friday Sale Live](https://www.nextboilerplate.com/)
* [Top 5 AI SaaS Boilerplates of 2025](https://realtors.medium.com/top-5-ai-saas-boilerplates-of-2025-why-nextboilerplate-reigns-supreme-e7981595c993)
* [Top 70 Next.js SaaS Boilerplates 2025](https://boilerplatelist.com/collections/top-next-js-saas-boilerplates/)
* [Best SaaS Boilerplates of 2025](https://slashdot.org/software/saas-boilerplates/)

## Top 12+ Battle-Tested React Boilerplates for 2024
https://dev.to/rodik/top-12-battle-tested-react-boilerplates-for-2024-f6i

## Site build in Umbraco v9 and .NET 5.0
https://github.com/gtechsltn/UmbracoNineDemoSite

## Clean Code
* https://medium.com/hackernoon/clean-code-for-net-coding-craftsman-7674373fccaf
* https://github.com/thangchung/clean-code-dotnet

# Craftsman Scaffolds Your Boilerplate!

A .NET scaffolding tool to help you stop worrying about boilerplate and focus on your business logic 🚀

## 1. Wrapt

Skip the boilerplate and focus on your business logic. 

Scaffold an entire .NET Web API with a simple yaml or json file so you can focus on the high value features in your web app.

* https://wrapt.dev/
* https://github.com/GrahamDumpleton/wrapt
* https://wrapt.dev/docs/how-it-works

## 2. Craftsman

A .NET scaffolding tool to help you stop worrying about boilerplate and focus on your business logic 🚀

* https://www.nuget.org/packages/Craftsman
* https://github.com/pdevito3/craftsman
 
## 3. Source Code For Lesson One Of Creating Dot Net Web Api and Microservices With Craftsman
* https://www.youtube.com/watch?v=rcRPvOh-q_8
* https://github.com/benjaminsqlserver/MuyikRecipeManagement
* https://github.com/gtechsltn/MuyikRecipeManagement

# File Path To Long

If you need filename management with GUIDs while keeping track of files (e.g., saving, retrieving, deleting, or mapping GUIDs to original names), you can create a FileManager class.


## Perhaps we should have used GUID for filename

Using a GUID for filenames is a great way to ensure uniqueness and avoid long file path issues. Here's how you can generate a GUID-based filename in C#:

```
using System;
using System.IO;

class Program
{
    static void Main()
    {
        string folderPath = @"C:\MyLongPathFolder";
        
        // Ensure the directory exists
        Directory.CreateDirectory(folderPath);

        // Generate a unique filename using GUID
        string fileName = $"{Guid.NewGuid()}.txt";
        string filePath = Path.Combine(folderPath, fileName);

        try
        {
            // Write content to the file
            File.WriteAllText(filePath, "This is a test file with a GUID-based filename.");
            Console.WriteLine($"File created successfully: {filePath}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"Error: {ex.Message}");
        }
    }
}
```

## 📌 File Management with GUID-based Filenames
* This example demonstrates:
* ✔️ Generating GUID filenames
* ✔️ Mapping GUIDs to original filenames
* ✔️ Saving, retrieving, and deleting files

### Create a FileManager Class
```
using System;
using System.Collections.Generic;
using System.IO;

class FileManager
{
    private readonly string storagePath;
    private readonly Dictionary<string, string> fileMapping; // Maps GUID to original filename

    public FileManager(string path)
    {
        storagePath = path;
        Directory.CreateDirectory(storagePath); // Ensure storage folder exists
        fileMapping = new Dictionary<string, string>();
    }

    // Save a file with a GUID-based filename
    public string SaveFile(string originalFileName, string content)
    {
        string guid = Guid.NewGuid().ToString();
        string fileExtension = Path.GetExtension(originalFileName);
        string newFileName = $"{guid}{fileExtension}";
        string filePath = Path.Combine(storagePath, newFileName);

        File.WriteAllText(filePath, content);
        fileMapping[guid] = originalFileName; // Store mapping

        Console.WriteLine($"File saved: {originalFileName} -> {newFileName}");
        return guid; // Return GUID to reference the file later
    }

    // Retrieve the original filename from GUID
    public string GetOriginalFileName(string guid)
    {
        return fileMapping.TryGetValue(guid, out string originalFileName) ? originalFileName : null;
    }

    // Retrieve file content
    public string ReadFile(string guid)
    {
        string fileName = $"{guid}.txt"; // Assuming .txt, can extend for other types
        string filePath = Path.Combine(storagePath, fileName);

        return File.Exists(filePath) ? File.ReadAllText(filePath) : null;
    }

    // Delete file by GUID
    public bool DeleteFile(string guid)
    {
        string fileName = $"{guid}.txt"; // Assuming .txt, adjust as needed
        string filePath = Path.Combine(storagePath, fileName);

        if (File.Exists(filePath))
        {
            File.Delete(filePath);
            fileMapping.Remove(guid);
            Console.WriteLine($"File deleted: {fileName}");
            return true;
        }
        return false;
    }
}
```
### Usage Example
```
class Program
{
    static void Main()
    {
        string folderPath = @"C:\FileStorage";
        FileManager fileManager = new FileManager(folderPath);

        // Save a file
        string guid = fileManager.SaveFile("Report.pdf", "This is a sample file content.");

        // Retrieve the original filename
        string originalFileName = fileManager.GetOriginalFileName(guid);
        Console.WriteLine($"Original Filename: {originalFileName}");

        // Read file content
        string content = fileManager.ReadFile(guid);
        Console.WriteLine($"File Content: {content}");

        // Delete file
        fileManager.DeleteFile(guid);
    }
}
```

## 📌 Benefits of This Approach
* ✅ Shorter Paths – Avoids long filenames.
* ✅ File Tracking – Keeps a mapping of GUIDs to original filenames.
* ✅ Security – Prevents predictable filenames.
* ✅ Scalable – Can be used in cloud storage or databases.

Would you like me to extend this with database storage for mappings? 🚀

