[![NuGet version (Micro-Manager.NET)](https://img.shields.io/nuget/v/Micro-Manager.NET.svg)](https://www.nuget.org/packages/Micro-Manager.NET/2.0.3)
[![NuGet version (Micro-Manager.NET)](https://img.shields.io/nuget/dt/Micro-Manager.NET?color=g)](https://www.nuget.org/packages/Micro-Manager.NET/2.0.3)
# Micro-Manager.NET
 Controlling Micro-Manager 2.0.3 with IKVM & C#

# Building 
- Get IKVM 8.9.0 or the [developer pre-release](https://github.com/ikvmnet/ikvm/actions/runs/9238355862/artifacts/1537937356).

- Then use Micro-Manager in C#
```
using org.micromanager.@internal;
using System;
namespace MMTest
{
    public partial class Form1 : Form
    {
        public Form1(string[] args)
        {
            InitializeComponent();
            Directory.SetCurrentDirectory("C:/Program Files/Micro-Manager-2.0/");
            java.lang.System.setProperty("force.annotation.index", "true");
            // Set the library path (adjust the path as needed)
            java.lang.System.setProperty("org.micromanager.corej.path", "C:/Program Files/Micro-Manager-2.0");
            try
            {
                MMStudio.main(args);
                MMStudio ms = MMStudio.getInstance();
            }
            catch (Exception e)
            {
            }
        }
    }
}
```
