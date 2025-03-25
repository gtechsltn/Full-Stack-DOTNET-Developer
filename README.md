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

This example demonstrates:
 
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


## 📌 File Management with GUID-Based Filenames & Database Storage

This implementation will:

* ✔️ Store file metadata (GUID, original filename, path) in a SQL Server database
* ✔️ Save, retrieve, and delete files using C# and Dapper
* ✔️ Ensure efficient file tracking and management

### Database Table: FileStorage
```
CREATE TABLE FileStorage (
    Id UNIQUEIDENTIFIER PRIMARY KEY DEFAULT NEWID(),
    OriginalFileName NVARCHAR(255) NOT NULL,
    StoredFileName NVARCHAR(255) NOT NULL,
    FilePath NVARCHAR(500) NOT NULL,
    CreatedAt DATETIME DEFAULT GETDATE()
);
```

### Nuget Packages
```
Install-Package Dapper
Install-Package System.Data.SqlClient
```

### FileManager Class with Database Storage

```
using System;
using System.Data;
using System.Data.SqlClient;
using System.IO;
using Dapper;

class FileManager
{
    private readonly string storagePath;
    private readonly string connectionString;

    public FileManager(string storagePath, string connectionString)
    {
        this.storagePath = storagePath;
        this.connectionString = connectionString;
        Directory.CreateDirectory(storagePath); // Ensure folder exists
    }

    // Save a file and store metadata in the database
    public Guid SaveFile(string originalFileName, string content)
    {
        Guid fileId = Guid.NewGuid();
        string fileExtension = Path.GetExtension(originalFileName);
        string storedFileName = $"{fileId}{fileExtension}";
        string filePath = Path.Combine(storagePath, storedFileName);

        // Save file to disk
        File.WriteAllText(filePath, content);

        // Insert metadata into the database
        using (IDbConnection db = new SqlConnection(connectionString))
        {
            string sql = @"INSERT INTO FileStorage (Id, OriginalFileName, StoredFileName, FilePath) 
                           VALUES (@Id, @OriginalFileName, @StoredFileName, @FilePath)";
            db.Execute(sql, new { Id = fileId, OriginalFileName = originalFileName, StoredFileName = storedFileName, FilePath = filePath });
        }

        Console.WriteLine($"File saved: {originalFileName} -> {storedFileName}");
        return fileId;
    }

    // Retrieve the original filename from GUID
    public string GetOriginalFileName(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(connectionString))
        {
            string sql = "SELECT OriginalFileName FROM FileStorage WHERE Id = @Id";
            return db.QueryFirstOrDefault<string>(sql, new { Id = fileId });
        }
    }

    // Retrieve file content
    public string ReadFile(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(connectionString))
        {
            string sql = "SELECT FilePath FROM FileStorage WHERE Id = @Id";
            string filePath = db.QueryFirstOrDefault<string>(sql, new { Id = fileId });

            return File.Exists(filePath) ? File.ReadAllText(filePath) : null;
        }
    }

    // Delete file from disk and database
    public bool DeleteFile(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(connectionString))
        {
            // Get file path
            string sql = "SELECT FilePath FROM FileStorage WHERE Id = @Id";
            string filePath = db.QueryFirstOrDefault<string>(sql, new { Id = fileId });

            if (!string.IsNullOrEmpty(filePath) && File.Exists(filePath))
            {
                File.Delete(filePath);

                // Delete from database
                string deleteSql = "DELETE FROM FileStorage WHERE Id = @Id";
                db.Execute(deleteSql, new { Id = fileId });

                Console.WriteLine($"File deleted: {filePath}");
                return true;
            }
        }
        return false;
    }
}
```

### Usage
```
class Program
{
    static void Main()
    {
        string folderPath = @"C:\FileStorage";
        string connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";

        FileManager fileManager = new FileManager(folderPath, connectionString);

        // Save a file
        Guid fileId = fileManager.SaveFile("Report.pdf", "This is a sample file content.");

        // Retrieve original filename
        string originalFileName = fileManager.GetOriginalFileName(fileId);
        Console.WriteLine($"Original Filename: {originalFileName}");

        // Read file content
        string content = fileManager.ReadFile(fileId);
        Console.WriteLine($"File Content: {content}");

        // Delete file
        fileManager.DeleteFile(fileId);
    }
}
```

