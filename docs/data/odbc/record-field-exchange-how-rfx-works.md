---
title: 'Datensatzfeldaustausch: Funktionsweise von RFX | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- record editing [C++], using RFX
- RFX (ODBC) [C++], updating data in recordsets
- scrolling [C++]
- ODBC [C++], RFX
- data binding [C++], DFX
- scrolling [C++], RFX
- RFX (ODBC) [C++], binding fields and parameters
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 5eac97bb87103bd72dfd721515baf58324fc851f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-how-rfx-works"></a>Datensatzfeldaustausch: Funktionsweise von RFX
In diesem Thema wird der RFX-Prozess beschrieben. Dies ist eine erweiterte abdeckenden Thema:  
  
-   [RFX und Recordsets](#_core_rfx_and_the_recordset)  
  
-   [RFX-Prozess](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  Dieses Thema bezieht sich auf von abgeleiteten Klassen `CRecordset` in denen der gesammelte Abrufen von Zeilen nicht implementiert wurde. Wenn Sie gesammelte verwenden, wird der Massen-Datensatzfeldaustausch (Bulk-RFX) implementiert. Bulk RFX ähnelt RFX. Um die Unterschiede zu verstehen, finden Sie unter [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_rfx_and_the_recordset"></a>RFX und Recordsets  
 Das Recordset-Objekt Felddatenmember, gemeinsam bilden Bearbeitungspuffer, der die ausgewählten Spalten eines Datensatzes enthält. Wenn das Recordset zuerst geöffnet wird und zum Lesen des ersten Datensatzes, RFX bindet (verknüpft) ausgewählte jede Spalte an die Adresse des Datenmembers entsprechende Feld. Wenn das Recordset einen Datensatz aktualisiert, ruft RFX ODBC-API-Funktionen, um eine SQL send- **UPDATE** oder **einfügen** Anweisung an den Treiber. RFX verwendet Beleg für den Felddatenmembern an die Spalten zu schreiben.  
  
 Das Framework sichert den Bearbeitungspuffer in bestimmten Phasen, sodass er seinen Inhalt bei Bedarf wiederhergestellt werden kann. RFX sichert den Bearbeitungspuffer, vor dem Hinzufügen eines neuen Datensatzes und bevor Sie einen vorhandenen Datensatz bearbeiten. Bearbeitungspuffer in einigen Fällen, z. B. wiederhergestellt, nachdem ein **Update** Aufruf Folgendes `AddNew`. Der Bearbeitungspuffer wird nicht wiederhergestellt werden, wenn Sie eine neu geänderten Bearbeitungspuffer verwerfen, indem Sie z. B. verschieben zu einem anderen Datensatz vor dem Aufruf **Update**.  
  
 Neben den Austausch von Daten zwischen der Datenquelle und das Recordset-Felddatenmember, verwaltet RFX Bindungsparameter. Beim Öffnen des Recordsets wird Parameterdatenmember in der Reihenfolge der gebunden sind die "?" Platzhalter in der SQL-Anweisung, die `CRecordset::Open` erstellt. Weitere Informationen finden Sie unter [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Das Außerkraftsetzen des Recordset-Klasse der `DoFieldExchange` wird die gesamte Arbeit, Verschieben von Daten in beide Richtungen. Wie Dialogdatenaustausch (DDX) benötigt RFX Informationen über die Datenmember der Klasse. Der Assistent bietet die erforderlichen Informationen, indem Sie schreiben eine Recordset-spezifische Implementierung der `DoFieldExchange` , basierend auf die Felddaten Member-Namen und Datentypen Sie, mit dem Assistenten angeben.  
  
##  <a name="_core_the_record_field_exchange_process"></a>RFX-Prozess  
 In diesem Abschnitt wird die Abfolge der RFX-Ereignisse beschrieben, wie einem Recordset-Objekt geöffnet ist und wie Sie hinzugefügt haben, aktualisieren und Löschen von Datensätzen. Die Tabelle [Sequenz der RFX-Operationen beim Öffnen eines Recordset](#_core_sequence_of_rfx_operations_during_recordset_open) und die Tabelle [Sequenz der RFX-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling) in diesem Thema zeigen den Prozess RFX Prozesse eine **verschieben**Befehl im Recordset und ein Update verwaltet. Bei diesen Prozessen [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) wird aufgerufen, um viele andere Vorgänge ausführen. Die **M_nOperation** Datenmember der [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt bestimmt, welcher Vorgang angefordert wird. Sie finden es vielleicht hilfreich, lesen Sie [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) und [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md) vor dem Lesen diese Materialien beziehen.  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a>RFX: Binden von Spalten und Parametern  
 Die folgenden RFX-Aktivitäten auftreten, in der Reihenfolge angezeigt, wenn Sie einem Recordset-Objekt aufrufen [öffnen](../../mfc/reference/crecordset-class.md#open) Memberfunktion:  
  
-   Wenn das Recordset Parameterdatenmember verfügt, das Framework ruft `DoFieldExchange` Parameter Parameterplatzhalter in die Zeichenfolge des Recordsets SQL-Anweisung zu binden. Typabhängige Darstellung des Werts des Parameters, für jeden Platzhalter verwendet wird Daten gefunden, der **wählen** Anweisung. Dies tritt auf, nachdem die SQL-Anweisung vorbereitet ist, aber bevor er ausgeführt wird. Informationen zur Vorbereitung der Anweisung finden Sie unter der **:: SQLPrepare** -Funktion in der ODBC *Programmer's Reference*.  
  
-   Das Framework ruft `DoFieldExchange` ein zweites Mal aus, um die Werte der ausgewählten Spalten entsprechenden Felddatenmembern im Recordset zu binden. Hierdurch wird das Recordset-Objekt als Bearbeitungspuffer mit den Spalten des ersten Datensatzes.  
  
-   Das Recordset führt die SQL-Anweisung aus, und die Datenquelle wählt den ersten Datensatz. Die Spalten des Datensatzes werden in das Recordset-Felddatenmember geladen.  
  
 In der folgenden Tabelle veranschaulicht die Abfolge der RFX-Operationen beim Öffnen eines Recordsets.  
  
### <a name="_core_sequence_of_rfx_operations_during_recordset_open"></a>Reihenfolge der RFX-Operationen beim Öffnen eines Recordsets  
  
|Der Vorgang zum|DoFieldExchange-Vorgang|Datenbank-SQL-Vorgang|  
|--------------------|-------------------------------|-----------------------------|  
|1. Öffnen des Recordsets.|||  
||2. Erstellen Sie eine SQL-Anweisung.||  
|||3. Senden Sie die SQL ein.|  
||4. Parameterdatenmember zu binden.||  
||5. Binden Sie Felddatenmember an Spalten.||  
|||6. ODBC ist das Verschieben und in den Daten füllt.|  
||7. Beheben Sie die Daten für C++.||  
  
 Recordsets verwenden ODBCs vorbereitete Ausführung, um zu ermöglichen, schnelle erneutes Abfragen mit der gleichen SQL-Anweisung. Weitere Informationen über die vorbereitete Ausführung finden Sie im ODBC-SDK *Programmer's Reference* in der MSDN Library.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a>RFX: Durchführen eines Bildlaufs  
 Wenn Sie einen Datensatz zu einem anderen scrollen, um das Framework ruft `DoFieldExchange` zuvor in den Felddatenmembern Werte für den neuen Eintrag gespeicherten Werte zu ersetzen.  
  
 In der folgenden Tabelle veranschaulicht die Abfolge der RFX-Vorgänge, wenn der Benutzer von Datensatz zu Datensatz bewegt.  
  
### <a name="_core_sequence_of_rfx_operations_during_scrolling"></a>Sequenz der RFX-Vorgänge während des Bildlaufs  
  
|Der Vorgang zum|DoFieldExchange-Vorgang|Datenbank-SQL-Vorgang|  
|--------------------|-------------------------------|-----------------------------|  
|1. Rufen Sie `MoveNext` oder einer anderen Move-Funktion.|||  
|||2. ODBC ist das Verschieben und in den Daten füllt.|  
||3. Beheben Sie die Daten für C++.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a>RFX: Neue Datensätze hinzufügen und Bearbeiten vorhandener Einträge  
 Wenn Sie einen neuen Datensatz hinzufügen, fungiert das Recordset als Bearbeitungspuffer, um den Inhalt des neuen Datensatzes zu erstellen. Wie beim Hinzufügen von Datensätzen, umfasst das Bearbeiten von Datensätzen ändern der Werte der Felddatenmember der Recordset. Aus der RFX-Perspektive ist die Sequenz wie folgt:  
  
1.  Rufen Sie des Recordsets [AddNew](../../mfc/reference/crecordset-class.md#addnew) oder [bearbeiten](../../mfc/reference/crecordset-class.md#edit) Memberfunktion führt dazu, dass RFX, den aktuellen Bearbeitungspuffer zu speichern, damit sie später wiederhergestellt werden kann.  
  
2.  `AddNew`oder **bearbeiten** bereitet die Felder im Bearbeitungspuffer vor, sodass RFX geänderten Felddatenmember erkennen kann.  
  
     Da ein neuer Datensatz keine alten Werte mit neue Werten verglichen wurde `AddNew` legt den Wert für jedes felddatenelement auf eine **PSEUDO_NULL** Wert. Wenn Sie rufen später **Update**, RFX vergleicht jedes Datenelement-Wert mit der **PSEUDO_NULL** Wert. Wenn es ein Unterschied, wurde das Datenelement festgelegt. (**PSEUDO_NULL** entspricht nicht dem als Datensatzspalte mit einem Null-Wert "true" noch eine dieser Optionen ist identisch mit C++ **NULL**.)  
  
     Im Gegensatz zu den **Update** rufen Sie für `AddNew`, die **Update** für Aufrufen **bearbeiten** vergleicht Werte mit zuvor gespeicherten Werte, anstatt aktualisiert**PSEUDO_NULL**. Der Unterschied besteht darin, die `AddNew` hat keine zuvor gespeicherten Werte für den Vergleich.  
  
3.  Die Werte der Felddatenmember wird direkt festgelegt, deren Werte, die Sie bearbeiten möchten oder dass für einen neuen Datensatz gefüllte werden sollen. Dies kann Folgendes aufrufen umfassen `SetFieldNull`.  
  
4.  Rufen Sie [Update](../../mfc/reference/crecordset-class.md#update) sucht der geänderten Felddatenmember, wie in Schritt 2 beschrieben (finden Sie in der Tabelle [Sequenz der RFX-Operationen beim Scrollen](#_core_sequence_of_rfx_operations_during_scrolling)). Wenn keine geändert haben, **Update** gibt 0 zurück. Wenn einige Felddatenmember geändert haben, **Update** vorbereitet und führt eine SQL **einfügen** -Anweisung, die Werte für alle aktualisierten Felder im Datensatz enthält.  
  
5.  Für `AddNew`, **Update** wird beendet, indem Sie die Wiederherstellung der zuvor gespeicherten Werte des Datensatzes, der vor dem aktuellen wurde die `AddNew` aufrufen. Für **bearbeiten**, die neuen, geänderten Werte bleiben unverändert.  
  
 In der folgenden Tabelle zeigt die Abfolge der RFX-Vorgänge aus, wenn Sie einen neuen Datensatz hinzufügen oder ein vorhandenes Datensatzes bearbeiten.  
  
### <a name="sequence-of-rfx-operations-during-addnew-and-edit"></a>Reihenfolge der RFX-Operationen bei AddNew und bearbeiten  
  
|Der Vorgang zum|DoFieldExchange-Vorgang|Datenbank-SQL-Vorgang|  
|--------------------|-------------------------------|-----------------------------|  
|1. Rufen Sie `AddNew` oder **bearbeiten**.|||  
||2. Sichern Sie den Bearbeitungspuffer.||  
||3. Für `AddNew`Felddatenmember als "bereinigen" zu markieren, und Null.||  
|4. Recordset-Felddatenmembern Werte zuweisen.|||  
|5. Rufen Sie **Update**.|||  
||6. Überprüfen Sie die geänderten Felder.||  
||7. Erstellen von SQL **einfügen** -Anweisung für `AddNew` oder **UPDATE** -Anweisung für **bearbeiten**.||  
|||8. Senden Sie die SQL ein.|  
||9. Für `AddNew`, Bearbeitungspuffer an seinen Inhalt gesicherte wiederherstellen. Für **bearbeiten**, löschen Sie die Sicherung.||  
  
### <a name="rfx-deleting-existing-records"></a>RFX: Löschen von Datensätzen  
 Wenn Sie einen Datensatz löschen, legt RFX alle Felder auf **NULL** Erinnerung, die der Datensatz gelöscht und müssen Sie verschieben, deaktiviert sie. Sie können weitere Informationen zur RFX-Sequenz ist nicht erforderlich.  
  
## <a name="see-also"></a>Siehe auch  
 [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC-ODBC-nutzen](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Makros, globale Funktionen und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)  
 [CDBException-Klasse](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset:: DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange)