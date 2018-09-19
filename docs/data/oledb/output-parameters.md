---
title: Ausgabeparameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB, stored procedures
- stored procedures, calling
- stored procedures, parameters
- procedure calls
- procedure calls, stored procedures
ms.assetid: 4f7c2700-1c2d-42f3-8c9f-7e83962b2442
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5f9e0e273df1221801a9b761cd7f45200e0b50c0
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895083"
---
# <a name="output-parameters"></a>Ausgabeparameter

Aufrufen einer gespeicherten Prozedur entspricht einen SQL-Befehl aufrufen. Der Hauptunterschied besteht darin, dass gespeicherte Prozeduren verwenden von Output-Parameter (oder "Outparameters"), und geben Werte zurück.

In der folgenden gespeicherten Prozedur, der ersten "?"ist der Rückgabewert (Phone) und das zweite"?" ist der Eingabeparameter (Name):

```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  

Sie werden die Eingabe- und Ausgabeparameter in der parameterzuordnung angeben:

```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter
END_PARAM_MAP()  
```  

Die Anwendung muss die Ausgabe von gespeicherten Prozeduren zurückgegebenen behandeln. Verschiedene OLE DB-Anbieter zurückgeben der Output-Parameter und Rückgabewerte zu unterschiedlichen Zeitpunkten während der ergebnisverarbeitung. Z. B. der Microsoft OLE DB-Anbieter für SQL Server (SQLOLEDB) nicht Ausgabeparameter und Rückgabecodes erst, nachdem der Consumer abgerufen oder die von der gespeicherten Prozedur zurückgegebenen Resultsets abgebrochen hat. Die Ausgabe wird im letzten TDS-Paket vom Server zurückgegeben.

## <a name="row-count"></a>Zeilenanzahl

Wenn Sie die OLE DB-Consumervorlagen verwenden, um eine gespeicherte Prozedur ausführen, die mit Ausgabeparametern, ist die Anzahl der Zeilen nicht festgelegt werden, bis zum Schließen des Rowsets.

Betrachten Sie beispielsweise eine gespeicherte Prozedur mit einer Zeilengruppe und einem Ausgabeparameter aus:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```  

Die \@_rowcount Ausgabeparameter meldet, wie viele Zeilen aus der Tabelle "Test" tatsächlich zurückgegeben wurden. Diese gespeicherte Prozedur beschränkt jedoch die Anzahl der Zeilen auf maximal 50. Beispielsweise würde es 100 Zeilen im Test, würde die Zeilenanzahl 50 lauten (da dieser Code nur die ersten 50 Zeilen werden abgerufen). Wenn nur 30 Zeilen in der Tabelle vorhanden waren, wäre die Zeilenanzahl 30. Rufen Sie `Close` oder `CloseAll` um den Ausgabeparameter aufzufüllen, bevor Sie diesen Wert abrufen.

## <a name="see-also"></a>Siehe auch

[Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)