### 📌 Why Use This Approach?
* ✅ Shorter Paths – Uses GUIDs to avoid long filename issues.
* ✅ File Tracking – Stores metadata in SQL Server.
* ✅ Security – Prevents guessing file paths.
* ✅ Scalability – Works well for large-scale storage.

## 📌 ASP.NET Core Web API for File Management (GUID-Based Filenames & Database Storage)

This API will:

* ✔️ Allow file upload, retrieval, and deletion via endpoints
* ✔️ Use GUID filenames for uniqueness and to avoid long path issues
* ✔️ Store metadata in SQL Server using Dapper

```
Install-Package Dapper
Install-Package Microsoft.AspNetCore.Http.Features
Install-Package Microsoft.Data.SqlClient
```

### Create FileManagerService.cs for File Operations
```
using System;
using System.Collections.Generic;
using System.Data;
using System.Data.SqlClient;
using System.IO;
using System.Threading.Tasks;
using Dapper;
using Microsoft.AspNetCore.Http;

public class FileManagerService
{
    private readonly string _storagePath;
    private readonly string _connectionString;

    public FileManagerService(string storagePath, string connectionString)
    {
        _storagePath = storagePath;
        _connectionString = connectionString;
        Directory.CreateDirectory(_storagePath); // Ensure storage folder exists
    }

    // Upload file
    public async Task<Guid> SaveFileAsync(IFormFile file)
    {
        Guid fileId = Guid.NewGuid();
        string fileExtension = Path.GetExtension(file.FileName);
        string storedFileName = $"{fileId}{fileExtension}";
        string filePath = Path.Combine(_storagePath, storedFileName);

        // Save file to disk
        using (var stream = new FileStream(filePath, FileMode.Create))
        {
            await file.CopyToAsync(stream);
        }

        // Insert metadata into database
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = @"INSERT INTO FileStorage (Id, OriginalFileName, StoredFileName, FilePath) 
                           VALUES (@Id, @OriginalFileName, @StoredFileName, @FilePath)";
            db.Execute(sql, new { Id = fileId, OriginalFileName = file.FileName, StoredFileName = storedFileName, FilePath = filePath });
        }

        return fileId;
    }

    // Get file metadata
    public async Task<string> GetOriginalFileNameAsync(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "SELECT OriginalFileName FROM FileStorage WHERE Id = @Id";
            return await db.QueryFirstOrDefaultAsync<string>(sql, new { Id = fileId });
        }
    }

    // Download file
    public async Task<(string, byte[])> GetFileAsync(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "SELECT OriginalFileName, FilePath FROM FileStorage WHERE Id = @Id";
            var result = await db.QueryFirstOrDefaultAsync<(string, string)>(sql, new { Id = fileId });

            if (result == default || !File.Exists(result.Item2))
                return (null, null);

            byte[] fileBytes = await File.ReadAllBytesAsync(result.Item2);
            return (result.Item1, fileBytes);
        }
    }

    // Delete file
    public async Task<bool> DeleteFileAsync(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "SELECT FilePath FROM FileStorage WHERE Id = @Id";
            string filePath = await db.QueryFirstOrDefaultAsync<string>(sql, new { Id = fileId });

            if (!string.IsNullOrEmpty(filePath) && File.Exists(filePath))
            {
                File.Delete(filePath);

                // Delete from database
                string deleteSql = "DELETE FROM FileStorage WHERE Id = @Id";
                await db.ExecuteAsync(deleteSql, new { Id = fileId });

                return true;
            }
        }
        return false;
    }
}
```

