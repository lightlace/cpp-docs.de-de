---
title: "Datensatzfeldaustausch: Funktionsweise von RFX"
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
  - "Datenbindung [C++], DFX"
  - "ODBC [C++], RFX"
  - "Datensatzbearbeitung [C++], Mit RFX"
  - "RFX (ODBC) [C++], Binden von Feldern und Parametern"
  - "RFX (ODBC) [C++], Aktualisieren von Daten in Recordsets"
  - "Scrollen [C++]"
  - "Scrollen [C++], RFX"
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# Datensatzfeldaustausch: Funktionsweise von RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

In diesem Thema wird der RFX\-Prozess erläutert.  Dies ist ein komplexes Thema, das die folgenden Punkte umfasst:  
  
-   [RFX und Recordset](#_core_rfx_and_the_recordset)  
  
-   [RFX\-Prozess](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von `CRecordset` abgeleitete Objekte, in denen das gesammelte Abrufen von Zeilen nicht implementiert wurde.  Beim gesammelten Abrufen von Zeilen wird der Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) implementiert.  Der Bulk\-RFX ist mit RFX vergleichbar.  Unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) werden die Unterschiede erläutert.  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX und Recordset  
 Die Felddatenmember des Recordset\-Objekts bilden zusammen einen Bearbeitungspuffer, der die ausgewählten Spalten eines Datensatzes enthält.  Wenn das Recordset zum ersten Mal geöffnet ist und unmittelbar bevor der erste Datensatz eingelesen wird, bindet \(verknüpft\) RFX jede ausgewählte Spalte mit der Adresse des zugeordneten Felddatenmembers.  Wenn das Recordset einen Datensatz aktualisiert, ruft RFX ODBC\-API\-Funktionen auf, um die **UPDATE\-**Anweisung oder **INSERT**\-Anweisung von SQL an den Treiber zu übertragen.  RFX kann aufgrund der Informationen über die Felddatenmember die Spalten festlegen, die geschrieben werden sollen.  
  
 Das Framework sichert den Bearbeitungspuffer an bestimmten Punkten, sodass es seinen Inhalt bei Bedarf wiederherstellen kann.  RFX sichert den Bearbeitungspuffer, bevor ein neuer Datensatz hinzugefügt wird und bevor ein vorhandener Datensatz verändert wird.  Es stellt den Bearbeitungspuffer in einigen Fällen wieder her, z. B. nach einer **Update**\-Anweisung, die einer `AddNew`\-Anweisung folgt.  Der Bearbeitungspuffer wird nicht wiederhergestellt, wenn Sie einen gerade geänderten Bearbeitungspuffer verwerfen, indem Sie z. B. zu einem anderen Datensatz wechseln, bevor Sie **Update** aufrufen.  
  
 Neben dem Austausch von Daten zwischen der Datenquelle und den Felddatenmembern des Recordsets verwaltet RFX die Parameterbindung.  Beim Öffnen des nächsten Recordsets werden alle Parameterdatenmember in der Reihenfolge der "?"\-Platzhalter in der von `CRecordset::Open` erstellten SQL\-Anweisung gebunden.  Weitere Informationen hierzu finden Sie unter [Recordset: Parametrisieren eines Recordsets \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Die überschriebene `DoFieldExchange`\-Funktion der Recordset\-Klasse übernimmt die gesamte Arbeit, sie überträgt Daten in beide Richtungen.  Genauso wie der Dialogdatenaustausch \(Dialog Data Exchange, DDX\) benötigt auch RFX Informationen über die Datenmember der Klasse.  Der Assistent stellt die notwendigen Informationen bereit, indem er eine recordsetspezifische **DoFieldExchange\-**Implementierung erstellt, die auf den Namen der Felddatenmember und auf den Datentypen basiert, die Sie mit dem Assistenten angegeben haben.  
  
##  <a name="_core_the_record_field_exchange_process"></a> RFX\-Prozess  
 Dieser Abschnitt beschreibt die Sequenz der RFX\-Ereignisse, wenn ein Recordset\-Objekt geöffnet wird und Sie Datensätze hinzufügen, aktualisieren oder löschen.  Die Tabellen [Reihenfolge der RFX\-Operationen beim Öffnen eines Recordsets](#_core_sequence_of_rfx_operations_during_recordset_open) und [Reihenfolge der RFX\-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling) in diesem Thema zeigen den Prozess, in dem RFX einen **Move**\-Befehl im Recordset verarbeitet und eine Aktualisierung verwaltet.  Im Verlauf dieser Prozesse wird [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) aufgerufen, um diverse Operationen durchzuführen.  Durch den Datenmember **m\_nOperation** des [CFieldExchange](../../mfc/reference/cfieldexchange-class.md)\-Objekts wird festgelegt, welche Operation durchgeführt werden soll.  Lesen Sie vor diesem Thema möglichst die Themen [Recordset: Datensatzauswahl durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [Recordset: Datensatzaktualisierung durch Recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX: Erstmaliges Binden von Spalten und Parametern  
 Wenn Sie die [Open](../Topic/CRecordset::Open.md)\-Memberfunktion eines Recordset\-Objekts aufrufen, löst dies die folgenden RFX\-Aktivitäten in der dargestellten Reihenfolge aus:  
  
-   Falls das Recordset über Parameterdatenmember verfügt, ruft das Framework `DoFieldExchange` auf, um die Parameter an Parameterplatzhalter in der SQL\-Anweisungszeichenfolge des Recordsets zu binden.  Für jeden in der **SELECT**\-Anweisung gefundenen Platzhalter wird eine datentypabhängige Repräsentation des Parameterwerts verwendet.  Diese Operation wird durchgeführt, nachdem die SQL\-Anweisung vorbereitet wurde, aber noch bevor sie ausgeführt wird.  \(Informationen über die Vorbereitung von Anweisungen finden Sie in der ODBC\-Dokumentation der Funktion **::SQLPrepare** in ODBC *Programmer's Reference*.\)  
  
-   Das Framework ruft `DoFieldExchange` ein zweites Mal auf, um die Werte der ausgewählten Spalten an die zugeordneten Felddatenmember im Recordset zu binden.  Dadurch wird das Recordset\-Objekt als Bearbeitungspuffer eingerichtet, der die Spalten des ersten Datensatzes enthält.  
  
-   Das Recordset führt die SQL\-Anweisung aus und die Datenquelle wählt den ersten Datensatz aus.  Die Spalten des Datensatzes werden in die Felddatenmember des Recordsets geladen.  
  
 Die folgende Tabelle zeigt die Reihenfolge der RFX\-Operationen beim Öffnen eines Recordsets.  
  
### Reihenfolge der RFX\-Operationen beim Öffnen eines Recordsets  
  
|Operation|DoFieldExchange\-Operation|Datenbank\-\/SQL\-Operation|  
|---------------|--------------------------------|---------------------------------|  
|1.  Recordset öffnen.|||  
||2.  Erstellen einer SQL\-Anweisung.||  
|||3.  Senden der SQL\-Anweisung.|  
||4.  Binden der Parameterdatenmember.||  
||5.  Binden der Felddatenmember an Spalten.||  
|||6.  ODBC führt die Verschiebung aus und trägt die Daten ein.|  
||7.  Aufbereiten der Daten für C\+\+.||  
  
 Recordsets machen von der vorbereiteten Ausführung von ODBC Gebrauch, damit mit derselben SQL\-Anweisung eine schnelle Neuabfrage durchgeführt werden kann.  Weitere Informationen über die vorbereitete Ausführung finden Sie in der ODBC SDK Programmer's Reference in der MSDN Library.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX: Scrollen  
 Wenn Sie von einem Datensatz zu einem anderen scrollen, ruft das Framework `DoFieldExchange` auf, um die vorher in den Felddatenmembern gespeicherten Werte durch die Werte des neuen Datensatzes zu ersetzen.  
  
 Die folgende Tabelle zeigt die Reihenfolge der RFX\-Operationen, wenn zwischen Datensätzen gewechselt wird.  
  
### Reihenfolge der RFX\-Operationen beim Scrollen  
  
|Operation|DoFieldExchange\-Operation|Datenbank\-\/SQL\-Operation|  
|---------------|--------------------------------|---------------------------------|  
|1.  Aufrufen von `MoveNext` oder einer anderen **Move\-**Funktion.|||  
|||2.  ODBC führt die Verschiebung aus und trägt die Daten ein.|  
||3.  Aufbereiten der Daten für C\+\+.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX: Hinzufügen neuer Datensätze und Bearbeiten vorhandener Datensätze  
 Wenn Sie einen neuen Datensatz hinzufügen, fungiert das Recordset als Bearbeitungspuffer für die Erstellung des Inhalts des neuen Datensatzes.  Genauso wie beim Hinzufügen von Datensätzen findet auch beim Bearbeiten von Datensätzen eine Änderung der Werte der Felddatenmember des Recordsets statt.  Aus Sicht des RFX gilt die folgende Reihenfolge:  
  
1.  Der Aufruf der [AddNew](../Topic/CRecordset::AddNew.md)\-Memberfunktion bzw. [Edit](../Topic/CRecordset::Edit.md)\-Memberfunktion des Recordsets veranlasst RFX, den aktuellen Bearbeitungspuffer zu speichern, um ihn später wiederherstellen zu können.  
  
2.  `AddNew` oder **Edit** bereitet die Felder im Bearbeitungspuffer vor, damit RFX veränderte Felddatenmember ermitteln kann.  
  
     Da bei einem neuen Datensatz keine alten Werte mit den neuen Werten verglichen werden können, stellt `AddNew` den Wert aller Felddatenmember auf den Wert **PSEUDO\_NULL** ein.  Wenn Sie später **Update** aufrufen, vergleicht RFX den Wert jedes Datenmembers mit dem Wert **PSEUDO\_NULL**.  Falls der Datenmember einen anderen Wert enthält, wurde dieser eingestellt. \(**PSEUDO\_NULL** ist ein anderer Wert als der echte NULL\-Wert einer Datensatzspalte; er entspricht auch nicht **NULL** in C\+\+.\)  
  
     Im Gegensatz zu dem **Update**\-Aufruf für `AddNew` werden aktualisierte Werte beim **Update**\-Aufruf für **Edit** mit den vorher gespeicherten Werten verglichen, anstatt **PSEUDO\_NULL** zu verwenden.  Der Unterschied besteht darin, dass `AddNew` über keine vorher gespeicherten Werte verfügt, mit denen die neuen Werte verglichen werden könnten.  
  
3.  Sie legen direkt die Felddatenmember fest, deren Werte Sie bearbeiten möchten oder die in einem neuen Datensatz eingeschrieben werden sollen.  Dazu kann auch der Aufruf von `SetFieldNull` gehören.  
  
4.  Beim Aufruf von [Update](../Topic/CRecordset::Update.md) wird nach geänderten Felddatenmembern gesucht, wie in Schritt 2 beschrieben \(siehe die Tabelle [Reihenfolge der RFX\-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling)\).  Wurden keine Werte geändert, gibt **Update** 0 zurück.  Falls sich einige Felddatenmember geändert haben, bereitet **Update** eine SQL\-**INSERT**\-Anweisung vor, die für alle aktualisierten Felder des Datensatzes Werte enthält, und führt diese Anweisung aus.  
  
5.  Für `AddNew` beendet **Update** seine Arbeit mit der Wiederherstellung der vorher gespeicherten Werte des Datensatzes, der vor dem `AddNew`\-Aufruf der aktuelle Datensatz war.  Für **Edit** bleiben die neuen, geänderten Werte bestehen.  
  
 Die folgende Tabelle zeigt die Reihenfolge der RFX\-Operationen beim Hinzufügen eines neuen Datensatzes oder beim Verändern eines bereits vorhandenen Datensatzes.  
  
### Reihenfolge der RFX\-Operationen bei AddNew und Edit  
  
|Operation|DoFieldExchange\-Operation|Datenbank\-\/SQL\-Operation|  
|---------------|--------------------------------|---------------------------------|  
|1.  Aufrufen von `AddNew` oder **Edit**.|||  
||2.  Sichern des Bearbeitungspuffers.||  
||3.  Für `AddNew`: Markieren der Felddatenmember als "leer" und NULL.||  
|4.  Zuweisen von Werten zu den Felddatenmembern des Recordsets.|||  
|5.  Aufrufen von **Update**.|||  
||6.  Suchen nach veränderten Feldern.||  
||7.  Erstellen einer SQL\-**INSERT**\-Anweisung für `AddNew` bzw. einer **UPDATE**\-Anweisung für **Edit**.||  
|||8.  Senden der SQL\-Anweisung.|  
||9.  Für `AddNew` Wiederherstellen des Bearbeitungspuffers mit dem vorher gesicherten Inhalt.  Für **Edit** Löschen der gesicherten Werte.||  
  
### RFX: Löschen vorhandener Datensätze  
 Wenn Sie einen Datensatz löschen, legt RFX für alle Felder **NULL** fest, um zu markieren, dass der Datensatz gelöscht ist und dass Sie einen anderen Datensatz auswählen müssen.  Weitere Informationen zur RFX\-Reihenfolge sind in diesem Fall nicht erforderlich.  
  
## Siehe auch  
 [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [Nutzen von MFC\-ODBC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Makros, globale Funktionen und globale Variablen](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)