---
title: 'Recordset: Datensatzaktualisierung durch Recordsets (ODBC) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- records, updating
- ODBC recordsets, updating
- recordsets, editing records
- updating recordsets
- recordsets, updating
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e38f2e62e9aa7b01680e9b2fd1e4a540ee552c3c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-how-recordsets-update-records-odbc"></a>Recordset: Datensatzaktualisierung durch Recordsets (ODBC)
Dieses Thema bezieht sich auf die MFC-ODBC-Klassen.  
  
 Neben ihrer Fähigkeit zum Auswählen von Datensätzen aus einer Datenquelle können Recordsets (optional) aktualisieren oder löschen Sie die ausgewählten Datensätze oder neue Datensätze hinzufügen. Drei Faktoren ermitteln, die ein Recordset aktualisierbar: Gibt an, ob die verbundene Datenquelle aktualisierbar ist, sind die Optionen, die Sie angeben, beim Erstellen von einem Recordset-Objekt und SQL, die erstellt wird.  
  
> [!NOTE]
>  SQL auf dem Ihre `CRecordset` Objekt basiert das Recordset aktualisierbar auswirken können. Beispielsweise, wenn Ihre SQL-Anweisung einen Join enthält oder einen **GROUP BY** -Klausel legt MFC auf die Updateability **"false"**.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Ihre Rolle Aktualisieren eines Recordsets](#_core_your_role_in_recordset_updating) und was das Framework für Sie erledigt.  
  
-   [Das Recordset als Bearbeitungspuffer](#_core_the_edit_buffer) und [Unterschiede zwischen Dynasets und Momentaufnahmen](#_core_dynasets_and_snapshots).  
  
 [Recordset: Wie AddNew, Edit und Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) beschreibt die Aktionen dieser Funktionen aus der Sicht des Recordsets.  
  
 [Recordset: Weitere Informationen zu Aktualisierungen (ODBC)](../../data/odbc/recordset-more-about-updates-odbc.md) Abschluss Recordset Update Story erläutert Auswirkungen von Transaktionen auf Aktualisierungen und Auswirkungen ein Recordsets schließen oder einen Bildlauf Updates werden ausgeführt wie Ihre Updates mit den Updates von anderen interagieren Benutzer.  
  
##  <a name="_core_your_role_in_recordset_updating"></a>Der Rolle im Recordset aktualisieren  
 Die folgende Tabelle zeigt die Rolle anhand einer Recordsets hinzufügen, bearbeiten oder Löschen von Datensätzen, zusammen mit, was das Framework für Sie erledigt.  
  
### <a name="recordset-updating-you-and-the-framework"></a>Aktualisieren eines Recordsets: Sie und das Framework  
  
|Benutzer|Das Framework|  
|---------|-------------------|  
|Bestimmen Sie, ob die Datenquelle aktualisierbar (oder erweiterbar) ist.|Stellt [CDatabase](../../mfc/reference/cdatabase-class.md) Memberfunktionen für der Datenquelle aktualisierbar oder erweiterbar ist.|  
|Öffnen Sie ein aktualisierbares Recordset (eines beliebigen Typs).||  
|Bestimmen Sie, ob das Recordset aktualisierbar, durch den Aufruf ist `CRecordset` Funktionen wie z. B. aktualisieren `CanUpdate` oder `CanAppend`.||  
|Rufen Sie Recordset Memberfunktionen zum Hinzufügen, bearbeiten und Löschen von Datensätzen.|Verwaltet den Austausch von Daten zwischen der Recordset-Objekt und der Datenquelle.|  
|Verwenden Sie optional Transaktionen, um den Updatevorgang dahingehend zu steuern.|Stellt `CDatabase` Memberfunktionen zur Unterstützung von Transaktionen.|  
  
 Weitere Informationen über Transaktionen finden Sie unter [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a>Der Bearbeitungspuffer  
 Gesamtheit, die Felddatenmembern eines Recordset-Objekts dienen als Bearbeitungspuffer, die einen Datensatz enthält, den aktuellen Datensatz. Update-Vorgänge verwenden diesen Puffer für den aktuellen Datensatz ausgeführt werden.  
  
-   Wenn Sie einen Datensatz hinzufügen, wird der Bearbeitungspuffer verwendet, um einen neuen Datensatz zu erstellen. Wenn Sie fertig sind, den Datensatz hinzufügen, wird der Datensatz, der zuvor war erneut aktuelle.  
  
-   Bei der Aktualisierung ist (Bearbeiten) einen Datensatz, bearbeiten-Puffer verwendet, um neue Werte der Felddatenmember der Recordset fest. Wenn Sie fertig sind, aktualisieren, wird der aktualisierte Datensatz aktuell.  
  
 Beim Aufruf [AddNew](../../mfc/reference/crecordset-class.md#addnew) oder [bearbeiten](../../mfc/reference/crecordset-class.md#edit), der aktuelle Datensatz wird gespeichert, damit sie später nach Bedarf wiederhergestellt werden kann. Beim Aufruf [löschen](../../mfc/reference/crecordset-class.md#delete), der aktuelle Datensatz nicht gespeichert, sondern als gelöscht markiert und müssen Sie einen Bildlauf zu einem anderen Datensatz durchführen.  
  
> [!NOTE]
>  Der Bearbeitungspuffer spielt keine Rolle Löschen eines Datensatzes. Wenn Sie den aktuellen Datensatz löschen, wird der Datensatz als gelöscht markiert, und das Recordset ist "nicht in einem Datensatz", bis Sie einen zu einem anderen Datensatz Bildlauf.  
  
##  <a name="_core_dynasets_and_snapshots"></a>Dynasets und Momentaufnahmen  
 [Dynasets](../../data/odbc/dynaset.md) aktualisieren den Inhalt eines Datensatzes, wie Sie einen zu dem Datensatz Bildlauf. [Momentaufnahmen](../../data/odbc/snapshot.md) sind statische Repräsentation der Datensätze, damit der Inhalt eines Datensatzes nicht aktualisiert werden, es sei denn, Sie rufen [Requery](../../mfc/reference/crecordset-class.md#requery). Um die volle Funktionalität des Dynasets verwenden zu können, müssen Sie mit einem ODBC-Treiber arbeiten, die das richtige Maß an ODBC API-Unterstützung entspricht. Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [Dynaset](../../data/odbc/dynaset.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Funktionsweise von AddNew, Edit und Delete (ODBC)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)