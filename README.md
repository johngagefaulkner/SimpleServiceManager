# SimpleServiceManager
The idea for SimpleSvcMgr came to me when I was building a Windows Service and I kept having to re-open services.msc to manually stop and start the service during debugging and compiling. I wanted a little tool that I could leave open to easily install, start, stop and uninstall any given service.

## Preview
![SSMui](https://i.imgur.com/AAZO0PM.png)

## Description
The source code here isn't at all impressive but this repository is really meant just to get the first one out of the way. 
If you're only here to download the .exe and be on your way, you can grab it **here** or from the Releases tab.

## Usage
If you're interesed in the source code, installing and uninstalling are handled by Windows' built-in "sc.exe" commands.
Here's an example with variables:
```csharp
 sc.exe create SERVICE NAME binpath= "SERVICE FULL PATH"
 Process p = new Process();
 p.StartInfo.UseShellExecute = false;
 p.StartInfo.RedirectStandardOutput = true;
 p.StartInfo.FileName = "YOURBATCHFILE.bat";
 p.Start();
 // Do not wait for the child process to exit before
 // reading to the end of its redirected stream.
 // p.WaitForExit();
 // Read the output stream first and then wait.
 string output = p.StandardOutput.ReadToEnd();
 p.WaitForExit();
 ```
