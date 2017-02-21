---
title: "CRecordset Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordset class"
  - "database records [C++]"
  - "ODBC-Recordsets [C++], CRecordset-Objekte"
  - "sets of records [C++]"
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt werden.  
  
## Syntax  
  
```  
class CRecordset : public CObject  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordset::CRecordset](../Topic/CRecordset::CRecordset.md)|Erstellt ein `CRecordset`\-Objekt.  Die abgeleitete Klasse muss einen Konstruktor bereitstellen, der dieses aufruft.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordset::AddNew](../Topic/CRecordset::AddNew.md)|Bereitet sich für das Hinzufügen eines neuen Datensatzes vor.  Aufruf `Update`, um der Addition abzuschließen.|  
|[CRecordset::CanAppend](../Topic/CRecordset::CanAppend.md)|Gibt Wert ungleich 0 zurück, wenn neue Datensätze im Recordset über die `AddNew`\-Memberfunktion hinzugefügt werden können.|  
|[CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset Lesezeichen unterstützt.|  
|[CRecordset::Cancel](../Topic/CRecordset::Cancel.md)|Bricht einen asynchronen Vorgang oder einen Prozess aus einem zweiten Thread ab.|  
|[CRecordset::CancelUpdate](../Topic/CRecordset::CancelUpdate.md)|Bricht alle anstehenden Updates aufgrund eines `AddNew` oder `Edit` Vorgangs ab.|  
|[CRecordset::CanRestart](../Topic/CRecordset::CanRestart.md)|Gibt Wert ungleich 0 zurück, wenn `Requery` aufgerufen werden kann, um die Abfrage des Recordsets erneut auszuführen.|  
|[CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|  
|[CRecordset::CanTransact](../Topic/CRecordset::CanTransact.md)|Gibt Wert ungleich 0 zurück, wenn die Datenquelle Transaktionen unterstützt.|  
|[CRecordset::CanUpdate](../Topic/CRecordset::CanUpdate.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset aktualisiert werden kann \(Sie können Datensätze hinzufügen, aktualisieren oder löschen\).|  
|[CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|Aufgerufen, um die Fehler zu behandeln generiert während des Rekordabrufens.|  
|[CRecordset::Close](../Topic/CRecordset::Close.md)|Schließt das Recordset und das ODBC **HSTMT**, das zugeordnet ist.|  
|[CRecordset::Delete](../Topic/CRecordset::Delete.md)|Löscht den aktuellen Datensatz des Recordsets.  Sie müssen zu einem anderen Datensatz nach dem Löschen explizit wechseln.|  
|[CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|Aufgerufen, um Massenzeilen von Daten aus der Datenquelle in das Recordset auszutauschen.  Werkzeugmassen\-datensatzfeldaustausch \(Bulk\-RFX\).|  
|[CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)|Aufgerufen für den Datenaustausch \(in beide Richtungen\) zwischen den Felddatenmembern des Recordsets und dem entsprechenden Datensatz in der Datenquelle.  Implementiert den Datensatzfeldaustausch \(RFX\).|  
|[CRecordset::Edit](../Topic/CRecordset::Edit.md)|Bereitet sich für Änderungen am aktuellen Datensatz vor.  Aufruf `Update`, um die Bearbeitung abzuschließen.|  
|[CRecordset::FlushResultSet](../Topic/CRecordset::FlushResultSet.md)|Gibt Wert ungleich 0 zurück, wenn ein anderes Resultset abgerufen werden müssen, wenn eine vordefinierte Abfrage verwendet wird.|  
|[CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)|Weist den Lesezeichenwert eines Datensatzes im Parameterobjekt zu.|  
|[CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md)|Aufgerufen, um die Standardverbindungszeichenfolge abzurufen.|  
|[CRecordset::GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)|Aufgerufen, um die Zeichenfolge mit SQL abzurufen, um.|  
|[CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CRecordset::GetODBCFieldCount](../Topic/CRecordset::GetODBCFieldCount.md)|Gibt die Anzahl von Feldern im Recordset zurück.|  
|[CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)|Gibt bestimmte Arten von Informationen über die Felder in einem Recordset zurück.|  
|[CRecordset::GetRecordCount](../Topic/CRecordset::GetRecordCount.md)|Gibt die Anzahl von Datensätzen im Recordset zurück.|  
|[CRecordset::GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|Gibt die Anzahl von Datensätzen zurück, die Sie während eines einzigen Abfrage abrufen möchten.|  
|[CRecordset::GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|Gibt die tatsächliche Anzahl der Zeilen zurück, die während eines Abrufs abgerufen werden.|  
|[CRecordset::GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|Gibt den Status der Zeile nach einem Abruf zurück.|  
|[CRecordset::GetSQL](../Topic/CRecordset::GetSQL.md)|Ruft die SQL\-Zeichenfolge ab, die verwendet wird, um Datensätze für das Recordset auszuwählen.|  
|[CRecordset::GetStatus](../Topic/CRecordset::GetStatus.md)|Ruft den Status des Recordsets ab: der Index des aktuellen Datensatzes und ob eine endgültige Anzahl der Datensätze abgerufen wurde.|  
|[CRecordset::GetTableName](../Topic/CRecordset::GetTableName.md)|Ruft den Namen der Tabelle ab, auf der das Recordset basiert.|  
|[CRecordset::IsBOF](../Topic/CRecordset::IsBOF.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset vor dem ersten Datensatz platziert wurde.  Es gibt keinen aktuellen Datensatz.|  
|[CRecordset::IsDeleted](../Topic/CRecordset::IsDeleted.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset auf gelöschten Datensatz platziert wird.|  
|[CRecordset::IsEOF](../Topic/CRecordset::IsEOF.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset hinter dem letzten Datensatz platziert wurde.  Es gibt keinen aktuellen Datensatz.|  
|[CRecordset::IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CRecordset::IsFieldNull](../Topic/CRecordset::IsFieldNull.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz NULL ist \(hat keinen Wert\).|  
|[CRecordset::IsFieldNullable](../Topic/CRecordset::IsFieldNullable.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz festgelegt werden kann, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CRecordset::IsOpen](../Topic/CRecordset::IsOpen.md)|Gibt Wert ungleich 0 zurück, wenn `Open` zuvor aufgerufen wurde.|  
|[CRecordset::Move](../Topic/CRecordset::Move.md)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen im aktuellen Datensatz in beide Richtungen.|  
|[CRecordset::MoveFirst](../Topic/CRecordset::MoveFirst.md)|Positioniert den aktuellen Datensatz auf dem ersten Datensatz des Recordsets.  Test für `IsBOF` zuerst.|  
|[CRecordset::MoveLast](../Topic/CRecordset::MoveLast.md)|Positioniert den aktuellen Datensatz im letzten Datensatz oder im letzten Rowset.  Test für `IsEOF` zuerst.|  
|[CRecordset::MoveNext](../Topic/CRecordset::MoveNext.md)|Positioniert den aktuellen Datensatz des nächsten Datensatz oder auf dem folgenden Rowset.  Test für `IsEOF` zuerst.|  
|[CRecordset::MovePrev](../Topic/CRecordset::MovePrev.md)|Positioniert den aktuellen Datensatz des vorherigen Datensatz oder auf dem vorherigen Rowset.  Test für `IsBOF` zuerst.|  
|[CRecordset::OnSetOptions](../Topic/CRecordset::OnSetOptions.md)|Aufgerufen, um die Optionen \(in Auswahl\) für die angegebene ODBC\-Anweisung festzulegen.|  
|[CRecordset::OnSetUpdateOptions](../Topic/CRecordset::OnSetUpdateOptions.md)|Aufgerufen, um die Optionen \(in Update\) für die angegebene ODBC\-Anweisung festzulegen.|  
|[CRecordset::Open](../Topic/CRecordset::Open.md)|Öffnet das Recordset durch das Abrufen der Tabelle oder Ausführen der Abfrage, die das Recordset darstellt.|  
|[CRecordset::RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|Aktualisiert die Daten und den Status der angegebenen Zeichenfolge.|  
|[CRecordset::Requery](../Topic/CRecordset::Requery.md)|Führt die Abfrage des Recordsets erneut aus, um die ausgewählten Datensätze zu aktualisieren.|  
|[CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md)|Positioniert das Recordset auf dem Datensatz entsprechend der angegebenen Datensatznummer.|  
|[CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)|Positioniert das Recordset auf dem Datensatz, der durch das Lesezeichen angegeben wird.|  
|[CRecordset::SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md)|Markiert das angegebene Feld im aktuellen Datensatz, wie geändert.|  
|[CRecordset::SetFieldNull](../Topic/CRecordset::SetFieldNull.md)|Legt den Wert des angegebenen Felds im aktuellen Datensatz fest, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CRecordset::SetLockingMode](../Topic/CRecordset::SetLockingMode.md)|Legt das "optimistische" Sperren des Sperrverhaltens \(Standard\) oder "das pessimistische" Sperren fest.  Bestimmt, wie Datensätze für Updates gesperrt werden.|  
|[CRecordset::SetParamNull](../Topic/CRecordset::SetParamNull.md)|Legt den angegebenen Parameter fest, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CRecordset::SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|Positioniert den Cursor in der angegebenen Zeile innerhalb des Rowsets.|  
|[CRecordset::SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|Gibt die Anzahl der Datensätze an, die Sie während eines Abrufs abrufen möchten.|  
|[CRecordset::Update](../Topic/CRecordset::Update.md)|Schließt einen `AddNew` oder `Edit` Vorgang durch Speichern der neuen oder geänderten Daten in der Datenquelle.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CRecordset::m\_hstmt](../Topic/CRecordset::m_hstmt.md)|Enthält das ODBC\-Anweisungshandle für das Recordset.  Geben Sie `HSTMT` ein.|  
|[CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)|Enthält die Anzahl der Felddatenmember des Recordsets.  Geben Sie `UINT` ein.|  
|[CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)|Enthält die Anzahl der Parameterdatenmember im Recordset.  Geben Sie `UINT` ein.|  
|[CRecordset::m\_pDatabase](../Topic/CRecordset::m_pDatabase.md)|Enthält einen Zeiger auf `CDatabase`\-Objekt, durch das das Recordset mit einer Datenquelle verbunden ist.|  
|[CRecordset::m\_strFilter](../Topic/CRecordset::m_strFilter.md)|Enthält `CString`, das eine `WHERE`\-Klausel der Structured Query Language \(SQL\) angibt.  Wird als Filter, um nur dieser Datensätze auszuwählen, die bestimmte Kriterien erfüllen.|  
|[CRecordset::m\_strSort](../Topic/CRecordset::m_strSort.md)|Enthält `CString`, das eine Klausel SQL `ORDER BY` angibt.  Wird verwendet, um zu steuern, wie die Datensätze sortiert werden.|  
  
## Hinweise  
 Bei diesen als "Recordsets," werden `CRecordset`\-Objekte in der Regel in zwei Formen verwendet: Dynasets und Momentaufnahmen.  Ein Dynaset bleibt mit den Datenupdates synchronisiert, die von anderen Benutzern vorgenommene.  Eine Momentaufnahme ist eine statische Ansicht der Daten.  Jedes Formular stellt korrigierten Gruppe von Datensätzen dar, wenn das Recordset geöffnet ist, aber wenn Sie zu einem Datensatz in einem Dynaset wechseln, werden die Änderungen widerspiegelt, die nach dem Datensatz, entweder durch andere Benutzer oder von anderen Recordsets in der Anwendung vorgenommen werden.  
  
> [!NOTE]
>  Wenn Sie mit den Datenzugriffsobjekten \(DAO\) Klasse anstatt die Klassen der Open Database Connectivity \(ODBC\), Verwendungsklasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) stattdessen arbeiten.  Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Um mit einem zu arbeiten, das vom Recordset enthält ist, leiten Sie normalerweise eine anwendungsspezifische Recordset\-Klasse von `CRecordset`.  Recordsets wählen Datensätze aus einer Datenquelle aus, und Sie können dann:  
  
-   Bildlauf durch die Datensätze.  
  
-   Aktualisieren Sie die Datensätze und geben Sie ein Sperrverhalten an.  
  
-   Filtern Sie das Recordset, um einzuschränken, das Datensätze es von denen auswählen, die in der Datenquelle verfügbar sind.  
  
-   Sortieren das Recordset.  
  
-   Parametrisieren Sie das Recordset, um seine Auswahl mit den Informationen anzupassen, die erst zur Laufzeit bekannt sind.  
  
 Um die Klasse verwenden, eine Datenbank öffnen und ein Recordset\-Objekt, den Konstruktor übergibt ein Zeiger auf dem `CDatabase`\-Objekt erstellen.  Rufen Sie dann die **Öffnen**\-Memberfunktion des Recordsets auf, auf der Sie angeben können, ob das Objekt ein Dynaset oder eine Momentaufnahme ist.  Das Aufrufen von **Öffnen** wählt Daten aus der Datenquelle aus.  Nachdem das Recordset\-Objekt geöffnet ist, verwenden Sie die Memberfunktionen und Datenmember, einen Bildlauf durch die Datensätze navigieren und sie ausgeführt werden.  Die verfügbaren Vorgänge hängen davon ab, ob das Objekt ein Dynaset oder eine Momentaufnahme ist, ob es aktualisierbar oder schreibgeschützt ist \(dies hängt von der Funktion der Datenquelle der Open Database Connectivity \(ODBC\)\) und ob Sie das gesammelte Abrufen von Zeilen implementiert haben.  So Datensätze aktualisieren, die möglicherweise geändert werden oder hinzugefügt, da der **Öffnen** Aufruf, die **Requery**\-Memberfunktion des Objekts aufrufen.  Rufen Sie die Memberfunktion des Objekts auf **Schließen** und das Objekt zerstört, wenn Sie mit ihr beenden.  
  
 In einer abgeleiteten Klasse wird `CRecordset` Datensatzfeldaustausch \(RFX\) oder den Sammel\-Datensatzfeldaustausch \(Bulk\-RFX\) verwendet, um Lesen und Aktualisieren von Datensatzfeldern zu unterstützen.  
  
 Weitere Informationen über Recordsets und Datensatzfeldaustausch, finden Sie in Artikel [Übersicht: Datenbank\-Programmierung](../../data/data-access-programming-mfc-atl.md), [Recordsets \(ODBC\)](../../data/odbc/recordset-odbc.md), [Recordset: Datensätzen in einer Sammeloperation \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) und [Datensatzfeldaustausch \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  Für einen Fokus auf Dynasets und Momentaufnahmen, finden Sie in Artikel [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## Anforderungen  
 **Header:**  afxdb.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordView Class](../../mfc/reference/crecordview-class.md)