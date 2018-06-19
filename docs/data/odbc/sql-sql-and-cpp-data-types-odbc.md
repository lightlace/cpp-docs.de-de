---
title: 'SQL: SQL- und C++-Datentypen (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], SQL vs. C++
- SQL data types [C++]
- SQL [C++], vs. C++ data types
ms.assetid: 066e0070-d4da-435c-9c4b-f7cab3352c86
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6a137c4f648f518420d06f5cbd98ea189a030aee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33095407"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL- und C++-Datentypen (ODBC)
> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im Thema "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" DAO-Hilfe.  
  
 Die folgende Tabelle ordnet die ANSI SQL-Datentypen in C++-Datentypen. Diese Tabelle die C-bezogenen Informationen im Anhang D ergänzt die *ODBC SDK* *Programmer's Reference* auf der MSDN Library-CD. Die Assistenten verwalten die meisten datentypzuordnung für Sie. Wenn Sie einen Assistenten nicht verwenden, können Sie die Zuordnungsinformationen zu verwenden, können Sie den Code manuell geschrieben.  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>ANSI SQL-Datentypen zugeordnet werden, um C++-Datentypen  
  
|ANSI SQL-Datentyp|C++-Datentyp|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**"SMALLINT"**|`int`|  
|`REAL`|**float**|  
|**GANZE ZAHL**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**"TINYINT"**|**BYTE**|  
|**"BIGINT"**|`CString` 1|  
|**BINÄRE**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**"LONGVARBINARY"**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**ZEIT**|**CTime, CString**|  
|**TIMESTAMP**|**CTime, CString**|  
  
 1. ANSI **DECIMAL** und **numerischen** zuordnen `CString` da **SQL_C_CHAR** der ODBC-Standardübertragungstyp ist.  
  
 2. Zeichendaten länger als 255 Zeichen abgeschnitten, wenn zugeordnet, wird standardmäßig `CString`. Sie können diese Länge erweitern, indem Sie das explizite Festlegen der `nMaxLength` Argument `RFX_Text`.  
  
 3. Binäre Daten, die länger als 255 Zeichen abgeschnitten, indem bei-Zuordnung standardmäßig `CByteArray`. Sie können diese Länge erweitern, indem Sie das explizite Festlegen der `nMaxLength` Argument `RFX_Binary`.  
  
 Wenn Sie die ODBC-Cursorbibliothek nicht verwenden, können ein Problem beim Versuch, aktualisieren Sie zwei oder mehr lange variabler Länge-Felder, die mit der Microsoft SQL Server-ODBC-Treiber und den MFC-ODBC-Datenbankklassen auftreten. Der ODBC-Datentypen **SQL_LONGVARCHAR** und **SQL_LONGVARBINARY**, Zuordnen von Text und image von SQLServer-Typen. Ein `CDBException` wird ausgelöst, wenn Sie zwei oder mehr lange variabler Länge, die Felder auf den gleichen Aufruf zum Aktualisieren `CRecordset::Update`. Aktualisieren Sie deshalb nicht mehrere lange Spalten gleichzeitig mit `CRecordset::Update`. Sie können mehrere lange Spalten gleichzeitig mit der ODBC-API aktualisieren **SQLPutData**. Sie können auch die ODBC-Cursorbibliothek verwenden, aber dies wird nicht empfohlen, für die Treiber, wie z. B. die SQL Server-Treiber, die Cursor unterstützen und die Cursorbibliothek ist nicht erforderlich.  
  
 Bei Verwendung der ODBC-Cursorbibliothek mit den MFC-ODBC-Datenbankklassen und dem Microsoft SQL Server ODBC-Treiber eine **ASSERT** auftreten, zusammen mit einem `CDBException` Wenn ein Aufruf von `CRecordset::Update` folgt einen Aufruf von `CRecordset::Requery`. Rufen Sie stattdessen `CRecordset::Close` und `CRecordset::Open` statt `CRecordset::Requery`. Eine andere Lösung besteht nicht die ODBC-Cursorbibliothek verwenden, da SQL Server und der SQL Server-ODBC-Treiber systemeigene Unterstützung für Cursor systemintern bieten und die ODBC-Cursorbibliothek ist nicht erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL](../../data/odbc/sql.md)   
 [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)