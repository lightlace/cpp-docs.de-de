---
title: "Anwendungsdom&#228;nen und Visual&#160;C++"
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
  - "/clr-Compileroption [C++], Anwendungsdomänen"
  - "Anwendungsdomänen [C++], C++"
  - "Interop [C++], Anwendungsdomänen"
  - "Interoperabilität [C++], Anwendungsdomänen"
  - "Gemischte Assemblys [C++], Anwendungsdomänen"
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Anwendungsdom&#228;nen und Visual&#160;C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie über eine virtuelle `__clrcall`\-Funktion verfügen, ist vtable auf die Anwendungsdomäne \(appdomain\) bezogen.  Wenn Sie ein Objekt in einer appdomain erstellen, können Sie die virtuelle Funktion nur innerhalb dieser appdomain aufrufen.  Alle in **\/clr:pure**\-Kompiliereinheiten definierten Funktionen verwenden die `__clrcall`\-Aufrufkonvention.  Deshalb sind alle in **\/clr:pure**\-Kompiliereinheiten definierten vtables auf die jeweilige appdomain bezogen.  Im gemischten Modus \(**\/clr**\) gibt es auch prozessbezogene vtables, falls der Typ nicht über virtuelle `__clrcall`\-Funktionen verfügt.  
  
 Weitere Informationen finden Sie unter  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [\_\_clrcall](../cpp/clrcall.md)  
  
-   [Gewusst wie: Migrieren auf \/clr:pure](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [Prozess](../cpp/process.md)  
  
## Siehe auch  
 [Gemischte \(systemeigene und verwaltete\) Assemblys](../dotnet/mixed-native-and-managed-assemblies.md)