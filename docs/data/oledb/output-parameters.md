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
ms.openlocfilehash: 4a17ff7e6e78b21267b71ba495ba10a98e29cfe7
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808849"
---
# <a name="output-parameters"></a>Ausgabeparameter

Aufrufen einer gespeicherten Prozedur ist ähnlich wie beim Ausführen eines SQL-Befehls. Der Hauptunterschied besteht darin, dass gespeicherte Prozeduren verwenden von Output-Parameter (oder "Outparameters"), und geben Werte zurück.

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

Die Anwendung muss die Ausgabe von gespeicherten Prozeduren zurückgegebenen behandeln. Verschiedene OLE DB-Anbieter zurückgeben der Output-Parameter und Rückgabewerte zu unterschiedlichen Zeitpunkten während der ergebnisverarbeitung. Der Microsoft OLE DB-Anbieter für SQL Server (SQLOLEDB) nicht, z. B. Ausgabeparameter und Rückgabecodes erst, nachdem der Consumer abgerufen oder die von der gespeicherten Prozedur zurückgegebenen Resultsets abgebrochen hat. Die Ausgabe wird im letzten TDS-Paket vom Server zurückgegeben.

## <a name="row-count"></a>Zeilenanzahl

Wenn Sie die OLE DB-Consumervorlagen verwenden, um eine gespeicherte Prozedur ausführen, die mit Ausgabeparametern, nicht die Anzahl der Zeilen festgelegt, bis Sie das Rowset schließen.

Betrachten Sie beispielsweise eine gespeicherte Prozedur mit einer Zeilengruppe und einem Ausgabeparameter aus:

```sql
create procedure sp_test
   @_rowcount integer output
as
   select top 50 * from test
   @_rowcount = @@rowcount
return 0
```  

Die \@_rowcount Ausgabeparameter meldet, wie viele Zeilen aus der Tabelle "Test" zurückgegeben wurden. Diese gespeicherte Prozedur wird jedoch die Anzahl der Zeilen auf 50 beschränkt. Beispielsweise würde es 100 Zeilen im Test, würde die Zeilenanzahl 50 lauten (da dieser Code nur die ersten 50 Zeilen werden abgerufen). Wenn nur 30 Zeilen in der Tabelle vorhanden waren, wäre die Zeilenanzahl 30. Achten Sie darauf, dass Sie zum Aufrufen `Close` oder `CloseAll` um den Ausgabeparameter aufzufüllen, bevor Sie diesen Wert abrufen.

## <a name="see-also"></a>Siehe auch

[Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)