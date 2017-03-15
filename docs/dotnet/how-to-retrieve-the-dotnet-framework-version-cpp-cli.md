---
title: "Gewusst wie: Abrufen der .NET Framework-Version (C++/CLI)"
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
  - ".NET Framework, Version"
  - "Version-Eigenschaft, Abrufen der .NET Framework-Version"
ms.assetid: fc786fbc-c915-4b15-bcad-0d68cf2c44bd
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen der .NET Framework-Version (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird gezeigt, wie die Version des aktuell installierten .NET Framework mit der Eigenschaft <xref:System.Environment.Version*> ermittelt werden kann. Dabei handelt es sich um einen Zeiger auf ein <xref:System.Version>\-Objekt, das die Versionsinformationen enthält.  
  
## Beispiel  
  
```  
// dotnet_ver.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   Version^ version = Environment::Version;  
   if (version)  
   {  
      int build = version->Build;  
      int major = version->Major;  
      int minor = version->Minor;  
      int revision = Environment::Version->Revision;  
      Console::Write(".NET Framework version: ");  
      Console::WriteLine("{0}.{1}.{2}.{3}",   
            build, major, minor, revision);  
   }  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)