---
title: "Gewusst wie: Abrufen der Windows-Version (C++/CLI)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Windows [C++], Abrufen der Version mit Visual C++"
  - "Windows [C++], Version"
ms.assetid: 7e6f567b-d378-49bb-aa59-2240f69a022d
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen der Windows-Version (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird dargestellt, wie Informationen zur Plattform und Version des aktuellen Betriebssystems abgerufen werden.  Diese Informationen werden in der <xref:System.Environment.OSVersion*?displayProperty=fullName>\-Eigenschaft gespeichert und bestehen aus einer Auflistung, in der grundlegende Informationen zur Windows\-Version enthalten sind, und einem <xref:System.Environment.Version*>\-Objekt, das den genauen Build des Betriebssystems enthält.  
  
## Beispiel  
  
```  
// os_ver.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   OperatingSystem^ osv = Environment::OSVersion;  
   PlatformID id = osv->Platform;  
   Console::Write("Operating system: ");  
  
   if (id == PlatformID::Win32NT)  
      Console::WriteLine("Win32NT");  
   else if (id == PlatformID::Win32S)  
      Console::WriteLine("Win32S");  
   else if (id == PlatformID::Win32Windows)  
      Console::WriteLine("Win32Windows");  
   else  
      Console::WriteLine("WinCE");  
  
   Version^ version = osv->Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write("OS Version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
                   build, major, minor, revision);  
   }  
  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)