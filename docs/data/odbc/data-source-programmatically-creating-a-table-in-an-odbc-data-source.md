---
title: "Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Datenquellen, Erstellen von Tabellen"
  - "Programmgesteuertes Erstellen von ODBC-Tabellen [C++]"
  - "Tabellen [C++]"
  - "Tabellen [C++], Programmgesteuertes Erstellen"
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird erläutert, wie eine Tabelle für die Datenquelle erstellt wird, indem die `ExecuteSQL`\-Memberfunktion der `CDatabase`\-Klasse aufgerufen und ihr eine Zeichenfolge übergeben wird, die eine **CREATE TABLE**\-SQL\-Anweisung enthält.  
  
 Allgemeine Informationen über ODBC\-Datenquellen in MFC finden Sie unter [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md).  Im Thema [Datenquelle: Programmgesteuertes Konfigurieren einer ODBC\-Datenquelle](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) wird die Erstellung von Datenquellen beschrieben.  
  
 Wenn die Datenquelle eingerichtet wurde, können Tabellen einfach mit der `ExecuteSQL`\-Memberfunktion und der **CREATE TABLE**\-SQL\-Anweisung erstellt werden.  Bei einem `CDatabase`\-Objekt mit der Bezeichnung `myDB` könnte zur Tabellenerstellung z. B. der folgende MFC\-Code verwendet werden:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 Mit diesem Beispielcode wird in der von `myDB` verwalteten Microsoft Access\-Datenquellenverbindung eine Tabelle mit der Bezeichnung "OFFICES" erstellt. Diese Tabelle enthält die beiden Felder "OfficeID" und "OfficeName".  
  
> [!NOTE]
>  Die in der **CREATE TABLE**\-SQL\-Anweisung angegebenen Feldtypen können je nach verwendetem ODBC\-Treiber variieren.  Mit dem Programm Microsoft Query, das zusammen mit Visual C\+\+, Version 1.5, erhältlich ist, kann festgestellt werden, welche Feldtypen für eine Datenquelle verfügbar sind.  Klicken Sie in Microsoft Query im Menü **Datei** auf **Table\_Definition**, wählen Sie in einer Datenquelle eine Tabelle aus, und überprüfen Sie, welcher Typ im Kombinationsfeld **Typ** angezeigt wird.  Es wird auch eine SQL\-Syntax zur Erstellung von Indizes unterstützt.  
  
## Siehe auch  
 [Datenquelle \(ODBC\)](../../data/odbc/data-source-odbc.md)