---
title: "CDaoRecordset Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordset-Klasse"
  - "Datensätze, CDaoRecordSet"
  - "Recordsets, Typen"
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CDaoRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Gruppe von Datensätzen, die aus einer Datenquelle ausgewählt werden.  
  
## Syntax  
  
```  
  
class CDaoRecordset : public CObject  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDaoRecordset::CDaoRecordset](../Topic/CDaoRecordset::CDaoRecordset.md)|Erstellt ein `CDaoRecordset`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDaoRecordset::AddNew](../Topic/CDaoRecordset::AddNew.md)|Bereitet sich für das Hinzufügen eines neuen Datensatzes vor.  Aufruf [Update](../Topic/CDaoRecordset::Update.md), um der Addition abzuschließen.|  
|[CDaoRecordset::CanAppend](../Topic/CDaoRecordset::CanAppend.md)|Gibt Wert ungleich 0 zurück, wenn neue Datensätze im Recordset über die [AddNew](../Topic/CDaoRecordset::AddNew.md)\-Memberfunktion hinzugefügt werden können.|  
|[CDaoRecordset::CanBookmark](../Topic/CDaoRecordset::CanBookmark.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset Lesezeichen unterstützt.|  
|[CDaoRecordset::CancelUpdate](../Topic/CDaoRecordset::CancelUpdate.md)|Bricht alle anstehenden Updates aufgrund eines [Bearbeiten](../Topic/CDaoRecordset::Edit.md) oder [AddNew](../Topic/CDaoRecordset::AddNew.md) Vorgangs ab.|  
|[CDaoRecordset::CanRestart](../Topic/CDaoRecordset::CanRestart.md)|Gibt Wert ungleich 0 zurück, wenn [Fragen Sie erneut ab](../Topic/CDaoRecordset::Requery.md) aufgerufen werden kann, um die Abfrage des Recordsets erneut auszuführen.|  
|[CDaoRecordset::CanScroll](../Topic/CDaoRecordset::CanScroll.md)|Gibt Wert ungleich 0 \(null\) zurück, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|  
|[CDaoRecordset::CanTransact](../Topic/CDaoRecordset::CanTransact.md)|Gibt Wert ungleich 0 zurück, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDaoRecordset::CanUpdate](../Topic/CDaoRecordset::CanUpdate.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset aktualisiert werden kann \(Sie können Datensätze hinzufügen, aktualisieren oder löschen\).|  
|[CDaoRecordset::Close](../Topic/CDaoRecordset::Close.md)|Schließt das Recordset.|  
|[CDaoRecordset::Delete](../Topic/CDaoRecordset::Delete.md)|Löscht den aktuellen Datensatz des Recordsets.  Sie müssen zu einem anderen Datensatz nach dem Löschen explizit wechseln.|  
|[CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)|Aufgerufen für den Datenaustausch \(in beide Richtungen\) zwischen den Felddatenmembern des Recordsets und dem entsprechenden Datensatz in der Datenquelle.  Werkzeug\-DAO\-Datensatzfeldaustausch \(DFX\).|  
|[CDaoRecordset::Edit](../Topic/CDaoRecordset::Edit.md)|Bereitet sich für Änderungen am aktuellen Datensatz vor.  Aufruf **Update**, um die Bearbeitung abzuschließen.|  
|[CDaoRecordset::FillCache](../Topic/CDaoRecordset::FillCache.md)|Füllt die gesamte oder einen Teil lokalen Cache für ein Recordset\-Objekt aus, das Daten aus einer ODBC\-Datenquelle enthält.|  
|[CDaoRecordset::Find](../Topic/CDaoRecordset::Find.md)|Sucht den ersten, nächsten, vorherigen oder letzten Speicherort einer bestimmten Zeichenfolge in einem Recordset vom Typ Dynaset, das die angegebenen Kriterien erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::FindFirst](../Topic/CDaoRecordset::FindFirst.md)|Findet den ersten Satz in einem Recordset oder vom Typ Dynaset Momentaufnahme vom Typ, das die angegebenen Kriterien erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::FindLast](../Topic/CDaoRecordset::FindLast.md)|Findet den letzten Datensatz in einem Recordset oder vom Typ Dynaset Momentaufnahme vom Typ, das die angegebenen Kriterien erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::FindNext](../Topic/CDaoRecordset::FindNext.md)|Findet den nächsten Datensatz in einem Recordset oder vom Typ Dynaset Momentaufnahme vom Typ, das die angegebenen Kriterien erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::FindPrev](../Topic/CDaoRecordset::FindPrev.md)|Findet den vorherigen Satz in einem Recordset oder vom Typ Dynaset Momentaufnahme vom Typ, das die angegebenen Kriterien erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::GetAbsolutePosition](../Topic/CDaoRecordset::GetAbsolutePosition.md)|Gibt die Datensatznummer des aktuellen Datensatzes eines Recordset\-Objekts zurück.|  
|[CDaoRecordset::GetBookmark](../Topic/CDaoRecordset::GetBookmark.md)|Gibt einen Wert zurück, der das Lesezeichen auf einem Datensatz darstellt.|  
|[CDaoRecordset::GetCacheSize](../Topic/CDaoRecordset::GetCacheSize.md)|Gibt einen Wert zurück, der die Anzahl von Datensätzen in einem Recordset vom Typ Dynaset angibt, das aus einer ODBC\-Datenquelle enthält die lokal zwischengespeichert werden, Daten.|  
|[CDaoRecordset::GetCacheStart](../Topic/CDaoRecordset::GetCacheStart.md)|Gibt einen Wert zurück, der das Lesezeichen des ersten Datensatzes im zwischengespeichert werden Recordset angibt.|  
|[CDaoRecordset::GetCurrentIndex](../Topic/CDaoRecordset::GetCurrentIndex.md)|Gibt `CString` zurück, das den Namen des Indexes enthält, der auf indizierten, `CDaoRecordset` vom Typ Tabelle zuletzt verwendet wird.|  
|[CDaoRecordset::GetDateCreated](../Topic/CDaoRecordset::GetDateCreated.md)|Gibt das Datum und die Uhrzeit zurück, die die zugrunde liegende Basistabelle ein Objekt erstellt wurde `CDaoRecordset`|  
|[CDaoRecordset::GetDateLastUpdated](../Topic/CDaoRecordset::GetDateLastUpdated.md)|Gibt das Datum und die Uhrzeit der letzten Änderung zurück, die am Entwurf einer zugrunde liegenden Basistabelle ein `CDaoRecordset`\-Objekt vorgenommen wird.|  
|[CDaoRecordset::GetDefaultDBName](../Topic/CDaoRecordset::GetDefaultDBName.md)|Gibt den Namen der standardmäßigen Datenquelle zurück.|  
|[CDaoRecordset::GetDefaultSQL](../Topic/CDaoRecordset::GetDefaultSQL.md)|Aufgerufen, um die Zeichenfolge mit SQL abzurufen, um.|  
|[CDaoRecordset::GetEditMode](../Topic/CDaoRecordset::GetEditMode.md)|Gibt einen Wert zurück, der den Zustand der Bearbeitung für den aktuellen Datensatz angibt.|  
|[CDaoRecordset::GetFieldCount](../Topic/CDaoRecordset::GetFieldCount.md)|Gibt einen Wert zurück, der die Anzahl von Feldern in einem Recordset darstellt.|  
|[CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)|Gibt bestimmte Arten von Informationen über die Felder im Recordset zurück.|  
|[CDaoRecordset::GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CDaoRecordset::GetIndexCount](../Topic/CDaoRecordset::GetIndexCount.md)|Ruft die Anzahl der Indizes in einer zugrunde liegenden Tabelle ein Recordset ab.|  
|[CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)|Gibt verschiedene Arten von Informationen über einen Index zurück.|  
|[CDaoRecordset::GetLastModifiedBookmark](../Topic/CDaoRecordset::GetLastModifiedBookmark.md)|Wird verwendet, um den hinzugefügten oder aktualisierten Datensatz zuletzt zu bestimmen.|  
|[CDaoRecordset::GetLockingMode](../Topic/CDaoRecordset::GetLockingMode.md)|Gibt einen Wert zurück, der den Typ der Sperre angibt, die in Kraft während der Bearbeitung ist.|  
|[CDaoRecordset::GetName](../Topic/CDaoRecordset::GetName.md)|Gibt `CString` zurück, das den Namen des Recordsets enthält.|  
|[CDaoRecordset::GetParamValue](../Topic/CDaoRecordset::GetParamValue.md)|Ruft den aktuellen Wert des angegebenen Parameters ab, der im zugrunde liegenden DAOParameter\-Objekt gespeichert wird.|  
|[CDaoRecordset::GetPercentPosition](../Topic/CDaoRecordset::GetPercentPosition.md)|Gibt die Position des aktuellen Datensatzes als Prozentsatz der Gesamtanzahl der Datensätze zurück.|  
|[CDaoRecordset::GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Gibt die Anzahl der Datensätze zurück, die in einem Recordset\-Objekt zugegriffen werden.|  
|[CDaoRecordset::GetSQL](../Topic/CDaoRecordset::GetSQL.md)|Ruft die SQL\-Zeichenfolge ab, die verwendet wird, um Datensätze für das Recordset auszuwählen.|  
|[CDaoRecordset::GetType](../Topic/CDaoRecordset::GetType.md)|Aufgerufen, um den Typ eines Recordsets zu bestimmen: vom Typ Tabelle, vom Typ Dynaset oder vom Typ Momentaufnahme.|  
|[CDaoRecordset::GetValidationRule](../Topic/CDaoRecordset::GetValidationRule.md)|Gibt `CString` zurück, das den Wert enthält, der Daten überprüft, während er in ein Feld eingegeben wird.|  
|[CDaoRecordset::GetValidationText](../Topic/CDaoRecordset::GetValidationText.md)|Ruft den Text ab, der angezeigt wird, wenn eine Validierungsregel nicht erfüllt ist.|  
|[CDaoRecordset::IsBOF](../Topic/CDaoRecordset::IsBOF.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset vor dem ersten Datensatz platziert wurde.  Es gibt keinen aktuellen Datensatz.|  
|[CDaoRecordset::IsDeleted](../Topic/CDaoRecordset::IsDeleted.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset auf gelöschten Datensatz platziert wird.|  
|[CDaoRecordset::IsEOF](../Topic/CDaoRecordset::IsEOF.md)|Gibt Wert ungleich 0 zurück, wenn das Recordset hinter dem letzten Datensatz platziert wurde.  Es gibt keinen aktuellen Datensatz.|  
|[CDaoRecordset::IsFieldDirty](../Topic/CDaoRecordset::IsFieldDirty.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CDaoRecordset::IsFieldNull](../Topic/CDaoRecordset::IsFieldNull.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz NULL ist \(keinen Wert aufweist\).|  
|[CDaoRecordset::IsFieldNullable](../Topic/CDaoRecordset::IsFieldNullable.md)|Gibt Wert ungleich 0 zurück, wenn das angegebene Feld im aktuellen Datensatz festgelegt werden kann, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CDaoRecordset::IsOpen](../Topic/CDaoRecordset::IsOpen.md)|Gibt Wert ungleich 0 zurück, wenn [Geöffnet](../Topic/CDaoRecordset::Open.md) zuvor aufgerufen wurde.|  
|[CDaoRecordset::Move](../Topic/CDaoRecordset::Move.md)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen im aktuellen Datensatz in beide Richtungen.|  
|[CDaoRecordset::MoveFirst](../Topic/CDaoRecordset::MoveFirst.md)|Positioniert den aktuellen Datensatz auf dem ersten Datensatz des Recordsets.|  
|[CDaoRecordset::MoveLast](../Topic/CDaoRecordset::MoveLast.md)|Positioniert den aktuellen Datensatz auf dem letzten Datensatz des Recordsets.|  
|[CDaoRecordset::MoveNext](../Topic/CDaoRecordset::MoveNext.md)|Positioniert den aktuellen Datensatz des nächsten Datensatz des Recordsets.|  
|[CDaoRecordset::MovePrev](../Topic/CDaoRecordset::MovePrev.md)|Positioniert den aktuellen Datensatz des vorherigen Datensatz des Recordsets.|  
|[CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)|Erstellt ein neues Recordset aus einer Tabelle, einem Dynaset oder von einer Momentaufnahme.|  
|[CDaoRecordset::Requery](../Topic/CDaoRecordset::Requery.md)|Führt die Abfrage des Recordsets erneut aus, um die ausgewählten Datensätze zu aktualisieren.|  
|[CDaoRecordset::Seek](../Topic/CDaoRecordset::Seek.md)|Findet den Satz in einem Recordset indizierten vom Typ Tabellen\-Objekt, das die angegebenen Kriterien für den aktuellen Index erfüllt und macht, das den aktuellen Datensatz aufzeichnen.|  
|[CDaoRecordset::SetAbsolutePosition](../Topic/CDaoRecordset::SetAbsolutePosition.md)|Legt die Datensatznummer des aktuellen Datensatzes eines Recordset\-Objekts fest.|  
|[CDaoRecordset::SetBookmark](../Topic/CDaoRecordset::SetBookmark.md)|Positioniert das Recordset auf einem Datensatz, der das angegebene Lesezeichen enthält.|  
|[CDaoRecordset::SetCacheSize](../Topic/CDaoRecordset::SetCacheSize.md)|Legt einen Wert fest, der die Anzahl von Datensätzen in einem Recordset vom Typ Dynaset angibt, das aus einer ODBC\-Datenquelle enthält die lokal zwischengespeichert werden, Daten.|  
|[CDaoRecordset::SetCacheStart](../Topic/CDaoRecordset::SetCacheStart.md)|Legt einen Wert fest, der das Lesezeichen des ersten Datensatzes im zwischengespeichert werden Recordset angibt.|  
|[CDaoRecordset::SetCurrentIndex](../Topic/CDaoRecordset::SetCurrentIndex.md)|Aufgerufen, um einen Index in einem Recordset vom Typ Tabelle festzulegen.|  
|[CDaoRecordset::SetFieldDirty](../Topic/CDaoRecordset::SetFieldDirty.md)|Markiert das angegebene Feld im aktuellen Datensatz, wie geändert.|  
|[CDaoRecordset::SetFieldNull](../Topic/CDaoRecordset::SetFieldNull.md)|Legt den Wert des angegebenen Felds im aktuellen Datensatz fest, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CDaoRecordset::SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)|Legt den Wert eines Felds in einem Recordset.|  
|[CDaoRecordset::SetFieldValueNull](../Topic/CDaoRecordset::SetFieldValueNull.md)|Legt den Wert eines Felds in einem Recordset fest, um ungültig zu machen.  \(keinen Wert aufweist\).|  
|[CDaoRecordset::SetLockingMode](../Topic/CDaoRecordset::SetLockingMode.md)|Legt einen Wert fest, der den Typ der Sperre angibt, die während der Bearbeitung zu bewerkstelligen.|  
|[CDaoRecordset::SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)|Legt den aktuellen Wert des angegebenen Parameters fest, der im zugrunde liegenden DAOParameter\-Objekt gespeichert wird|  
|[CDaoRecordset::SetParamValueNull](../Topic/CDaoRecordset::SetParamValueNull.md)|Legt den aktuellen Wert des angegebenen Parameters fest, um ungültig zu machen \(keinen Wert aufweist\).|  
|[CDaoRecordset::SetPercentPosition](../Topic/CDaoRecordset::SetPercentPosition.md)|Legt die Position des aktuellen Datensatzes zu einem Speicherort entspricht einem Prozentsatz der Gesamtanzahl der Datensätze in einem Recordset.|  
|[CDaoRecordset::Update](../Topic/CDaoRecordset::Update.md)|Schließt einen `AddNew` oder **Edit** Vorgang durch Speichern der neuen oder geänderten Daten in der Datenquelle.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CDaoRecordset::m\_bCheckCacheForDirtyFields](../Topic/CDaoRecordset::m_bCheckCacheForDirtyFields.md)|Enthält ein Flag, das angibt, ob Felder automatisch markiert werden, wie geändert.|  
|[CDaoRecordset::m\_nFields](../Topic/CDaoRecordset::m_nFields.md)|Enthält die Anzahl der Felddatenmember in der Recordset\-Klasse und die Anzahl der Spalten ausgewählt durch das Recordset aus der Datenquelle.|  
|[CDaoRecordset::m\_nParams](../Topic/CDaoRecordset::m_nParams.md)|Enthält die Anzahl der Parameterdatenmember in der Recordset\-Klasse \- die Anzahl von Parametern, die mit der Abfrage des Recordsets übergeben werden|  
|[CDaoRecordset::m\_pDAORecordset](../Topic/CDaoRecordset::m_pDAORecordset.md)|Ein Zeiger auf die zugrunde liegenden DAO\-Schnittstelle das Recordset\-Objekt.|  
|[CDaoRecordset::m\_pDatabase](../Topic/CDaoRecordset::m_pDatabase.md)|Quelldatenbank für dieses Resultset.  Enthält einen Zeiger auf einen [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)\-Objekt.|  
|[CDaoRecordset::m\_strFilter](../Topic/CDaoRecordset::m_strFilter.md)|Enthält eine Zeichenfolge, die verwendet wird, um eine Anweisung SQL **WHERE** zu erstellen.|  
|[CDaoRecordset::m\_strSort](../Topic/CDaoRecordset::m_strSort.md)|Enthält eine Zeichenfolge, die verwendet wird, um eine Anweisung SQL **ORDER BY** zu erstellen.|  
  
## Hinweise  
 Bei diesen als "Recordsets," sind `CDaoRecordset`\-Objekte in den folgenden drei Formen verfügbar:  
  
-   Recordset vom Typ Tabellen stellen eine Basistabelle dar, die Sie verwenden können, um Datensätze aus einer einzelnen Datenbanktabelle zu überprüfen, hinzuzufügen, zu ändern oder zu löschen.  
  
-   Recordsets vom Typ Dynaset sind das Ergebnis einer Abfrage, die aktualisierbare Datensätze haben kann.  Diese Recordsets sind eine Gruppe von Datensätzen, die Sie verwenden können, um Datensätze aus einer Tabelle oder Tabellen der zugrunde liegenden Datenbank sicherzustellen, hinzuzufügen, zu ändern oder zu löschen.  Recordsets vom Typ Dynaset können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten.  
  
-   Recordsets vom Typ Momentaufnahme sind eine statische Kopie Gruppe von Datensätzen, die Sie verwenden können, um Daten zu suchen oder Berichte zu generieren.  Diese Felder können Recordsets, aus einer oder mehreren Tabellen in einer Datenbank enthalten jedoch können nicht aktualisiert werden.  
  
 Jedes Formular des Recordsets stellt korrigierten Gruppe von Datensätzen dar, wenn das Recordset geöffnet ist.  Wenn Sie zu einem Datensatz in einem Recordset vom Typ Tabelle oder in einem Recordset vom Typ Dynaset wechseln, gibt es die Änderungen, die am Datensatz vorgenommen werden, nachdem das Recordset, entweder durch andere Benutzer oder von anderen Recordsets in der Anwendung geöffnet wird.  \(Ein Recordset vom Typ Momentaufnahme kann nicht aktualisiert werden.\) Sie können `CDaoRecordset` direkt verwenden oder eine anwendungsspezifische Recordset\-Klasse von `CDaoRecordset` berechnen.  Sie können anschließend folgende Aktionen durchführen:  
  
-   Bildlauf durch die Datensätze.  
  
-   Legen Sie einen Index fest und suchen Sie schnell nach Datensätzen mit [Suche](../Topic/CDaoRecordset::Seek.md) \(nur Recordset vom Typ Tabellen\).  
  
-   Suchen Sie Datensätze auf Grundlage einen Zeichenfolgenvergleich: "\<", "\<\=", "\=", "\>\=" oder "\>" \(und Recordsets vom Typ Dynaset vom Typ Momentaufnahme\).  
  
-   Aktualisieren Sie die Datensätze und geben Sie ein Sperrverhalten an \(außer Recordsets vom Typ Momentaufnahme\).  
  
-   Filtern Sie das Recordset, um einzuschränken, das Datensätze es von denen auswählen, die in der Datenquelle verfügbar sind.  
  
-   Sortieren das Recordset.  
  
-   Parametrisieren Sie das Recordset, um seine Auswahl mit den Informationen anzupassen, die erst zur Laufzeit bekannt sind.  
  
 Klassifizieren Sie `CDaoRecordset` stellt eine Schnittstelle, die zu der der \- Klasse `CRecordset` ähnelt.  Der Hauptunterschied liegt darin, dass Klasse `CDaoRecordset` auf Daten über ein Datenzugriffsobjekt \(DAO\) anhand OLE zugreift.  Klasse `CRecordset` greift auf das DBMS von Open Database Connectivity \(ODBC\) und einen ODBC\-Treiber für dieses DBMS zu.  
  
> [!NOTE]
>  Die DAO\-Datenbankklassen sind von den MFC\-Datenbankklassen auf Grundlage Open Database Connectivity \(ODBC\) unterschiedlich.  Alle DAO\-Datenbankklassen\-Namen haben das Präfix "CDao".  Sie können auf ODBC\-Datenquellen mit den DAO\-Klassen noch zugreifen; DAO\-Klassen bieten im Allgemeinen überlegene Funktionen, da sie an Microsoft Jet\-Datenbankmodul spezifisch sind.  
  
 Sie können entweder `CDaoRecordset` direkt verwenden oder eine Klasse von `CDaoRecordset` berechnen.  So fügen Sie eine Recordset\-Klasse in jedem Fall verwenden, eine Datenbank öffnen und ein Recordset\-Objekt, den Konstruktor übergibt ein Zeiger auf dem `CDaoDatabase`\-Objekt erstellen.  Sie können ein `CDaoRecordset`\-Objekt auch erstellen und lassen MFC ein temporäres Objekt `CDaoDatabase` für Sie erstellen.  Rufen Sie dann die [Geöffnet](../Topic/CDaoRecordset::Open.md)\-Memberfunktion des Recordsets auf und angeben, ob das Objekt ein Recordset vom Typ Tabelle, ein Recordset vom Typ Dynaset oder ein Recordset vom Typ Momentaufnahme ist.  Das Aufrufen von **Open** wählt Daten aus der Datenbank aus und ruft den ersten Datensatz ab.  
  
 Verwenden Sie die Memberfunktionen und Datenmember Objekts zum Bildlauf durch die Datensätze und lassen Sie an diese ausgeführt werden.  Die verfügbaren Vorgänge hängen davon ab, ob das Objekt ein Recordset vom Typ Tabelle, ein Recordset vom Typ Dynaset oder ein Recordset vom Typ Momentaufnahme ist und ob es aktualisierbar oder schreibgeschützt ist \- dies von der Funktion der Datenbank oder der Datenquelle der Open Database Connectivity \(ODBC\) abhängt.  So Datensätze aktualisieren, die möglicherweise geändert werden oder hinzugefügt, da der **Open** Aufruf, die [Fragen Sie erneut ab](../Topic/CDaoRecordset::Requery.md)\-Memberfunktion des Objekts aufrufen.  Rufen Sie die Memberfunktion des Objekts auf **Close** und das Objekt zerstört, wenn Sie mit ihr beenden.  
  
 `CDaoRecordset` verwendet DAO\-Datensatzfeldaustausch \(DFX\) zum Lesen und Aktualisieren von Datensatzfeldern durch typsichere C\+\+\-Member aus dem `CDaoRecordset` oder von `CDaoRecordset` zur Unterstützung von abgeleitete Klasse.  Sie können dynamische Binden von Spalten in einer Datenbank auch implementieren, ohne den DFX\-Mechanismus mithilfe [GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md) und [SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md) zu verwenden.  
  
 Weitere Informationen finden Sie im Thema "Recordset\-Objekt" in der DAO\-Hilfe.  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## Anforderungen  
 **Header:** afxdao.h  
  
## Siehe auch  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)