### Create FileController.cs
```
using Microsoft.AspNetCore.Mvc;
using System;
using System.IO;
using System.Threading.Tasks;

[Route("api/files")]
[ApiController]
public class FileController : ControllerBase
{
    private readonly FileManagerService _fileManagerService;

    public FileController(FileManagerService fileManagerService)
    {
        _fileManagerService = fileManagerService;
    }

    // Upload file
    [HttpPost("upload")]
    public async Task<IActionResult> UploadFile([FromForm] IFormFile file)
    {
        if (file == null || file.Length == 0)
            return BadRequest("Invalid file.");

        Guid fileId = await _fileManagerService.SaveFileAsync(file);
        return Ok(new { FileId = fileId });
    }

    // Download file
    [HttpGet("download/{fileId}")]
    public async Task<IActionResult> DownloadFile(Guid fileId)
    {
        var (originalFileName, fileBytes) = await _fileManagerService.GetFileAsync(fileId);

        if (fileBytes == null)
            return NotFound("File not found.");

        return File(fileBytes, "application/octet-stream", originalFileName);
    }

    // Get file metadata
    [HttpGet("metadata/{fileId}")]
    public async Task<IActionResult> GetFileMetadata(Guid fileId)
    {
        string originalFileName = await _fileManagerService.GetOriginalFileNameAsync(fileId);
        if (string.IsNullOrEmpty(originalFileName))
            return NotFound("File metadata not found.");

        return Ok(new { FileId = fileId, OriginalFileName = originalFileName });
    }

    // Delete file
    [HttpDelete("delete/{fileId}")]
    public async Task<IActionResult> DeleteFile(Guid fileId)
    {
        bool deleted = await _fileManagerService.DeleteFileAsync(fileId);
        if (!deleted)
            return NotFound("File not found.");

        return Ok("File deleted successfully.");
    }
}
```

### Configure Program.cs

Modify Program.cs to register FileManagerService:

```
var builder = WebApplication.CreateBuilder(args);

builder.Services.AddControllers();
builder.Services.AddEndpointsApiExplorer();
builder.Services.AddSwaggerGen();

string storagePath = @"C:\FileStorage";  // Change to your directory
string connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";

builder.Services.AddSingleton(new FileManagerService(storagePath, connectionString));

var app = builder.Build();

app.UseSwagger();
app.UseSwaggerUI();
app.UseAuthorization();
app.MapControllers();
app.Run();
```

## Test API Endpoints (Using Postman or Swagger)
### Upload File:
POST /api/files/upload → Upload a file via form-data.

### Download File:
GET /api/files/download/{fileId} → Retrieves the file.

### Get File Metadata:
GET /api/files/metadata/{fileId} → Retrieves original filename.

### Delete File:
DELETE /api/files/delete/{fileId} → Deletes the file.

## 📌 Why This Approach?
* ✅ Shorter Paths – Avoids long filename issues.
* ✅ Efficient File Tracking – Stores metadata in SQL Server.
* ✅ Security – Prevents guessing file paths.
* ✅ Scalable – Works well for cloud storage and distributed systems.

## File Encryption or Access Control

📌 File Encryption & Access Control in ASP.NET Core Web API
This implementation will:

* ✔️ Encrypt & Decrypt Files before saving/retrieving
* ✔️ Access Control using authentication & authorization

```
Install-Package System.Security.Cryptography
Install-Package Microsoft.AspNetCore.Authentication.JwtBearer
Install-Package Microsoft.AspNetCore.Authorization
```

### Add Encryption & Decryption

