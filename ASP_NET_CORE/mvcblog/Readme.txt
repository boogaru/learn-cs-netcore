0. add entity vào project
dotnet add package System.Data.SqlClient
dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Microsoft.EntityFrameworkCore.SqlServer
dotnet add package Microsoft.EntityFrameworkCore.Design
dotnet add package Microsoft.Extensions.DependencyInjection
dotnet add package Microsoft.Extensions.Logging.Console

dotnet add package Microsoft.AspNetCore.Identity
dotnet add package Microsoft.AspNetCore.Identity.EntityFrameworkCore
dotnet add package Microsoft.VisualStudio.Web.CodeGeneration.Design
dotnet add package Microsoft.AspNetCore.Identity.UI
dotnet add package Microsoft.AspNetCore.Authentication
dotnet add package Microsoft.AspNetCore.Abstractions
dotnet add package Microsoft.AspNetCore.Cookies
dotnet add package Microsoft.AspNetCore.Facebook

1. Tạo một Migration đặt tên là AddCategory
-> dotnet ef migrations add AddCategory

2. Cập nhật database
-> dotnet ef database update AddCategory

3. Xóa migration cuối 
-> dotnet ef migrations remove

4. Tạo CRUD cho category
-> dotnet aspnet-codegenerator controller -name CategoryController -m mvcblog.Models.Category -dc mvcblog.Data.AppDbContext -outDir  Areas/Admin/Controllers -l _Layout
Với:

-name Category tạo controller đặt tên là Category
-m mvcblog.Models.Category chỉ ra lớp Model sẽ phát sinh CRUD
-dc mvcblog.Data.AppDbContext chỉ ra lớp DbContext
-outDir Areas/Admin/Controllers nơi lưu code Controller (đặt trong Area có tên Blog)
-l _Layout view phát sinh sử dụng layout là _Layout