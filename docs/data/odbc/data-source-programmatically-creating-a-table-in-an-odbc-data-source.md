---
title: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- programmatically creating ODBC tables [C++]
- tables [C++]
- ODBC data sources, creating tables in
- tables [C++], creating programmatically
ms.assetid: 9ca68fb5-c3df-424a-a75c-e3fb01cc1b18
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5ea8ddc8e683c0e5f0681bdf98cbddca180e4023
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="data-source-programmatically-creating-a-table-in-an-odbc-data-source"></a>Datenquelle: Programmgesteuertes Erstellen einer Tabelle in einer ODBC-Datenquelle
In diesem Thema wird erläutert, wie zum Erstellen einer Tabelle für Ihre Daten Datenquelle mithilfe der `ExecuteSQL` Memberfunktion der Klasse `CDatabase`, übergeben der Funktion eine Zeichenfolge, enthält eine **CREATE TABLE** SQL-Anweisung.  
  
 Allgemeine Informationen über ODBC-Datenquellen in MFC finden Sie unter [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md). Das Thema [Datenquelle: Programmgesteuertes Konfigurieren einer ODBC-Datenquelle](../../data/odbc/data-source-programmatically-configuring-an-odbc-data-source.md) wird die Erstellung von Datenquellen beschrieben.  
  
 Wenn Sie die Datenquelle eingerichtet haben, können problemlos Tabelleninhalts durch Erstellen der `ExecuteSQL` Memberfunktion und die **CREATE TABLE** SQL-Anweisung. Angenommen, Sie haben eine `CDatabase` bezeichnetes Objekt `myDB`, können Sie den folgenden MFC-Code zum Erstellen einer Tabelle:  
  
```  
myDB.ExecuteSQL("CREATE TABLE OFFICES (OfficeID TEXT(4)" ",   
                         OfficeName TEXT(10))");  
```  
  
 Dieses Codebeispiel erstellt eine Tabelle namens "BÜROS" in der Microsoft Access-datenquellenverbindung, die von verwalteten `myDB`; die Tabelle enthält zwei Felder "OfficeID" und "OfficeName."  
  
> [!NOTE]
>  Die Feldtypen, angegeben der **CREATE TABLE** SQL-Anweisung variieren entsprechend der ODBC-Treiber, die Sie verwenden. Das Microsoft Query-Programm (zusammen mit Visual C++, Version 1.5) ist eine Möglichkeit zum Ermitteln, welche Feldtypen für eine Datenquelle verfügbar sind. Klicken Sie im Microsoft-Query auf **Datei**, klicken Sie auf **Table_Definition**, wählen Sie eine Tabelle aus einer Datenquelle, und sehen Sie sich die Art, die der **Typ** Kombinationsfeld. SQL-Syntax ist auch zum Erstellen von Indizes vorhanden.  
  
## <a name="see-also"></a>Siehe auch  
 [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md)