#### Encryption Helper Class
```
using System;
using System.IO;
using System.Security.Cryptography;
using System.Text;

public class EncryptionHelper
{
    private readonly byte[] _key;
    private readonly byte[] _iv;

    public EncryptionHelper(string secretKey)
    {
        using (SHA256 sha256 = SHA256.Create())
        {
            _key = sha256.ComputeHash(Encoding.UTF8.GetBytes(secretKey));
            _iv = new byte[16]; // 16-byte IV for AES
        }
    }

    public byte[] Encrypt(byte[] data)
    {
        using (Aes aes = Aes.Create())
        {
            aes.Key = _key;
            aes.IV = _iv;

            using (MemoryStream ms = new MemoryStream())
            using (CryptoStream cs = new CryptoStream(ms, aes.CreateEncryptor(), CryptoStreamMode.Write))
            {
                cs.Write(data, 0, data.Length);
                cs.FlushFinalBlock();
                return ms.ToArray();
            }
        }
    }

    public byte[] Decrypt(byte[] encryptedData)
    {
        using (Aes aes = Aes.Create())
        {
            aes.Key = _key;
            aes.IV = _iv;

            using (MemoryStream ms = new MemoryStream())
            using (CryptoStream cs = new CryptoStream(ms, aes.CreateDecryptor(), CryptoStreamMode.Write))
            {
                cs.Write(encryptedData, 0, encryptedData.Length);
                cs.FlushFinalBlock();
                return ms.ToArray();
            }
        }
    }
}
```

### Modify FileManagerService.cs
```
public class FileManagerService
{
    private readonly string _storagePath;
    private readonly string _connectionString;
    private readonly EncryptionHelper _encryptionHelper;

    public FileManagerService(string storagePath, string connectionString, string secretKey)
    {
        _storagePath = storagePath;
        _connectionString = connectionString;
        _encryptionHelper = new EncryptionHelper(secretKey);
        Directory.CreateDirectory(_storagePath);
    }

    // Encrypt & Save File
    public async Task<Guid> SaveFileAsync(IFormFile file)
    {
        Guid fileId = Guid.NewGuid();
        string fileExtension = Path.GetExtension(file.FileName);
        string storedFileName = $"{fileId}{fileExtension}";
        string filePath = Path.Combine(_storagePath, storedFileName);

        using (var memoryStream = new MemoryStream())
        {
            await file.CopyToAsync(memoryStream);
            byte[] encryptedData = _encryptionHelper.Encrypt(memoryStream.ToArray());
            await File.WriteAllBytesAsync(filePath, encryptedData);
        }

        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = @"INSERT INTO FileStorage (Id, OriginalFileName, StoredFileName, FilePath) 
                           VALUES (@Id, @OriginalFileName, @StoredFileName, @FilePath)";
            db.Execute(sql, new { Id = fileId, OriginalFileName = file.FileName, StoredFileName = storedFileName, FilePath = filePath });
        }

        return fileId;
    }

    // Decrypt & Retrieve File
    public async Task<(string, byte[])> GetFileAsync(Guid fileId)
    {
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "SELECT OriginalFileName, FilePath FROM FileStorage WHERE Id = @Id";
            var result = await db.QueryFirstOrDefaultAsync<(string, string)>(sql, new { Id = fileId });

            if (result == default || !File.Exists(result.Item2))
                return (null, null);

            byte[] encryptedData = await File.ReadAllBytesAsync(result.Item2);
            byte[] decryptedData = _encryptionHelper.Decrypt(encryptedData);
            return (result.Item1, decryptedData);
        }
    }
}
```

## Implement Authentication & Authorization

Modify Program.cs to add JWT-based authentication:

🔑 Configure JWT Authentication

🔑 Store securely in appsettings.json or environment variables

```
var builder = WebApplication.CreateBuilder(args);

var secretKey = "YourSuperSecretKeyHere";
string storagePath = @"C:\FileStorage";
string connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";

// Register services
builder.Services.AddSingleton(new FileManagerService(storagePath, connectionString, secretKey));

builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        options.RequireHttpsMetadata = false;
        options.SaveToken = true;
        options.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters
        {
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new Microsoft.IdentityModel.Tokens.SymmetricSecurityKey(Encoding.UTF8.GetBytes(secretKey)),
            ValidateIssuer = false,
            ValidateAudience = false
        };
    });

builder.Services.AddAuthorization();

var app = builder.Build();
app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();
app.Run();
```

### Secure API Endpoints

Modify FileController.cs to require authentication.

