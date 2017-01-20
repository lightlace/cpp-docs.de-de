---
title: "SQL: SQL- und C++-Datentypen (ODBC)"
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
  - "Datentypen [C++], SQL im Vergleich zu C++"
  - "SQL [C++], Im Vergleich zu C#-Datentypen"
  - "SQL-Datentypen [C++]"
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# SQL: SQL- und C++-Datentypen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Diese Informationen beziehen sich auf die MFC\-ODBC\-Klassen.  Wenn Sie mit den MFC\-DAO\-Klassen arbeiten, lesen Sie in der DAO\-Hilfe das Thema "Vergleich von Microsoft Jet Database Engine\-SQL und ANSI\-SQL".  
  
 Die folgende Tabelle listet ANSI SQL\-Datentypen und die zugehörigen C\+\+\-Datentypen auf.  Diese Tabelle ergänzt die C\-bezogenen Informationen im Anhang D von *ODBC SDK* *Programmer's Reference* auf der MSDN Library\-CD.  Die Assistenten verwalten die meisten Datentypzuordnungen.  Falls Sie keinen Assistenten verwenden, können Sie mithilfe dieser Zuordnungsinformationen den Code für den Feldaustausch von Hand erstellen.  
  
### C\+\+\-Datentypen zugeordnete ANSI SQL\-Datentypen  
  
|ANSI SQL\-Datentyp|C\+\+\-Datentyp|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DEZIMAL**|`CString` 1|  
|**SMALLINT**|`int`|  
|`REAL`|**float**|  
|**INTEGER**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINARY**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**TIME**|**CTime, CString**|  
|**TIMESTAMP**|**CTime, CString**|  
  
 1.  Die ANSI\-Typen **DECIMAL** und **NUMERIC** werden `CString` zugeordnet, da **SQL\_C\_CHAR** der ODBC\-Standardübertragungstyp ist.  
  
 2.  Zeichendaten, die länger als 255 Zeichen sind, werden bei der `CString`\-Zuordnung standardmäßig abgeschnitten.  Sie können diese Länge erhöhen, indem Sie das Argument `nMaxLength` von `RFX_Text` explizit einstellen.  
  
 3.  Binäre Daten, die länger als 255 Zeichen sind, werden bei der `CByteArray`\-Zuordnung standardmäßig abgeschnitten.  Sie können diese Länge erhöhen, indem Sie das Argument `nMaxLength` von `RFX_Binary` explizit festlegen.  
  
 Falls Sie die ODBC\-Cursorbibliothek nicht verwenden, ergeben sich möglicherweise Probleme bei dem Versuch, zwei oder mehr lange Felder variabler Länge zu aktualisieren, wenn Sie hierzu den Microsoft SQL Server\-ODBC\-Treiber und die MFC\-ODBC\-Datenbankklassen verwenden.  Die ODBC\-Typen **SQL\_LONGVARCHAR** und **SQL\_LONGVARBINARY** werden den SQL Server\-Typen "text" und "image" zugeordnet.  Wenn Sie zwei oder mehr lange Felder variabler Länge bei demselben Aufruf von `CRecordset::Update` aktualisieren, wird eine `CDBException` ausgelöst.  Daher dürfen mehrere lange Spalten nicht gleichzeitig mit `CRecordset::Update` aktualisiert werden.  Sie können mehrere lange Spalten gleichzeitig mit der ODBC\-API\-Funktion **SQLPutData** aktualisieren.  Sie können auch die ODBC\-Cursorbibliothek verwenden, deren Verwendung für Treiber wie dem SQL Server\-Treiber jedoch nicht empfehlenswert ist, da solche Treiber Cursor unterstützen und die Cursorbibliothek nicht benötigen.  
  
 Wenn Sie die ODBC\-Cursorbibliothek mit den MFC\-ODBC\-Datenbankklassen und dem Microsoft SQL Server\-ODBC\-Treiber verwenden, kann **ASSERT** zusammen mit `CDBException` ausgelöst werden, falls ein Aufruf für `CRecordset::Update` einem Aufruf für `CRecordset::Requery` folgt.  Rufen Sie daher an Stelle von `CRecordset::Requery` erst `CRecordset::Close` und dann `CRecordset::Open` auf.  Eine weitere Lösungsmöglichkeit besteht darin, die ODBC\-Cursorbibliothek nicht zu verwenden, da SQL Server und der SQL Server\-ODBC\-Treiber Cursor standardmäßig unterstützen und die ODBC\-Cursorbibliothek daher nicht benötigt wird.  
  
## Siehe auch  
 [SQL](../../data/odbc/sql.md)   
 [SQL: Durchführen direkter SQL\-Aufrufe \(ODBC\)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)