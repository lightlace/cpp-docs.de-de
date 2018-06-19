---
title: 'Recordset: Sortieren von Datensätzen (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- sorting data, recordset data
- ODBC recordsets, sorting
- recordsets, sorting
ms.assetid: b40b152e-0a91-452e-be7b-e5bc27f744c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ddb92016b7b911fc86f2feab27a698ce7fa55c45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090272"
---
# <a name="recordset-sorting-records-odbc"></a>Recordset: Sortieren von Datensätzen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie das Recordset sortiert wird. Sie können angeben, dass eine oder mehrere Spalten auf dem die Sortierung basieren, und Sie können angeben, aufsteigend oder Absteigend (`ASC` oder **"DESC"**; `ASC` ist die Standardeinstellung) für jede Spalte angegeben. Z. B. Wenn Sie zwei Spalten angeben, werden die Datensätze zuerst auf der ersten Spalte und dann auf die zweite Spalte mit dem Namen sortiert. Eine SQL **ORDER BY** -Klausel definiert eine Sortierung. Wenn das Framework fügt die **ORDER BY** -Klausel, um das Recordset SQL-Abfragen, die Klausel-Steuerelemente, die die Auswahl der Sortierung.  
  
 Sie müssen ein Recordset-Sortierreihenfolge einrichten, nach dem Erstellen des Objekts, aber vor dem Aufruf seiner **öffnen** Memberfunktion (oder vor dem Aufruf der **Requery** Memberfunktion für ein vorhandenes Recordset-Objekt dessen **öffnen** Memberfunktion zuvor aufgerufen wurde).  
  
#### <a name="to-specify-a-sort-order-for-a-recordset-object"></a>Angeben eine Sortierreihenfolge für ein Recordset-Objekt  
  
1.  Erstellen Sie ein neues Recordset-Objekt (oder bereiten Aufrufen **Requery** für eine vorhandene).  
  
2.  Legen Sie den Wert, der des Objekts [M_strSort](../../mfc/reference/crecordset-class.md#m_strsort) -Datenmember.  
  
     Die Sortierung ist eine Null-terminierte Zeichenfolge. Es enthält den Inhalt der **ORDER BY** -Klausel jedoch nicht das Schlüsselwort **ORDER BY**. Beispielsweise verwenden:  
  
    ```  
    recordset.m_strSort = "LastName DESC, FirstName DESC";  
    ```  
  
     not  
  
    ```  
    recordset.m_strSort = "ORDER BY LastName DESC, FirstName DESC";  
    ```  
  
3.  Legen Sie alle anderen Optionen, die Sie benötigen, die können Sie z. B. einen Filter, Sperrverhalten oder Parameter.  
  
4.  Rufen Sie **öffnen** für das neue Objekt (oder **Requery** für ein vorhandenes Objekt).  
  
 Die ausgewählten Datensätze werden sortiert nach den Angaben. Um einen Satz von Studentendatensätze nach Nachnamen und dann die Vornamen in absteigender Reihenfolge zu sortieren, führen Sie z. B. Folgendes ein:  
  
```  
// Construct the recordset  
CStudentSet rsStudent( NULL );  
// Set the sort  
rsStudent.m_strSort = "LastName DESC, FirstName DESC";  
// Run the query with the sort in place  
rsStudent.Open( );  
```  
  
 Das Recordset enthält alle Studentendatensätze, die in absteigender Reihenfolge sortiert (Z bis A) nach dem Nachnamen, dann nach Vornamen.  
  
> [!NOTE]
>  Falls gewünscht, auf das Recordset Standard-SQL-Zeichenfolge zu überschreiben, indem Sie eine eigene SQL-Zeichenfolge zu übergeben **öffnen**, eine Sortierung nicht festgelegt, wenn die benutzerdefinierte Zeichenfolge ist ein **ORDER BY** Klausel.  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)   
 [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)