```
[Authorize] // 🔒 Require authentication for all endpoints
[Route("api/files")]
[ApiController]
public class FileController : ControllerBase
{
    private readonly FileManagerService _fileManagerService;

    public FileController(FileManagerService fileManagerService)
    {
        _fileManagerService = fileManagerService;
    }

    [HttpPost("upload")]
    public async Task<IActionResult> UploadFile([FromForm] IFormFile file)
    {
        if (file == null || file.Length == 0)
            return BadRequest("Invalid file.");

        Guid fileId = await _fileManagerService.SaveFileAsync(file);
        return Ok(new { FileId = fileId });
    }

    [HttpGet("download/{fileId}")]
    public async Task<IActionResult> DownloadFile(Guid fileId)
    {
        var (originalFileName, fileBytes) = await _fileManagerService.GetFileAsync(fileId);

        if (fileBytes == null)
            return NotFound("File not found.");

        return File(fileBytes, "application/octet-stream", originalFileName);
    }

    [HttpDelete("delete/{fileId}")]
    public async Task<IActionResult> DeleteFile(Guid fileId)
    {
        bool deleted = await _fileManagerService.DeleteFileAsync(fileId);
        if (!deleted)
            return NotFound("File not found.");

        return Ok("File deleted successfully.");
    }
}
```

### Generate JWT Tokens for Access

Create a AuthController.cs to issue JWT tokens.

```
using Microsoft.AspNetCore.Mvc;
using System;
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Text;
using Microsoft.IdentityModel.Tokens;

[Route("api/auth")]
[ApiController]
public class AuthController : ControllerBase
{
    private readonly string _secretKey = "YourSuperSecretKeyHere"; // Store securely

    [HttpPost("login")]
    public IActionResult Login([FromBody] LoginRequest request)
    {
        if (request.Username == "admin" && request.Password == "password") // Replace with real user validation
        {
            var tokenHandler = new JwtSecurityTokenHandler();
            var key = Encoding.UTF8.GetBytes(_secretKey);
            var tokenDescriptor = new SecurityTokenDescriptor
            {
                Subject = new ClaimsIdentity(new[] { new Claim(ClaimTypes.Name, request.Username) }),
                Expires = DateTime.UtcNow.AddHours(1),
                SigningCredentials = new SigningCredentials(new SymmetricSecurityKey(key), SecurityAlgorithms.HmacSha256Signature)
            };
            var token = tokenHandler.CreateToken(tokenDescriptor);
            return Ok(new { Token = tokenHandler.WriteToken(token) });
        }
        return Unauthorized();
    }
}

public class LoginRequest
{
    public string Username { get; set; }
    public string Password { get; set; }
}
```

### 📌 Summary
* ✔ Files are Encrypted Before Storage 🔐
* ✔ Only Authenticated Users Can Access Files 🔑
* ✔ Files are Decrypted Only When Retrieved 🔓

## Role-Based Access Control (RBAC) for different user permissions

📌 Role-Based Access Control (RBAC) with Admin Role in ASP.NET Core Web API

This implementation will:

* ✔ Use JWT for Authentication 🔑
* ✔ Implement Role-Based Authorization (Admin vs. Regular Users) 🔒
* ✔ Restrict File Management Endpoints to Admins Only 🚀

### Modify JWT Token Generation to Include Roles

Update AuthController.cs to include roles in JWT tokens.

```
[Route("api/auth")]
[ApiController]
public class AuthController : ControllerBase
{
    private readonly string _secretKey = "YourSuperSecretKeyHere"; // Store securely

    [HttpPost("login")]
    public IActionResult Login([FromBody] LoginRequest request)
    {
        // Mock user authentication (Replace with real user validation from a database)
        string userRole = request.Username == "admin" ? "Admin" : "User";

        var tokenHandler = new JwtSecurityTokenHandler();
        var key = Encoding.UTF8.GetBytes(_secretKey);
        var tokenDescriptor = new SecurityTokenDescriptor
        {
            Subject = new ClaimsIdentity(new[]
            {
                new Claim(ClaimTypes.Name, request.Username),
                new Claim(ClaimTypes.Role, userRole) // Assign Role
            }),
            Expires = DateTime.UtcNow.AddHours(1),
            SigningCredentials = new SigningCredentials(new SymmetricSecurityKey(key), SecurityAlgorithms.HmacSha256Signature)
        };
        var token = tokenHandler.CreateToken(tokenDescriptor);

        return Ok(new { Token = tokenHandler.WriteToken(token) });
    }
}

public class LoginRequest
{
    public string Username { get; set; }
    public string Password { get; set; }
}
```

