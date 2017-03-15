---
title: "Gewusst wie: Ermitteln des interaktiven Zustands (C++/CLI)"
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
  - "Interaktiver Benutzerzustand"
  - "Visual C++, Interaktiver Benutzerzustand"
ms.assetid: 9f52323e-38b8-4a41-9b1d-052012ad839b
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Ermitteln des interaktiven Zustands (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird veranschaulicht, wie ermittelt werden kann, ob Code in einem interaktiven Kontext ausgeführt wird.  Wenn <xref:System.Environment.UserInteractive*> false ist, wird der Code als Dienstprozess oder in einer Webanwendung ausgeführt. In diesem Fall sollten Sie nicht mit dem Benutzer interagieren.  
  
## Beispiel  
  
```  
// user_interactive.cpp  
// compile with: /clr  
using namespace System;  
  
int main()   
{  
   if ( Environment::UserInteractive )  
      Console::WriteLine("User interactive");  
   else  
      Console::WriteLine("Noninteractive");  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)