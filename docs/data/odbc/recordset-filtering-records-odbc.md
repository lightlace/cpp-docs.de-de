---
title: "Recordset: Filtern von Datensätzen (ODBC) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- data [MFC], filtering
- recordsets [C++], filtering
- filtering recordsets
- ODBC recordsets [C++], filtering records
- filters [C++], recordset object
ms.assetid: 5c075f37-c837-464d-90c1-d028a9d1c175
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b6d6e8b41e67c9f33d643a2f64c7bdf2d2251eff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-filtering-records-odbc"></a>Recordset: Filtern von Datensätzen (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 In diesem Thema wird erläutert, wie auf einem Recordset filtern, sodass nur eine bestimmte Teilmenge der verfügbaren Datensätze ausgewählt werden. Sie möchten z. B. nur die Klasse Abschnitte für einen bestimmten Kurs, z. B. MATH101 auswählen. Ein Filter ist eine Suchbedingung erfüllen, definiert durch den Inhalt eines SQL- **, in denen** Klausel. Wenn das Framework für das Recordset-SQL-Anweisung, fügt die **, in denen** Klausel schränkt die Auswahl.  
  
 Sie müssen einem Recordset-Objekt Filter einrichten, nach dem Erstellen des Objekts, aber vor dem Aufrufen der **öffnen** Memberfunktion (oder vor dem Aufruf der **Requery** Memberfunktion für ein bereits vorhandenes Recordset Objekt, dessen **öffnen** Memberfunktion zuvor aufgerufen wurde).  
  
#### <a name="to-specify-a-filter-for-a-recordset-object"></a>Angeben ein Filters für ein Recordset-Objekt  
  
1.  Erstellen Sie ein neues Recordset-Objekt (oder bereiten Aufrufen **Requery** für ein vorhandenes Objekt).  
  
2.  Legen Sie den Wert, der des Objekts [M_strFilter](../../mfc/reference/crecordset-class.md#m_strfilter) -Datenmember.  
  
     Der Filter ist eine Null-terminierte Zeichenfolge mit dem Inhalt der SQL- **, in denen** -Klausel jedoch nicht das Schlüsselwort **, in denen**. Beispielsweise verwenden:  
  
    ```  
    m_pSet->m_strFilter = "CourseID = 'MATH101'";  
    ```  
  
     not  
  
    ```  
    m_pSet->m_strFilter = "WHERE CourseID = 'MATH101'";  
    ```  
  
    > [!NOTE]
    >  Das Zeichenfolgenliteral "MATH101" wird durch einfache Anführungszeichen, die oben angezeigt. In der ODBC-SQL-Spezifikation sind einfache Anführungszeichen verwendet, um ein Zeichenfolgenliteral zu kennzeichnen. Überprüfen der ODBC-Treiber-Dokumentation für die zitieren Anforderungen des DBMS in dieser Situation. Diese Syntax wird ebenfalls erläutert weiter hinten in diesem Thema.  
  
3.  Legen Sie alle anderen Optionen, die Sie, die z. b. Sortierreihenfolge, Sperrverhalten oder Parameter benötigen. Es ist besonders nützlich, einen Parameter angeben. Informationen zur Parametrisierung eines Filters finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
4.  Rufen Sie **öffnen** für das neue Objekt (oder **Requery** für ein zuvor geöffneten Objekt).  
  
> [!TIP]
>  Verwenden von Parametern im Filter ist möglicherweise die effizienteste Methode zum Abrufen von Datensätzen.  
  
> [!TIP]
>  Recordset-Filter sind nützlich für [verknüpfen](../../data/odbc/recordset-performing-a-join-odbc.md) Tabellen und für die Verwendung von [Parameter](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) auf Basis der Informationen abgerufen oder zur Laufzeit berechnet.  
  
 Das Recordset wählt nur die Datensätze, die die Suchbedingung erfüllen, die Sie angegeben haben. Oben z. B. an, dass der Kurs Filter beschriebenen (vorausgesetzt, eine Variable `strCourseID` derzeit festgelegt, z. B. "MATH101"), gehen Sie folgendermaßen vor:  
  
```  
// Using the recordset pointed to by m_pSet  
  
// Set the filter  
m_pSet->m_strFilter = "CourseID = " + strCourseID;   
  
// Run the query with the filter in place  
if ( m_pSet->Open( CRecordset::snapshot, NULL, CRecordset::readOnly ) )  
  
// Use the recordset  
```  
  
 Das Recordset enthält Datensätze für alle Bereiche der Klasse für MATH101.  
  
 Beachten Sie, wie die Filterzeichenfolge im Beispiel oben, verwenden eine Zeichenfolgenvariable festgelegt wurde. Dies ist die typische Nutzung. Aber angenommen, Sie möchten, geben Sie den literalen Wert 100 für die Kurs-ID Der folgende Code zeigt, wie Sie die Filterzeichenfolge ordnungsgemäß mit einem Literalwert festlegen:  
  
```  
m_strFilter = "StudentID = '100'";   // correct  
```  
  
 Beachten Sie die Verwendung der einfachen Anführungszeichen. Wenn Sie die Filterzeichenfolge direkt festlegen, wird die Filterzeichenfolge **nicht**:  
  
```  
m_strFilter = "StudentID = 100";   // incorrect for some drivers  
```  
  
 Der ODBC-Spezifikation entspricht der oben gezeigten zitieren, jedoch einige DBMS möglicherweise andere Anführungszeichen erforderlich. Weitere Informationen finden Sie unter [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
> [!NOTE]
>  Wunsch das Recordset Standard-SQL-Zeichenfolge zu überschreiben, indem Sie eine eigene SQL-Zeichenfolge zu übergeben **öffnen**, einen Filter sollte nicht festgelegt werden, wenn die benutzerdefinierte Zeichenfolge ist ein **, in denen** Klausel. Weitere Informationen zum Überschreiben des Standard-SQL finden Sie unter [SQL: Anpassen eines Recordsets SQL-Anweisung (ODBC)](../../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)   
 [Recordset: Datensatzauswahl durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Recordset: Datensatzaktualisierung durch Recordsets (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)   
 [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md)