### Enforce Role-Based Access in API Endpoints

Modify FileController.cs to restrict file operations to Admins.

```
[Authorize] // Require authentication for all endpoints
[Route("api/files")]
[ApiController]
public class FileController : ControllerBase
{
    private readonly FileManagerService _fileManagerService;

    public FileController(FileManagerService fileManagerService)
    {
        _fileManagerService = fileManagerService;
    }

    [Authorize(Roles = "Admin")] // Only Admins can upload files
    [HttpPost("upload")]
    public async Task<IActionResult> UploadFile([FromForm] IFormFile file)
    {
        if (file == null || file.Length == 0)
            return BadRequest("Invalid file.");

        Guid fileId = await _fileManagerService.SaveFileAsync(file);
        return Ok(new { FileId = fileId });
    }

    [Authorize] // Both Users and Admins can download files
    [HttpGet("download/{fileId}")]
    public async Task<IActionResult> DownloadFile(Guid fileId)
    {
        var (originalFileName, fileBytes) = await _fileManagerService.GetFileAsync(fileId);

        if (fileBytes == null)
            return NotFound("File not found.");

        return File(fileBytes, "application/octet-stream", originalFileName);
    }

    [Authorize(Roles = "Admin")] // Only Admins can delete files
    [HttpDelete("delete/{fileId}")]
    public async Task<IActionResult> DeleteFile(Guid fileId)
    {
        bool deleted = await _fileManagerService.DeleteFileAsync(fileId);
        if (!deleted)
            return NotFound("File not found.");

        return Ok("File deleted successfully.");
    }
}
```

### Update Program.cs to Support Role-Based Authentication

Ensure JWT authentication is properly configured.

```
var builder = WebApplication.CreateBuilder(args);

var secretKey = "YourSuperSecretKeyHere"; // 🔑 Store securely
string storagePath = @"C:\FileStorage";
string connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";

// Register services
builder.Services.AddSingleton(new FileManagerService(storagePath, connectionString, secretKey));

builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        options.RequireHttpsMetadata = false;
        options.SaveToken = true;
        options.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters
        {
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new Microsoft.IdentityModel.Tokens.SymmetricSecurityKey(Encoding.UTF8.GetBytes(secretKey)),
            ValidateIssuer = false,
            ValidateAudience = false,
            RoleClaimType = ClaimTypes.Role // Ensure role claims are recognized
        };
    });

builder.Services.AddAuthorization();

var app = builder.Build();
app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();
app.Run();
```

### Test the Implementation

🛠️ Generate JWT Token

Admin User (Can Upload & Delete)

```
{
  "username": "admin",
  "password": "password"
}
```

Regular User (Can Only Download)

{
  "username": "user",
  "password": "password"
}

#### Restricted Endpoints

POST /api/files/upload → Only Admin

DELETE /api/files/delete/{fileId} → Only Admin

GET /api/files/download/{fileId} → Admin & Users

### 📌 Summary
* ✅ Admins Can Upload & Delete Files 🔒
* ✅ Regular Users Can Only Download 📥
* ✅ JWT Tokens Now Include Roles 🔑

## Add user registration with role selection

### 📌 User Registration with Role Selection in ASP.NET Core Web API

This implementation will:

* ✔ Allow users to register with a role (Admin/User)
* ✔ Store user credentials securely in a database
* ✔ Validate login and issue JWT tokens with roles

