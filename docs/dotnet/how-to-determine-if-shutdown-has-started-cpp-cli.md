---
title: "Gewusst wie: Ermitteln, ob das Herunterfahren begonnen hat (C++/CLI)"
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
  - ".NET Framework, Herunterfahren"
  - "Anwendungen [C++], Herunterfahren"
  - "Herunterfahren"
  - "Terminierung"
ms.assetid: a8d39731-dea8-4f0a-96b7-2a5de09b21d7
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Gewusst wie: Ermitteln, ob das Herunterfahren begonnen hat (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Im folgenden Codebeispiel wird dargestellt, wie festgestellt werden kann, ob die Anwendung oder .NET Framework gerade beendet wird.  Dies ist für den Zugriff auf statische Elemente im .NET Framework sinnvoll, da diese Konstrukte beim Herunterfahren durch das System beendet werden und nicht verlässlich genutzt werden können.  Sie können potenzielle Fehler vermeiden, indem Sie zuerst die <xref:System.Environment.HasShutdownStarted*>\-Eigenschaft überprüfen und ggf. nicht auf diese Elemente zugreifen.  
  
## Beispiel  
  
```  
// check_shutdown.cpp  
// compile with: /clr  
using namespace System;  
int main()   
{  
   if (Environment::HasShutdownStarted)  
      Console::WriteLine("Shutting down.");  
   else  
      Console::WriteLine("Not shutting down.");  
   return 0;  
}  
```  
  
## Siehe auch  
 [Windows\-Vorgänge](../dotnet/windows-operations-cpp-cli.md)   
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)