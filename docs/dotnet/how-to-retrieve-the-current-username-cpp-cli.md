---
title: "Gewusst wie: Abrufen des aktuellen Benutzernamens (C++/CLI)"
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
  - "Aktuelle Benutzernamen"
  - "Benutzernamen, Abrufen"
  - "UserName-Zeichenfolge"
ms.assetid: 91679571-d029-41f5-b657-1460c81c608a
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen des aktuellen Benutzernamens (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das folgende Codebeispiel veranschaulicht, wie der aktuelle Benutzername \(der bei Windows angemeldete Benutzername\) abgerufen werden kann.  Der Name ist in der <xref:System.Environment.UserName*>\-Zeichenfolge gespeichert, die im <xref:System.Environment>\-Namespace definiert ist.  
  
## Beispiel  
  
```  
// username.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nCurrent user: {0}", Environment::UserName);  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)