```
CREATE TABLE Users (
    Id UNIQUEIDENTIFIER PRIMARY KEY DEFAULT NEWID(),
    Username NVARCHAR(50) UNIQUE NOT NULL,
    PasswordHash NVARCHAR(255) NOT NULL,
    Role NVARCHAR(10) NOT NULL CHECK (Role IN ('Admin', 'User'))
);
```

### Modify AuthController.cs for Registration & Login

Replace your existing AuthController.cs with the following:
```
using Microsoft.AspNetCore.Mvc;
using System;
using System.Data;
using System.Data.SqlClient;
using System.IdentityModel.Tokens.Jwt;
using System.Security.Claims;
using System.Security.Cryptography;
using System.Text;
using Dapper;
using Microsoft.IdentityModel.Tokens;

[Route("api/auth")]
[ApiController]
public class AuthController : ControllerBase
{
    private readonly string _connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";
    private readonly string _secretKey = "YourSuperSecretKeyHere"; // Store securely

    // ✅ REGISTER NEW USER
    [HttpPost("register")]
    public async Task<IActionResult> Register([FromBody] RegisterRequest request)
    {
        if (string.IsNullOrWhiteSpace(request.Username) || string.IsNullOrWhiteSpace(request.Password))
            return BadRequest("Username and password are required.");

        if (request.Role != "Admin" && request.Role != "User")
            return BadRequest("Invalid role. Choose 'Admin' or 'User'.");

        string passwordHash = HashPassword(request.Password);

        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "INSERT INTO Users (Username, PasswordHash, Role) VALUES (@Username, @PasswordHash, @Role)";
            try
            {
                await db.ExecuteAsync(sql, new { request.Username, PasswordHash = passwordHash, request.Role });
                return Ok("User registered successfully.");
            }
            catch (SqlException ex) when (ex.Number == 2627) // Unique constraint violation
            {
                return Conflict("Username already exists.");
            }
        }
    }

    // ✅ LOGIN AND GET JWT TOKEN
    [HttpPost("login")]
    public async Task<IActionResult> Login([FromBody] LoginRequest request)
    {
        using (IDbConnection db = new SqlConnection(_connectionString))
        {
            string sql = "SELECT PasswordHash, Role FROM Users WHERE Username = @Username";
            var user = await db.QueryFirstOrDefaultAsync<User>(sql, new { request.Username });

            if (user == null || !VerifyPassword(request.Password, user.PasswordHash))
                return Unauthorized("Invalid username or password.");

            var token = GenerateJwtToken(request.Username, user.Role);
            return Ok(new { Token = token });
        }
    }

    // 🔑 GENERATE JWT TOKEN WITH ROLE
    private string GenerateJwtToken(string username, string role)
    {
        var tokenHandler = new JwtSecurityTokenHandler();
        var key = Encoding.UTF8.GetBytes(_secretKey);
        var tokenDescriptor = new SecurityTokenDescriptor
        {
            Subject = new ClaimsIdentity(new[]
            {
                new Claim(ClaimTypes.Name, username),
                new Claim(ClaimTypes.Role, role)
            }),
            Expires = DateTime.UtcNow.AddHours(1),
            SigningCredentials = new SigningCredentials(new SymmetricSecurityKey(key), SecurityAlgorithms.HmacSha256Signature)
        };
        var token = tokenHandler.CreateToken(tokenDescriptor);
        return tokenHandler.WriteToken(token);
    }

    // 🔐 HASH PASSWORD
    private string HashPassword(string password)
    {
        using (SHA256 sha256 = SHA256.Create())
        {
            byte[] hashedBytes = sha256.ComputeHash(Encoding.UTF8.GetBytes(password));
            return Convert.ToBase64String(hashedBytes);
        }
    }

    // 🔑 VERIFY PASSWORD
    private bool VerifyPassword(string enteredPassword, string storedHash)
    {
        return HashPassword(enteredPassword) == storedHash;
    }
}

// 📌 DATA MODELS
public class RegisterRequest
{
    public string Username { get; set; }
    public string Password { get; set; }
    public string Role { get; set; } // "Admin" or "User"
}

public class LoginRequest
{
    public string Username { get; set; }
    public string Password { get; set; }
}

public class User
{
    public string PasswordHash { get; set; }
    public string Role { get; set; }
}
```

