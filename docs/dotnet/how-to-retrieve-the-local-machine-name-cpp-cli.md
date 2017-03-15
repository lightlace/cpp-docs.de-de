---
title: "Gewusst wie: Abrufen des lokalen Computernamens (C++/CLI)"
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
  - "Computername"
  - "Computername, Abrufen"
  - "Computername, Abrufen"
ms.assetid: 6c7acb9a-3f9b-43b2-a756-bd4fb859e697
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Abrufen des lokalen Computernamens (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das folgende Codebeispiel veranschaulicht das Abrufen des lokalen Computernamens \(der Name des Computers, der im Netzwerk angezeigt wird\).  Dies erreichen Sie durch Abrufen der <xref:System.Environment.MachineName*>\-Zeichenfolge, die im <xref:System.Environment>\-Namespace definiert wird.  
  
## Beispiel  
  
```  
// machine_name.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   Console::WriteLine("\nMachineName: {0}", Environment::MachineName);  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)