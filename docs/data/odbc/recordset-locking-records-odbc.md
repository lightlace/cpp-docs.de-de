---
title: "Recordset: Sperren von Datens&#228;tzen (ODBC)"
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
  - "Daten [C++], Sperren"
  - "Sperren [C++], Recordsets"
  - "ODBC-Recordsets [C++], Sperren von Datensätzen"
  - "Eingeschränktes Sperren"
  - "Eingeschränktes Sperren, ODBC"
  - "Eingeschränktes Sperren in ODBC"
  - "Recordsets [C++], Sperren von Datensätzen"
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset: Sperren von Datens&#228;tzen (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Verschiedene Arten, einen Datensatz zu sperren](#_core_record.2d.locking_modes).  
  
-   [Sperren von Datensätzen im Recordset während Aktualisierungen](#_core_locking_records_in_your_recordset).  
  
 Wenn Sie mithilfe eines Recordsets einen Datensatz der Datenquelle aktualisieren, kann die Anwendung den Datensatz sperren, sodass kein anderer Benutzer den Datensatz gleichzeitig aktualisieren kann.  Der Zustand eines Datensatzes, der von zwei Benutzern gleichzeitig aktualisiert wurde, ist nicht definiert, solange nicht sichergestellt ist, dass ein Datensatz nicht gleichzeitig von zwei Benutzern aktualisiert werden kann.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Falls Sie das gesammelte Abrufen von Zeilen einsetzen, treffen einige dieser Informationen nicht zu.  Sie können z. B. nicht die **Edit\-**Memberfunktion oder die **Update\-**Memberfunktion aufrufen.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a> Sperrverhalten für Datensätze  
 Die Datenbankklassen stellen zwei Arten von [Datensatz\-Sperrverhalten](../Topic/CRecordset::SetLockingMode.md) bereit:  
  
-   eingeschränktes Sperren \(dies ist der Standard\);  
  
-   vollständiges Sperren.  
  
 Die Aktualisierung eines Datensatzes umfasst drei Schritte:  
  
1.  Sie starten die Operation durch einen Aufruf der [Edit](../Topic/CRecordset::Edit.md)\-Memberfunktion.  
  
2.  Sie ändern die gewünschten Felder des aktuellen Datensatzes.  
  
3.  Sie beenden die Operation \(und führen normalerweise einen Commit für die Aktualisierung aus\), indem Sie die [Update](../Topic/CRecordset::Update.md)\-Memberfunktion aufrufen.  
  
 Beim eingeschränkten Sperren wird der Datensatz in der Datenquelle nur während des **Update**\-Aufrufs gesperrt.  Wenn Sie das eingeschränkte Sperren in einer Mehrbenutzerumgebung verwenden, muss die Anwendung darauf vorbereitet sein, dass während des **Update**\-Aufrufs eine Fehlerbedingung auftreten könnte.  Beim vollständigen Sperren wird der Datensatz gesperrt, sobald Sie **Edit** aufrufen. Die Sperre wird erst wieder aufgehoben, wenn Sie **Update** aufrufen \(Fehler werden über den `CDBException`\-Mechanismus angezeigt, nicht durch Rückgabe von **FALSE** von **Update**\).  Das vollständige Sperren resultiert für andere Benutzer in manchen Fällen in einer Leistungseinbuße, da der Zugriff auf denselben Datensatz möglicherweise so lange verzögert werden muss, bis die Anwendung den **Update**\-Prozess abgeschlossen hat.  
  
##  <a name="_core_locking_records_in_your_recordset"></a> Sperren von Datensätzen im Recordset  
 Um das standardmäßige [Sperrverhalten](#_core_record.2d.locking_modes) eines Recordset\-Objekts zu ändern, müssen Sie den Modus noch vor dem Aufruf von **Edit** ändern.  
  
#### So ändern Sie das aktuelle Sperrverhalten für das Recordset  
  
1.  Rufen Sie die [SetLockingMode](../Topic/CRecordset::SetLockingMode.md)\-Memberfunktion auf, und übergeben Sie ihr entweder den Wert **CRecordset::pessimistic** oder **CRecordset::optimistic**.  
  
 Das neue Sperrverhalten wird angewendet, bis Sie es erneut ändern oder bis das Recordset geschlossen wird.  
  
> [!NOTE]
>  Derzeit wird das vollständige Sperren nur durch verhältnismäßig wenige ODBC\-Treiber unterstützt.  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Ausführen einer Verknüpfung \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Recordset: Hinzufügen, Aktualisieren und Löschen von Datensätzen \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)