### Update Program.cs to Support Authentication

Modify Program.cs to ensure JWT role-based authentication works correctly.

```
var builder = WebApplication.CreateBuilder(args);

var secretKey = "YourSuperSecretKeyHere"; // 🔑 Store securely
string storagePath = @"C:\FileStorage";
string connectionString = "Server=YOUR_SERVER;Database=YOUR_DB;User Id=YOUR_USER;Password=YOUR_PASSWORD;";

// Register services
builder.Services.AddSingleton(new FileManagerService(storagePath, connectionString, secretKey));

builder.Services.AddAuthentication(JwtBearerDefaults.AuthenticationScheme)
    .AddJwtBearer(options =>
    {
        options.RequireHttpsMetadata = false;
        options.SaveToken = true;
        options.TokenValidationParameters = new Microsoft.IdentityModel.Tokens.TokenValidationParameters
        {
            ValidateIssuerSigningKey = true,
            IssuerSigningKey = new SymmetricSecurityKey(Encoding.UTF8.GetBytes(secretKey)),
            ValidateIssuer = false,
            ValidateAudience = false,
            RoleClaimType = ClaimTypes.Role // Ensure role claims are recognized
        };
    });

builder.Services.AddAuthorization(options =>
{
    options.AddPolicy("AdminOnly", policy => policy.RequireRole("Admin"));
    options.AddPolicy("UserOrAdmin", policy => policy.RequireRole("User", "Admin"));
});

var app = builder.Build();
app.UseAuthentication();
app.UseAuthorization();
app.MapControllers();
app.Run();
```

## Test the Implementation

### 🛠️ Register a New User

Register an Admin User

```
{
  "username": "admin1",
  "password": "securepassword",
  "role": "Admin"
}
```

Register a Regular User

```
{
  "username": "user1",
  "password": "securepassword",
  "role": "User"
}
```

### Login to Get JWT Token

Use the registered credentials in POST /api/auth/login to receive a JWT token.

### Restrict API Endpoints by Role

Update your FileController to use role-based policies:

```
[Authorize] // Require authentication for all endpoints
[Route("api/files")]
[ApiController]
public class FileController : ControllerBase
{
    private readonly FileManagerService _fileManagerService;

    public FileController(FileManagerService fileManagerService)
    {
        _fileManagerService = fileManagerService;
    }

    [Authorize(Policy = "AdminOnly")] // Only Admins can upload files
    [HttpPost("upload")]
    public async Task<IActionResult> UploadFile([FromForm] IFormFile file)
    {
        if (file == null || file.Length == 0)
            return BadRequest("Invalid file.");

        Guid fileId = await _fileManagerService.SaveFileAsync(file);
        return Ok(new { FileId = fileId });
    }

    [Authorize(Policy = "UserOrAdmin")] // Both Users and Admins can download files
    [HttpGet("download/{fileId}")]
    public async Task<IActionResult> DownloadFile(Guid fileId)
    {
        var (originalFileName, fileBytes) = await _fileManagerService.GetFileAsync(fileId);

        if (fileBytes == null)
            return NotFound("File not found.");

        return File(fileBytes, "application/octet-stream", originalFileName);
    }

    [Authorize(Policy = "AdminOnly")] // Only Admins can delete files
    [HttpDelete("delete/{fileId}")]
    public async Task<IActionResult> DeleteFile(Guid fileId)
    {
        bool deleted = await _fileManagerService.DeleteFileAsync(fileId);
        if (!deleted)
            return NotFound("File not found.");

        return Ok("File deleted successfully.");
    }
}
```

## 📌 Summary
* ✅ Users Can Register & Choose a Role 🎭
* ✅ Admins Can Upload & Delete Files 🔒
* ✅ Regular Users Can Only Download 📥
* ✅ JWT Tokens Now Include Role-Based Authorization 🔑
