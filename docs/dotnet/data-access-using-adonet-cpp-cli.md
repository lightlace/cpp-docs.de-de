---
title: "Datenzugriff mit ADO.NET (C++/CLI)"
ms.custom: na
ms.date: "12/14/2016"
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
  - ".NET Framework [C++], Datenzugriff"
  - "ADO.NET [C++]"
  - "Daten [C++], ADO.NET"
  - "Datenzugriff [C++], ADO.NET"
  - "Datenbanken [C++], Zugreifen über C++"
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
caps.latest.revision: 12
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Datenzugriff mit ADO.NET (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ADO.NET ist die .NET Framework\-API für Datenzugriff, deren Leistungsfähigkeit und Benutzerfreundlichkeit von früheren Datenzugriffslösungen nicht erreicht wurde.  Dieser Abschnitt beschreibt einige mit ADO.NET verbundene Probleme, die ausschließlich Visual C\+\+\-Benutzer betreffen, wie das Marshallen systemeigener Typen.  
  
 ADO.NET wird unter der Common Language Runtime \(CLR\) ausgeführt.  Deshalb muss jede Anwendung, die mit ADO.NET interagiert, auch auf die CLR abzielen.  Allerdings bedeutet das nicht, dass systemeigene Anwendungen ADO.NET nicht verwenden können.  Diese Beispiele zeigen, wie systemeigener Code mit einer ADO.NET\-Datenbank interagieren kann.  
  
## In diesem Abschnitt  
 [Gewusst wie: Marshallen von ANSI\-Zeichenfolgen für ADO.NET](../dotnet/how-to-marshal-ansi-strings-for-adonet-cpp-cli.md)  
  
 [Gewusst wie: Marshallen von BSTR\-Zeichenfolgen für ADO.NET](../dotnet/how-to-marshal-bstr-strings-for-adonet-cpp-cli.md)  
  
 [Gewusst wie: Marshallen von Unicode\-Zeichenfolgen für ADO.NET](../dotnet/how-to-marshal-unicode-strings-for-adonet-cpp-cli.md)  
  
 [Gewusst wie: Marshallen eines VARIANT für ADO.NET](../dotnet/how-to-marshal-a-variant-for-adonet-cpp-cli.md)  
  
 [Gewusst wie: Marshallen eines SAFEARRAY für ADO.NET](../dotnet/how-to-marshal-a-safearray-for-adonet-cpp-cli.md)  
  
## Verwandte Abschnitte  
  
|Abschnitt|**Beschreibung**|  
|---------------|----------------------|  
|[ADO.NET](../Topic/ADO.NET.md)|Enthält eine Übersicht über ADO.NET und einen Satz von Klassen, die Datenzugriffsdienste für .NET\-Programmierer verfügbar machen.|  
|[Creating SQL Server 2005 Objects In Managed Code](assetId:///5358a825-e19b-49aa-8214-674ce5fed1da)|Beschreibt die Verwendung von .NET\-Sprachen wie Visual C\+\+, um Datenbankobjekte zu erstellen, z. B. gespeicherte Prozeduren, Aggregate, Trigger, benutzerdefinierte Funktionen und benutzerdefinierte Typen, und um Daten für Microsoft SQL Server 2005\-Datenbanken abzurufen und zu aktualisieren.|  
  
## Siehe auch  
 [.NET\-Programmierung mit C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interoperabilität von systemeigenem Code und .NET](../dotnet/native-and-dotnet-interoperability.md)