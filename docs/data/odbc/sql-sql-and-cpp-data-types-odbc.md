---
title: 'SQL: SQL- und C++-Datentypen (ODBC) | Microsoft-Dokumentation'
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
ms.openlocfilehash: 8b978356cead1f9b74ce59e58ab0191f5e00105b
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340767"
---
# <a name="sql-sql-and-c-data-types-odbc"></a>SQL: SQL- und C++-Datentypen (ODBC)
> [!NOTE]
>  Diese Informationen gelten für die MFC-ODBC-Klassen. Wenn Sie mit den MFC-DAO-Klassen arbeiten, finden Sie im "Vergleich von Microsoft Jet-Datenbank-Engine-SQL und ANSI-SQL" in-DAO-Hilfe.  
  
 In der folgende Tabelle werden ANSI SQL-Datentypen in C++-Datentypen zugeordnet. Diese Tabelle die C-Language-Informationen erhalten in Anhang D des ergänzt die *ODBC SDK* *Programmer's Reference* auf der MSDN Library-CD. Die Assistenten verwalten die meisten datentypzuordnung für Sie. Wenn Sie einen Assistenten nicht verwenden, können Sie die Zuordnungsinformationen zu, damit Sie den Code manuell schreiben können.  
  
### <a name="ansi-sql-data-types-mapped-to-c-data-types"></a>ANSI SQL-Datentypen, die C++-Datentypen zugeordnet  
  
|ANSI-SQL-Datentyp|C++-Datentyp|  
|------------------------|---------------------|  
|**CHAR**|`CString`|  
|**DECIMAL**|`CString` 1|  
|**SMALLINT**|**int**|  
|**REAL**|**float**|  
|**GANZE ZAHL**|**long**|  
|**FLOAT**|**double**|  
|**DOUBLE**|**double**|  
|**NUMERIC**|`CString` 1|  
|**VARCHAR**|`CString`|  
|**LONGVARCHAR**|`CLongBinary`, `CString` 2|  
|**BIT**|**BOOL**|  
|**TINYINT**|**BYTE**|  
|**BIGINT**|`CString` 1|  
|**BINÄRE**|`CByteArray`|  
|**VARBINARY**|`CByteArray`|  
|**LONGVARBINARY**|`CLongBinary`, `CByteArray` 3|  
|**DATE**|`CTime`, `CString`|  
|**ZEIT**|`CTime`, `CString`|  
|**TIMESTAMP**|`CTime`, `CString`|  
  
 1. ANSI **DECIMAL** und **numerischen** zuordnen `CString` da **SQL_C_CHAR** ist der Standardtyp für ODBC-Übertragung.  
  
 2. Zeichendaten, die länger als 255 Zeichen abgeschnitten, indem bei-Zuordnung standardmäßig `CString`. Sie können diese Länge erweitern, indem Sie explizit die *nMaxLength* Argument `RFX_Text`.  
  
 3. Binäre Daten länger als 255 Zeichen abgeschnitten, indem bei-Zuordnung standardmäßig `CByteArray`. Sie können diese Länge erweitern, indem Sie explizit die *nMaxLength* Argument `RFX_Binary`.  
  
 Wenn Sie nicht die ODBC-Cursorbibliothek verwenden, können ein Problem beim Versuch, aktualisieren Sie zwei oder mehr Felder für lange variabler Länge mit der Microsoft SQL Server-ODBC-Treiber und die MFC-ODBC-Datenbankklassen auftreten. Der ODBC-Datentypen, **SQL_LONGVARCHAR** und **SQL_LONGVARBINARY**, ordnen Sie Text und image von SQLServer-Typen. Ein `CDBException` wird ausgelöst, wenn Sie zwei oder mehr lange variabler Länge, die Felder auf den gleichen Aufruf aktualisieren `CRecordset::Update`. Aktualisieren Sie daher nicht mehrere lange Spalten gleichzeitig mit `CRecordset::Update`. Sie können mehrere lange Spalten gleichzeitig mit der ODBC-API aktualisieren `SQLPutData`. Sie können auch die ODBC-Cursorbibliothek verwenden, aber dies wird nicht empfohlen, für die Treiber, z. B. den SQL Server-Treiber, die Cursor unterstützen und die Cursorbibliothek ist nicht erforderlich.  
  
 Bei Verwendung der ODBC-Cursorbibliothek mit dem MFC-ODBC-Datenbankklassen und Microsoft SQL Server-ODBC-Treiber eine **ASSERT** auftreten, zusammen mit einem `CDBException` Wenn ein Aufruf von `CRecordset::Update` folgt einen Aufruf zum `CRecordset::Requery`. Rufen Sie stattdessen `CRecordset::Close` und `CRecordset::Open` statt `CRecordset::Requery`. Eine andere Lösung ist nicht für die ODBC-Cursorbibliothek verwenden, da es sich bei der SQL Server und der SQL Server-ODBC-Treiber systemeigene Unterstützung für Cursor systemeigen bieten und die ODBC-Cursorbibliothek ist nicht erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [SQL](../../data/odbc/sql.md)   
 [SQL: Durchführen direkter SQL-Aufrufe (ODBC)](../../data/odbc/sql-making-direct-sql-calls-odbc.md)