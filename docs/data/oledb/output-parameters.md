---
title: Ausgabeparameter | Microsoft Docs
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
ms.openlocfilehash: 8733b967ddab7e6f68fcbee1c80e78500a679f96
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104385"
---
# <a name="output-parameters"></a>Ausgabeparameter
Aufrufen einer gespeicherten Prozedur ist ähnlich wie einen SQL-Befehl aufrufen. Der Hauptunterschied besteht darin, dass gespeicherte Prozeduren verwenden Sie Output-Parameter (oder "Outparameters") und Rückgabewerte.  
  
 In der folgenden gespeicherten Prozedur, die erste "?"ist der Rückgabewert (Phone) und die zweite"?" ist der Eingabeparameter (Name):  
  
```  
DEFINE_COMMAND(CMySProcAccessor, _T("{ ? = SELECT phone FROM shippers WHERE name = ? }")  
```  
  
 Die ein- und Ausgabeparameter werden in der Zuordnung Parameter angeben:  
  
```  
BEGIN_PARAM_MAP(CMySProcAccessor)  
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)  
   COLUMN_ENTRY(1, m_Phone)   // Phone is the return value  
   SET_PARAM_TYPE(DBPARAMIO_INPUT)  
   COLUMN_ENTRY(2, m_Name)   // Name is the input parameter  
END_PARAM_MAP()  
```  
  
 Die Anwendung muss die Ausgabe von gespeicherten Prozeduren behandeln. Verschiedene OLE DB-Anbieter zurückgeben Output-Parameter und Rückgabewerte zu unterschiedlichen Zeitpunkten während der ergebnisverarbeitung. Der Microsoft OLE DB-Anbieter für SQL Server (SQLOLEDB) beispielsweise nicht Ausgabeparameter und Rückgabecodes erst, nachdem der Consumer abgerufen oder die von der gespeicherten Prozedur zurückgegebenen Resultsets abgebrochen hat. Die Ausgabe wird im letzten TDS-Paket vom Server zurückgegeben.  
  
## <a name="row-count"></a>Zeilenanzahl  
 Wenn Sie die OLE DB-Consumervorlagen zum Ausführen einer gespeicherten Prozedur, die von Ausgabeparametern verwenden, wird die Zeilenanzahl erst beim Schließen des Rowsets nicht festgelegt.  
  
 Betrachten Sie beispielsweise eine gespeicherte Prozedur mit einem Rowset und einem Ausgabeparameter aus:  
  
```  
create procedure sp_test  
   @_rowcount integer output  
as  
   select top 50 * from test  
   @_rowcount = @@rowcount  
return 0  
```  
  
 Die @_rowcount Ausgabeparameter meldet, wie viele Zeilen aus der Tabelle "Test" zurückgegeben wurden. Diese gespeicherte Prozedur wird jedoch die Anzahl der Zeilen auf maximal 50 beschränkt. Beispielsweise wäre es 100 Zeilen im Test, würde die Zeilenanzahl 50 werden (da es sich bei diesem Code werden nur die ersten 50 Zeilen abgerufen). Wenn nur 30 Zeilen in der Tabelle vorhanden waren, wäre die Zeilenanzahl 30. Rufen Sie **schließen** oder **CloseAll** in den Ausgabeparameter zu laden, bevor Sie diesen Wert abrufen.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von gespeicherten Prozeduren](../../data/oledb/using-stored-procedures.md)