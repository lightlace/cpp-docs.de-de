---
title: "Recordset: Datensatzaktualisierung durch Recordsets (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ODBC-Recordsets, Aktualisieren"
  - "Datensätze, Aktualisieren"
  - "Recordsets, Bearbeiten von Datensätzen"
  - "Recordsets, Aktualisieren"
  - "Aktualisieren von Recordsets"
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Recordset: Datensatzaktualisierung durch Recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dieses Thema bezieht sich auf die MFC\-ODBC\-Klassen.  
  
 Neben ihrer Fähigkeit, Datensätze aus einer Datenquelle auszuwählen, können Recordsets die ausgewählten Datensätze \(optional\) aktualisieren oder löschen und neue Datensätze hinzufügen.  Drei Faktoren bestimmen, ob ein Recordset aktualisierbar ist: ob die damit verbundene Datenquelle aktualisierbar ist, welche Optionen Sie beim Erstellen des Recordset\-Objekts angeben und welche SQL\-Anweisung erstellt wird.  
  
> [!NOTE]
>  Die SQL\-Anweisung, auf der das `CRecordset`\-Objekt beruht, kann Auswirkungen auf die Aktualisierbarkeit des Recordsets haben.  Falls die SQL\-Anweisung z. B. einen Join oder eine **GROUP BY**\-Klausel enthält, legt MFC die Aktualisierbarkeit auf **FALSE** fest.  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 In diesem Thema wird Folgendes erläutert:  
  
-   [Aufgaben beim Aktualisieren eines Recordsets](#_core_your_role_in_recordset_updating) und die Rolle des Frameworks.  
  
-   [Das Recordset als Bearbeitungspuffer](#_core_the_edit_buffer) und die [Unterschiede zwischen Dynasets und Momentaufnahmen](#_core_dynasets_and_snapshots).  
  
 Unter [Recordset: Funktionsweise von AddNew, Edit und Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) werden die Aktionen dieser Funktionen aus der Perspektive des Recordsets beschrieben.  
  
 Unter [Recordset: Weitere Informationen zu Aktualisierungen \(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md) wird abschließend erläutert, wie sich Transaktionen auf Aktualisierungen auswirken, wie das Schließen oder Scrollen bei einem Recordset ausgeführte Aktualisierungen beeinflusst und welche Wechselwirkungen mit Aktualisierungen anderer Benutzer auftreten können.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> Aufgaben beim Aktualisieren eines Recordsets  
 Die folgende Tabelle zeigt, welche Aufgaben Sie beim Hinzufügen, Bearbeiten oder Löschen von Datensätzen eines Recordsets haben und welche Aufgaben das Framework durchführt.  
  
### Recordsetaktualisierung: Interaktion mit dem Framework  
  
|Benutzer|Framework|  
|--------------|---------------|  
|Stellt fest, ob die Datenquelle aktualisierbar ist \(oder erweiterbar\).|Stellt [CDatabase](../../mfc/reference/cdatabase-class.md)\-Memberfunktionen zur Verfügung, mit denen Sie feststellen können, ob die Datenquelle aktualisierbar oder erweiterbar ist.|  
|Öffnen ein aktualisierbares Recordset eines beliebigen Typs.||  
|Stellen fest, ob das Recordset aktualisierbar ist, indem Sie `CRecordset`\-Aktualisierungsfunktionen aufrufen, z. B. `CanUpdate` oder `CanAppend`.||  
|Rufen Memberfunktionen des Recordsets auf, um Datensätze hinzuzufügen, zu bearbeiten oder zu löschen.|Verwaltet den Datenaustausch zwischen dem Recordset\-Objekt und der Datenquelle.|  
|Setzen bei Bedarf Transaktionen ein, um den Aktualisierungsprozess zu steuern.|Stellt `CDatabase`\-Memberfunktionen für die Transaktionsunterstützung zur Verfügung.|  
  
 Weitere Informationen über Transaktionen finden Sie unter [Transaktion \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a> Der Bearbeitungspuffer  
 Die Felddatenmember eines Recordsets fungieren gemeinsam als Bearbeitungspuffer, der einen Datensatz enthält, nämlich den aktuellen Datensatz.  Bei Aktualisierungsoperationen wird dieser Puffer für die Bearbeitung des aktuellen Datensatzes verwendet.  
  
-   Wenn Sie einen Datensatz hinzufügen, wird im Bearbeitungspuffer ein neuer Datensatz erstellt.  Nachdem Sie den Datensatz hinzugefügt haben, wird der Datensatz wieder aktuell, der vorher der aktuelle Datensatz war.  
  
-   Wenn Sie einen Datensatz aktualisieren \(d. h. bearbeiten\), werden im Bearbeitungspuffer die Felddatenmember des Recordsets auf neue Werte eingestellt.  Nachdem Sie die Aktualisierung beendet haben, bleibt der editierte Datensatz der aktuelle Datensatz.  
  
 Wenn Sie [AddNew](../Topic/CRecordset::AddNew.md) oder [Edit](../Topic/CRecordset::Edit.md) aufrufen, wird der aktuelle Datensatz gespeichert, damit er ggf. später wiederhergestellt werden kann.  Wenn Sie [Delete](../Topic/CRecordset::Delete.md) aufrufen, wird der aktuelle Datensatz nicht gespeichert, sondern als gelöscht markiert. Sie müssen dann zu einem anderen Datensatz wechseln.  
  
> [!NOTE]
>  Der Bearbeitungspuffer hat beim Löschen eines Datensatzes keine Funktion.  Wenn Sie den aktuellen Datensatz löschen, wird der Datensatz als gelöscht markiert. Das Recordset ist auf keinen Datensatz eingestellt, bis Sie zu einem anderen Datensatz wechseln.  
  
##  <a name="_core_dynasets_and_snapshots"></a> Dynasets und Momentaufnahmen  
 [Dynasets](../../data/odbc/dynaset.md) aktualisieren den Inhalt eines Datensatzes, wenn Sie zu diesem Datensatz wechseln.  [Momentaufnahmen](../../data/odbc/snapshot.md) sind eine statische Repräsentation der Datensätze. Daher wird der Inhalt eines Datensatzes nicht aktualisiert, solange Sie nicht [Requery](../Topic/CRecordset::Requery.md) aufrufen.  Um den gesamten Funktionsumfang der Dynasets nutzen zu können, müssen Sie mit einem ODBC\-Treiber arbeiten, der den entsprechenden Grad an ODBC\-API\-Unterstützung bietet.  Weitere Informationen finden Sie unter [ODBC](../../data/odbc/odbc-basics.md) und [Dynaset](../../data/odbc/dynaset.md).  
  
## Siehe auch  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset: Funktionsweise von AddNew, Edit und Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)