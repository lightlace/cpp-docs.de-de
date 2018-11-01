---
title: CDaoRecordset-Klasse
ms.date: 08/27/2018
f1_keywords:
- CDaoRecordset
- AFXDAO/CDaoRecordset
- AFXDAO/CDaoRecordset::CDaoRecordset
- AFXDAO/CDaoRecordset::AddNew
- AFXDAO/CDaoRecordset::CanAppend
- AFXDAO/CDaoRecordset::CanBookmark
- AFXDAO/CDaoRecordset::CancelUpdate
- AFXDAO/CDaoRecordset::CanRestart
- AFXDAO/CDaoRecordset::CanScroll
- AFXDAO/CDaoRecordset::CanTransact
- AFXDAO/CDaoRecordset::CanUpdate
- AFXDAO/CDaoRecordset::Close
- AFXDAO/CDaoRecordset::Delete
- AFXDAO/CDaoRecordset::DoFieldExchange
- AFXDAO/CDaoRecordset::Edit
- AFXDAO/CDaoRecordset::FillCache
- AFXDAO/CDaoRecordset::Find
- AFXDAO/CDaoRecordset::FindFirst
- AFXDAO/CDaoRecordset::FindLast
- AFXDAO/CDaoRecordset::FindNext
- AFXDAO/CDaoRecordset::FindPrev
- AFXDAO/CDaoRecordset::GetAbsolutePosition
- AFXDAO/CDaoRecordset::GetBookmark
- AFXDAO/CDaoRecordset::GetCacheSize
- AFXDAO/CDaoRecordset::GetCacheStart
- AFXDAO/CDaoRecordset::GetCurrentIndex
- AFXDAO/CDaoRecordset::GetDateCreated
- AFXDAO/CDaoRecordset::GetDateLastUpdated
- AFXDAO/CDaoRecordset::GetDefaultDBName
- AFXDAO/CDaoRecordset::GetDefaultSQL
- AFXDAO/CDaoRecordset::GetEditMode
- AFXDAO/CDaoRecordset::GetFieldCount
- AFXDAO/CDaoRecordset::GetFieldInfo
- AFXDAO/CDaoRecordset::GetFieldValue
- AFXDAO/CDaoRecordset::GetIndexCount
- AFXDAO/CDaoRecordset::GetIndexInfo
- AFXDAO/CDaoRecordset::GetLastModifiedBookmark
- AFXDAO/CDaoRecordset::GetLockingMode
- AFXDAO/CDaoRecordset::GetName
- AFXDAO/CDaoRecordset::GetParamValue
- AFXDAO/CDaoRecordset::GetPercentPosition
- AFXDAO/CDaoRecordset::GetRecordCount
- AFXDAO/CDaoRecordset::GetSQL
- AFXDAO/CDaoRecordset::GetType
- AFXDAO/CDaoRecordset::GetValidationRule
- AFXDAO/CDaoRecordset::GetValidationText
- AFXDAO/CDaoRecordset::IsBOF
- AFXDAO/CDaoRecordset::IsDeleted
- AFXDAO/CDaoRecordset::IsEOF
- AFXDAO/CDaoRecordset::IsFieldDirty
- AFXDAO/CDaoRecordset::IsFieldNull
- AFXDAO/CDaoRecordset::IsFieldNullable
- AFXDAO/CDaoRecordset::IsOpen
- AFXDAO/CDaoRecordset::Move
- AFXDAO/CDaoRecordset::MoveFirst
- AFXDAO/CDaoRecordset::MoveLast
- AFXDAO/CDaoRecordset::MoveNext
- AFXDAO/CDaoRecordset::MovePrev
- AFXDAO/CDaoRecordset::Open
- AFXDAO/CDaoRecordset::Requery
- AFXDAO/CDaoRecordset::Seek
- AFXDAO/CDaoRecordset::SetAbsolutePosition
- AFXDAO/CDaoRecordset::SetBookmark
- AFXDAO/CDaoRecordset::SetCacheSize
- AFXDAO/CDaoRecordset::SetCacheStart
- AFXDAO/CDaoRecordset::SetCurrentIndex
- AFXDAO/CDaoRecordset::SetFieldDirty
- AFXDAO/CDaoRecordset::SetFieldNull
- AFXDAO/CDaoRecordset::SetFieldValue
- AFXDAO/CDaoRecordset::SetFieldValueNull
- AFXDAO/CDaoRecordset::SetLockingMode
- AFXDAO/CDaoRecordset::SetParamValue
- AFXDAO/CDaoRecordset::SetParamValueNull
- AFXDAO/CDaoRecordset::SetPercentPosition
- AFXDAO/CDaoRecordset::Update
- AFXDAO/CDaoRecordset::m_bCheckCacheForDirtyFields
- AFXDAO/CDaoRecordset::m_nFields
- AFXDAO/CDaoRecordset::m_nParams
- AFXDAO/CDaoRecordset::m_pDAORecordset
- AFXDAO/CDaoRecordset::m_pDatabase
- AFXDAO/CDaoRecordset::m_strFilter
- AFXDAO/CDaoRecordset::m_strSort
helpviewer_keywords:
- CDaoRecordset [MFC], CDaoRecordset
- CDaoRecordset [MFC], AddNew
- CDaoRecordset [MFC], CanAppend
- CDaoRecordset [MFC], CanBookmark
- CDaoRecordset [MFC], CancelUpdate
- CDaoRecordset [MFC], CanRestart
- CDaoRecordset [MFC], CanScroll
- CDaoRecordset [MFC], CanTransact
- CDaoRecordset [MFC], CanUpdate
- CDaoRecordset [MFC], Close
- CDaoRecordset [MFC], Delete
- CDaoRecordset [MFC], DoFieldExchange
- CDaoRecordset [MFC], Edit
- CDaoRecordset [MFC], FillCache
- CDaoRecordset [MFC], Find
- CDaoRecordset [MFC], FindFirst
- CDaoRecordset [MFC], FindLast
- CDaoRecordset [MFC], FindNext
- CDaoRecordset [MFC], FindPrev
- CDaoRecordset [MFC], GetAbsolutePosition
- CDaoRecordset [MFC], GetBookmark
- CDaoRecordset [MFC], GetCacheSize
- CDaoRecordset [MFC], GetCacheStart
- CDaoRecordset [MFC], GetCurrentIndex
- CDaoRecordset [MFC], GetDateCreated
- CDaoRecordset [MFC], GetDateLastUpdated
- CDaoRecordset [MFC], GetDefaultDBName
- CDaoRecordset [MFC], GetDefaultSQL
- CDaoRecordset [MFC], GetEditMode
- CDaoRecordset [MFC], GetFieldCount
- CDaoRecordset [MFC], GetFieldInfo
- CDaoRecordset [MFC], GetFieldValue
- CDaoRecordset [MFC], GetIndexCount
- CDaoRecordset [MFC], GetIndexInfo
- CDaoRecordset [MFC], GetLastModifiedBookmark
- CDaoRecordset [MFC], GetLockingMode
- CDaoRecordset [MFC], GetName
- CDaoRecordset [MFC], GetParamValue
- CDaoRecordset [MFC], GetPercentPosition
- CDaoRecordset [MFC], GetRecordCount
- CDaoRecordset [MFC], GetSQL
- CDaoRecordset [MFC], GetType
- CDaoRecordset [MFC], GetValidationRule
- CDaoRecordset [MFC], GetValidationText
- CDaoRecordset [MFC], IsBOF
- CDaoRecordset [MFC], IsDeleted
- CDaoRecordset [MFC], IsEOF
- CDaoRecordset [MFC], IsFieldDirty
- CDaoRecordset [MFC], IsFieldNull
- CDaoRecordset [MFC], IsFieldNullable
- CDaoRecordset [MFC], IsOpen
- CDaoRecordset [MFC], Move
- CDaoRecordset [MFC], MoveFirst
- CDaoRecordset [MFC], MoveLast
- CDaoRecordset [MFC], MoveNext
- CDaoRecordset [MFC], MovePrev
- CDaoRecordset [MFC], Open
- CDaoRecordset [MFC], Requery
- CDaoRecordset [MFC], Seek
- CDaoRecordset [MFC], SetAbsolutePosition
- CDaoRecordset [MFC], SetBookmark
- CDaoRecordset [MFC], SetCacheSize
- CDaoRecordset [MFC], SetCacheStart
- CDaoRecordset [MFC], SetCurrentIndex
- CDaoRecordset [MFC], SetFieldDirty
- CDaoRecordset [MFC], SetFieldNull
- CDaoRecordset [MFC], SetFieldValue
- CDaoRecordset [MFC], SetFieldValueNull
- CDaoRecordset [MFC], SetLockingMode
- CDaoRecordset [MFC], SetParamValue
- CDaoRecordset [MFC], SetParamValueNull
- CDaoRecordset [MFC], SetPercentPosition
- CDaoRecordset [MFC], Update
- CDaoRecordset [MFC], m_bCheckCacheForDirtyFields
- CDaoRecordset [MFC], m_nFields
- CDaoRecordset [MFC], m_nParams
- CDaoRecordset [MFC], m_pDAORecordset
- CDaoRecordset [MFC], m_pDatabase
- CDaoRecordset [MFC], m_strFilter
- CDaoRecordset [MFC], m_strSort
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
ms.openlocfilehash: 6b3e3fac575d6a1308a9f61b3bf827d76785e94d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639323"
---
# <a name="cdaorecordset-class"></a>CDaoRecordset-Klasse

Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.

## <a name="syntax"></a>Syntax

```
class CDaoRecordset : public CObject
```

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung|
|----------|-----------------|
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Erstellt ein `CDaoRecordset`-Objekt.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[AddNew](#addnew)|Bereitet zum Hinzufügen eines neuen Eintrags. Rufen Sie [Update](#update) das Hinzufügen abgeschlossen.|
|[CDaoRecordset::CanAppend](#canappend)|Gibt ungleich NULL, wenn das Recordset über neue Datensätze hinzugefügt werden können die [AddNew](#addnew) Member-Funktion.|
|[CDaoRecordset::CanBookmark](#canbookmark)|Gibt, die ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.|
|[CDaoRecordset::CanRestart](#canrestart)|Ungleich NULL zurück, wenn [Requery](#requery) aufgerufen werden, um die Abfrage des Recordsets erneut ausführen.|
|[CDaoRecordset::CanScroll](#canscroll)|Gibt, die ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|
|[CDaoRecordset::CanTransact](#cantransact)|Gibt, die ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|
|[CDaoRecordset::CanUpdate](#canupdate)|Gibt ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|
|[CDaoRecordset::Close](#close)|Schließt das Recordset.|
|[CDaoRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang scrollen.|
|[CDaoRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implements-DAO-Datensatzfeldaustausch (DFX).|
|[CDaoRecordset::Edit](#edit)|Bereitet für Änderungen an den aktuellen Datensatz. Rufen Sie `Update` um die Bearbeitung abzuschließen.|
|[FillCache](#fillcache)|Füllt den gesamten oder einen Teil des lokalen Cache für ein Recordsetobjekt, das Daten aus einer ODBC-Datenquelle enthält.|
|[CDaoRecordset::Find](#find)|Sucht das erste, Next, letzten oder vorherigen Speicherort einer bestimmten Zeichenfolge in einem Typ Dynaset-Recordset, das erfüllt werden, den angegebenen Kriterien und macht, die zum aktuellen Datensatz.|
|[CDaoRecordset::FindFirst](#findfirst)|Sucht den ersten Datensatz in ein Dynaset oder Snapshot-Type-Recordset, das erfüllt werden, den angegebenen Kriterien und macht diesen des aktuellen Datensatzes an.|
|[CDaoRecordset::FindLast](#findlast)|Sucht den letzten Datensatz in ein Dynaset oder Snapshot-Type-Recordset, das erfüllt werden, den angegebenen Kriterien und macht diesen des aktuellen Datensatzes an.|
|[CDaoRecordset::FindNext](#findnext)|Sucht den nächsten Datensatz in ein Dynaset oder Snapshot-Type-Recordset, das erfüllt werden, den angegebenen Kriterien und macht diesen des aktuellen Datensatzes an.|
|[CDaoRecordset::FindPrev](#findprev)|Sucht nach dem vorherigen Datensatz in ein Dynaset oder Snapshot-Type-Recordset, das erfüllt werden, den angegebenen Kriterien und macht, die zum aktuellen Datensatz.|
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|Gibt die Nummer des aktuellen Datensatzes einem Recordset-Objekt zurück.|
|[CDaoRecordset:: GetBookmark](#getbookmark)|Gibt einen Wert, der das Lesezeichen für einen Datensatz darstellt.|
|[CDaoRecordset::GetCacheSize](#getcachesize)|Gibt einen Wert, der angibt, die Anzahl der Datensätze in einem Recordset Dynaset-Typ, die mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.|
|[CDaoRecordset::GetCacheStart](#getcachestart)|Gibt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden.|
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Gibt eine `CString` für eine indizierte Tabelle – verwendet mit dem Namen des Indexes die vor kurzem `CDaoRecordset`.|
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit der zugrunde liegenden Basistabelle eine `CDaoRecordset` Objekt erstellt wurde|
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum und Uhrzeit der letzten Änderungen an den Entwurf einer zugrunde liegenden Basistabelle eine `CDaoRecordset` Objekt.|
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Gibt den Namen der Standard-Datenquelle.|
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, rufen Sie die Standard-SQL-Zeichenfolge ausgeführt wird.|
|[CDaoRecordset::GetEditMode](#geteditmode)|Gibt einen Wert, der den Status der Bearbeiten für den aktuellen Datensatz angibt.|
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in einem Recordset darstellt.|
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Gibt bestimmte Arten von Informationen zu den Feldern im Recordset zurück.|
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|
|[CDaoRecordset::GetIndexCount](#getindexcount)|Ruft die Anzahl der Indizes in einer Tabelle mit dem zugrunde liegenden Recordset ab.|
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Gibt die verschiedenen Arten von Informationen zu einem Index zurück.|
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Verwendet, um zu bestimmen, die am häufigsten vor kurzem hinzugefügt oder Datensatz aktualisiert.|
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Gibt einen Wert, der den Typ der Sperre, der während der Bearbeitung aktiviert ist angibt.|
|[CDaoRecordset::GetName](#getname)|Gibt eine `CString` mit dem Namen des Recordset-Objekts.|
|[CDaoRecordset::GetParamValue](#getparamvalue)|Ruft den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter-Objekt gespeichert.|
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|Gibt die Position des aktuellen Datensatzes als Prozentsatz der Gesamtanzahl von Datensätzen zurück.|
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze, die auf die in einem Recordset-Objekt zurück.|
|[CDaoRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset.|
|[CDaoRecordset::GetType](#gettype)|Wird aufgerufen, um den Typ eines Recordset-Objekts zu ermitteln: Tabellentyp, Dynaset eines assistentartigen oder Snapshot-Typ.|
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Gibt eine `CString` mit dem Wert, der Daten überprüft werden, während sie in ein Feld eingegeben wird.|
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Ruft den Text ab, der angezeigt wird, wenn eine Validierungsregel nicht erfüllt ist.|
|[CDaoRecordset::IsBOF](#isbof)|Gibt, die ungleich NULL, wenn das Recordset vor dem ersten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.|
|[CDaoRecordset::IsDeleted](#isdeleted)|Gibt, die ungleich NULL, wenn das Recordset in einem gelöschten Datensatz positioniert ist.|
|[CDaoRecordset::IsEOF](#iseof)|Gibt, die ungleich NULL, wenn das Recordset nach dem letzten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.|
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Gibt, die ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Gibt, die ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz (mit keinen Wert) Null ist.|
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz auf Null festgelegt werden kann (mit keinen Wert) zurück.|
|[CDaoRecordset::IsOpen](#isopen)|Ungleich NULL zurück, wenn [öffnen](#open) wurde zuvor aufgerufen.|
|[CDaoRecordset::Move](#move)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|
|[CDaoRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz für den ersten Datensatz im Recordset.|
|[CDaoRecordset::MoveLast](#movelast)|Positioniert den aktuellen Datensatz für den letzten Datensatz im Recordset.|
|[CDaoRecordset::MoveNext](#movenext)|Den aktuellen Datensatz positioniert den nächsten Datensatz im Recordset.|
|[CDaoRecordset::MovePrev](#moveprev)|Den aktuellen Datensatz positioniert den vorherigen Datensatz im Recordset.|
|[CDaoRecordset:: Open](#open)|Erstellt einen neuen Datensatz aus einer Tabelle, die Dynaset oder die Momentaufnahme an.|
|[CDaoRecordset::Requery](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|
|[CDaoRecordset::Seek](#seek)|Sucht nach dem Datensatz in einem indizierten Tabelle Typ Recordset-Objekt, das für den aktuellen Index und macht, die zum aktuellen Datensatz die angegebenen Kriterien erfüllt.|
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Legt die Nummer des aktuellen Datensatzes einem Recordset-Objekt fest.|
|[CDaoRecordset:: SetBookmark](#setbookmark)|Positioniert das Recordset einen Datensatz mit dem angegebenen Lesezeichen.|
|[CDaoRecordset:: SetCacheSize](#setcachesize)|Legt einen Wert, der angibt, die Anzahl der Datensätze in einem Recordset Dynaset-Typ, die mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.|
|[CDaoRecordset:: SetCacheStart](#setcachestart)|Legt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden.|
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|Wird aufgerufen, um einen Index für ein Recordset-Tabelle vom Typ festzulegen.|
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz an, als geändert.|
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds in den aktuellen Datensatz auf Null (kein Wert mit) fest.|
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Legt den Wert eines Felds in einem Recordset fest.|
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Legt den Wert eines Felds in einem Recordset auf Null fest. (Wenn kein Wert).|
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Legt einen Wert, der den Typ der Sperren, um während der Bearbeitung vollzogen angibt.|
|[CDaoRecordset::SetParamValue](#setparamvalue)|Stellt den aktuellen Wert des angegebenen Parameters in der zugrunde liegende Objekt DAOParameter gespeichert|
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Legt den aktuellen Wert des angegebenen Parameters auf Null (kein Wert mit) fest.|
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|Legt die Position des aktuellen Datensatzes an einen Speicherort für einen Prozentsatz der Gesamtzahl der Datensätze in einem Recordset fest.|
|[CDaoRecordset::Update](#update)|Schließt eine `AddNew` oder `Edit` Vorgang, durch die neuen oder bearbeiteten Daten speichern, in der Datenquelle.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[CDaoRecordset:: M_bcheckcachefordirtyfields](#m_bcheckcachefordirtyfields)|Enthält ein Flag, das angibt, ob Felder automatisch als geändert markiert werden.|
|[CDaoRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.|
|[CDaoRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in die Recordset-Klasse, die Anzahl der Parameter zu übergeben, mit der Abfrage des Recordsets|
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Ein Zeiger auf die DAO-Schnittstelle, die zugrunde liegende des Recordset-Objekts.|
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Die Quelldatenbank für dieses Resultset. Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.|
|[CDaoRecordset::m_strFilter](#m_strfilter)|Enthält eine Zeichenfolge verwendet, um eine SQL-Konstrukt **, in denen** Anweisung.|
|[CDaoRecordset::m_strSort](#m_strsort)|Enthält eine Zeichenfolge verwendet, um eine SQL-Konstrukt **ORDER BY** Anweisung.|

## <a name="remarks"></a>Hinweise

Bekannt als "Recordsets," `CDaoRecordset` Objekte sind in den folgenden drei Formen verfügbar:

- Recordsets vom Typ Tabelle stellen eine Basistabelle, die Sie verwenden können, zu überprüfen, hinzufügen, ändern oder Löschen von Datensätzen in einer einzelnen Datenbanktabelle dar.

- Recordsets vom Typ Dynaset sind das Ergebnis einer Abfrage, die aktualisierbare Datensätze haben kann. Diese Recordsets sind eine Gruppe von Datensätzen, die Sie zum Überprüfen, hinzufügen, ändern oder Löschen von Datensätzen in einer zugrunde liegenden Datenbanktabelle oder-Tabellen verwenden können. Recordsets vom Typ Dynaset können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten.

- Recordsets vom Typ Snapshot sind eine statische Kopie einer Gruppe von Datensätzen, die Sie zum Suchen von Daten oder zum Generieren von Berichten verwenden können. Diese Recordsets können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten, aber es kann nicht aktualisiert werden.

Jedes Formular des Recordsets stellt eine Gruppe von Datensätzen, die behoben werden, zu dem Zeitpunkt, die das Recordset geöffnet wird. Wenn Sie einen Bildlauf zu einem Datensatz in einem Recordset-Tabelle vom Typ oder einem Recordset vom Typ Dynaset durchführen, prüfen, ob Änderungen am Datensatz vorgenommen werden, nachdem das Recordset, von anderen Benutzern oder von anderen Recordsets in Ihrer Anwendung geöffnet wird. (Ein Recordset Momentaufnahme vom Typ kann nicht aktualisiert werden.) Sie können `CDaoRecordset` direkt oder leiten Sie eine anwendungsspezifische Recordset-Klasse von `CDaoRecordset`. Anschließend können Sie:

- Durch die Datensätze scrollen.

- Legen Sie einen Index, und suchen Sie kurz nach Einträgen mit [Seek](#seek) (nur Recordsets vom Typ Tabelle).

- Suchen nach Datensätzen, die auf Basis eines Wertevergleichs der Zeichenfolge: "<","\<=", "=", "> =", oder ">" (Typ Dynaset und Recordsets vom Typ Snapshot).

- Aktualisieren Sie der Datensätze, und geben Sie einen Sperrmodus (mit Ausnahme der Recordsets vom Typ Snapshot).

- Filtern Sie das Recordset aus, um die Datensätze zu beschränken, für die Datenquelle aus den verfügbaren ausgewählt.

- Sortieren Sie das Recordset.

- Parametrisieren Sie das Recordset aus, um die Auswahl mit Informationen, die nicht bis zur Laufzeit bekannt anzupassen.

Klasse `CDaoRecordset` stellt eine Schnittstelle, die der Klasse ähnelt `CRecordset`. Der Hauptunterschied besteht darin, Klasse `CDaoRecordset` greift auf Daten über einen (Datenzugriffsobjekt) basierend auf OLE. Klasse `CRecordset` greift auf das DBMS über Open Database Connectivity (ODBC) und einem ODBC-Treiber für dieses DBMS verwaltet.

> [!NOTE]
> Die DAO-Datenbankklassen unterscheiden sich von der MFC-Datenbankklassen in Bezug auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können weiterhin den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; die DAO-Klassen bieten im Allgemeinen überlegene Funktionen, da sie für die Microsoft Jet-Datenbank-Engine spezifisch sind.

Sie können entweder `CDaoRecordset` direkt oder leiten eine Klasse von `CDaoRecordset`. Um eine Recordset-Klasse in beiden Fällen zu verwenden, öffnen Sie eine Datenbank aus, und erstellen Sie ein Recordsetobjekt, und übergeben dem Konstruktor einen Zeiger auf Ihre `CDaoDatabase` Objekt. Sie können auch erstellen eine `CDaoRecordset` Objekts, sodass Sie die MFC-Erstellen eines temporären `CDaoDatabase` -Objekt für Sie. Rufen Sie dann der Recordsets [öffnen](#open) Member-Funktion, die angibt, ob das Objekt ein Tabellentyp Recordset, ein Recordset Dynaset vom Typ oder ein Recordset Momentaufnahme vom Typ ist. Aufrufen von `Open` wählt Daten aus der Datenbank aus, und ruft den ersten Datensatz.

Verwenden Sie die Member des Objekts Member-Funktionen und Daten, um durch die Datensätze scrollen und auf ihnen ausgeführt werden. Die verfügbaren Vorgänge ist davon abhängig, ob das Objekt ein Tabellentyp Recordset, ein Recordset Dynaset vom Typ oder ein Recordset Momentaufnahme vom Typ ist, und gibt an, ob es sich um aktualisierbar oder schreibgeschützt ist — dies hängt von der Funktion der Datenbank oder der Open Database Connectivity (ODBC) die Datenquelle. Um Datensätze zu aktualisieren, die möglicherweise wurde geändert oder hinzugefügt werden, da die `Open` aufzurufen, rufen Sie des Objekts [Requery](#requery) Member-Funktion. Aufrufen des Objekts `Close` Member Funktion, und das Objekt zerstört, wenn Sie damit fertig sind.

`CDaoRecordset` DAO-Datensatzfeldaustausch (DFX) zur Unterstützung von lesen und Aktualisieren von Datensatzfeldern verwendet, durch typsichere C++ Mitglieder Ihrer `CDaoRecordset` oder `CDaoRecordset`-abgeleitete Klasse. Sie können auch dynamische Bindung von Spalten in einer Datenbank implementieren, ohne mit DFX Mechanismus [GetFieldValue](#getfieldvalue) und [SetFieldValue](#setfieldvalue).

Verwandte Informationen finden Sie im Thema "Recordset-Objekts" in-DAO-Hilfe.

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CDaoRecordset`

## <a name="requirements"></a>Anforderungen

**Header:** afxdao.h

##  <a name="addnew"></a>  AddNew

Rufen Sie diese Memberfunktion zum Hinzufügen eines neuen Datensatzes zu einem Recordset-Tabellentyp oder Dynaset.

```
virtual void AddNew();
```

### <a name="remarks"></a>Hinweise

Der Felder, die ursprünglich Null sind. (Null, in der datenbankterminologie bedeutet "kein Wert having" und entspricht nicht der NULL-Wert in C++.) Um den Vorgang abzuschließen, müssen Sie den Aufrufen der [Update](#update) Member-Funktion. `Update` Speichert die Änderungen an die Datenquelle an.

> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten und navigieren Sie zu einem anderen Datensatz ohne `Update`, Ihre Änderungen gehen verloren, ohne Warnung.

Wenn Sie einen Datensatz durch den Aufruf zu einem Recordset vom Typ Dynaset hinzufügen [AddNew](#addnew), wird von der Datensatz im Recordset angezeigt und enthalten in der zugrunde liegenden Tabelle, in denen es angezeigt, auf eine neue wird `CDaoRecordset` Objekte.

Die Position des neuen Datensatzes hängt von den Typ des Recordsets:

- In der Art eines Dynaset ist Recordset, an der neue Datensatz eingefügt wird nicht garantiert. Dieses Verhalten ist mit Microsoft Jet 3.0 aus Gründen der Leistung und Parallelität. Wenn Ihr Ziel ist es, die neu hinzugefügten Datensatz den aktuellen Datensatz, erhalten Sie das Lesezeichen des letzten Datensatzes geändert und in dieses Lesezeichen verschieben:

[!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]

- In einem Recordset Table-Typ, der für die ein Index angegeben wurde, werden die Datensätze entsprechend ihrer Position in der Sortierreihenfolge zurückgegeben. Wenn kein Index angegeben wurde, werden neue Einträge am Ende des Recordset-Objekts zurückgegeben.

Der Datensatz, der aktuell, bevor Sie verwendet war `AddNew` bleibt der aktuelle. Wenn Sie den neuen Datensatz aktualisieren möchten, und das Recordset Lesezeichen Aufruf unterstützt [SetBookmark](#setbookmark) auf das Lesezeichen, das durch die Einstellung der Eigenschaft der letzten Änderung des zugrunde liegenden DAO-Recordset-Objekts identifiziert. Auf diese Weise ist nützlich zum Bestimmen des Werts für Leistungsindikator (automatisch inkrementierten) Felder in einem Datensatz hinzugefügt. Weitere Informationen finden Sie unter [GetLastModifiedBookmark](#getlastmodifiedbookmark).

Wenn die Datenbank Transaktionen unterstützt, können Sie machen Ihre `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Beachten Sie, die Sie aufrufen sollten [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) vor dem Aufruf `AddNew`.

Es ist nicht zulässig, rufen Sie `AddNew` für ein Recordset, deren [öffnen](#open) Memberfunktion nicht aufgerufen wurde. Ein `CDaoException` wird ausgelöst, wenn Sie aufrufen `AddNew` für ein Recordset, das kann nicht angefügt werden. Sie können bestimmen, ob das Recordset aktualisierbar, durch den Aufruf ist [CanAppend](#canappend).

Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld geändert automatisch, sodass Sie nur selten aufrufen, müssen [SetFieldDirty](#setfielddirty) selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten werden explizit aktualisiert oder eingefügt werden unabhängig davon, ob welcher Wert im Feld-Datenmember ist. Der DFX-Mechanismus verwendet auch die Verwendung von **UNECHTE NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss explizit das Feld geändert festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Feld Prüfung.

> [!NOTE]
> Wenn Datensätze doppelt gepufferte sind (d. h. automatische Feld zu überprüfen ist aktiviert), Aufrufen von `CancelUpdate` stellen die Membervariablen auf die Werte, die sie zuvor `AddNew` oder `Edit` aufgerufen wurde.

Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate-Methode", "Eigenschaft" LastModified "und"EditMode-Eigenschaft"in-DAO-Hilfe.

##  <a name="canappend"></a>  CDaoRecordset::CanAppend

Rufen Sie diese Memberfunktion, um festzustellen, ob das zuvor geöffnete Recordset Sie neue Datensätze hinzufügen, durch den Aufruf kann die [AddNew](#addnew) Member-Funktion.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset ermöglicht neue Datensätze hinzufügen; andernfalls 0. `CanAppend` Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem Thema "Fügen Sie der Methode" in-DAO-Hilfe.

##  <a name="canbookmark"></a>  CDaoRecordset::CanBookmark

Rufen Sie diese Memberfunktion, um festzustellen, ob das zuvor geöffnete Recordset, die Sie einzeln Datensätze, die mithilfe von Lesezeichen markieren kann.

```
BOOL CanBookmark();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset Lesezeichen, andernfalls 0 unterstützt.

### <a name="remarks"></a>Hinweise

Bei Verwendung von Recordsets basiert vollständig auf der Microsoft Jet-Datenbank-Engine-Tabellen können außer bei Momentaufnahme-Type-Recordsets als Bildlauf von Vorwärts-Recordsets Lesezeichen verwendet werden. Anderer Produkte (externe ODBC-Datenquellen) unterstützen möglicherweise keine Lesezeichen.

Verwandte Informationen finden Sie im Thema "Lesezeichenfähig Property" in-DAO-Hilfe.

##  <a name="cancelupdate"></a>  CDaoRecordset::CancelUpdate

Die `CancelUpdate` Memberfunktion bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.

```
virtual void CancelUpdate();
```

### <a name="remarks"></a>Hinweise

Wenn eine Anwendung ruft z. B. die `Edit` oder `AddNew` Member-Funktion und nicht aufgerufen [Update](#update), `CancelUpdate` verwirft alle Änderungen, die nach `Edit` oder `AddNew` aufgerufen wurde.

> [!NOTE]
>  Wenn Datensätze doppelt gepufferte sind (d. h. automatische Feld zu überprüfen ist aktiviert), Aufrufen von `CancelUpdate` stellen die Membervariablen auf die Werte, die sie zuvor `AddNew` oder `Edit` aufgerufen wurde.

Es ist keine `Edit` oder `AddNew` Vorgang Ausstehend "," `CancelUpdate` bewirkt, dass MFC eine Ausnahme ausgelöst. Rufen Sie die [GetEditMode](#geteditmode) Memberfunktion, um zu bestimmen, ob es ein ausstehender Vorgang, der abgebrochen werden kann.

Weitere Informationen finden Sie unter dem Thema "CancelUpdate-Methode" in-DAO-Hilfe.

##  <a name="canrestart"></a>  CDaoRecordset::CanRestart

Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset ermöglicht das Neustarten der Abfrage (Wenn Sie die Datensätze zu aktualisieren) durch Aufrufen der `Requery` Member-Funktion.

```
BOOL CanRestart();
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich NULL `Requery` aufgerufen werden, um die Ausführung des Recordsets Abfrage erneut aus, andernfalls 0.

### <a name="remarks"></a>Hinweise

Recordsets vom Typ Tabelle unterstützen keine `Requery`.

Wenn `Requery` wird nicht unterstützt wird, rufen [schließen](#close) dann [öffnen](#open) zum Aktualisieren der Daten. Rufen Sie `Requery` zum Aktualisieren von einem Recordset-Objekt zugrunde liegende Parameter-Abfrage nach dem die Parameterwerte geändert wurden.

Verwandte Informationen finden Sie im Thema "Neu gestartet werden können Eigenschaft" in-DAO-Hilfe.

##  <a name="canscroll"></a>  CDaoRecordset::CanScroll

Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset ermöglicht das Durchführen eines Bildlaufs.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze, andernfalls 0 durchführen können.

### <a name="remarks"></a>Hinweise

Wenn Sie aufrufen [öffnen](#open) mit `dbForwardOnly`, das Recordset kann nur vorwärts scrollen.

Weitere Informationen finden Sie unter im Thema "Positionierung der aktuellen Zeiger mit DAO" in-DAO-Hilfe.

##  <a name="cantransact"></a>  CDaoRecordset::CanTransact

Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset Transaktionen ermöglicht.

```
BOOL CanTransact();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn die zugrunde liegenden Datenquelle unterstützt die Transaktionen, andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwandte Informationen finden Sie im Thema "Transaktionen Property" in-DAO-Hilfe.

##  <a name="canupdate"></a>  CDaoRecordset::CanUpdate

Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset aktualisiert werden kann.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset aktualisiert werden kann (hinzufügen, aktualisieren und Löschen von Datensätzen), andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Recordset kann schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist, oder wenn Sie angegeben haben `dbReadOnly` für *nOptions* beim Aufruf [öffnen](#open) für das Recordset.

Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "-Methode Delete", "Update-Methode" und "Aktualisierbare Property" in-DAO-Hilfe.

##  <a name="cdaorecordset"></a>  CDaoRecordset::CDaoRecordset

Erstellt ein `CDaoRecordset`-Objekt.

```
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parameter

*pDatabase*<br/>
Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt oder den Wert NULL. Falls ungleich NULL und `CDaoDatabase` des Objekts `Open` Memberfunktion nicht aufgerufen wurde, um es an die Datenquelle zu verbinden, versucht Sie, dass das Recordset es für Sie öffnen, während eine eigene [öffnen](#open) aufrufen. Wenn Sie NULL übergeben eine `CDaoDatabase` Objekt erstellt und verbunden sind, Sie verwenden die Datenquelleninformationen, die Sie angegeben werden, wenn Sie vom Recordset-Klasse abgeleitet ist `CDaoRecordset`.

### <a name="remarks"></a>Hinweise

Sie können entweder `CDaoRecordset` direkt oder leiten Sie eine anwendungsspezifische Klasse von `CDaoRecordset`. Klassen-Assistenten können Sie die Recordset-Klassen abgeleitet werden.

> [!NOTE]
>  Bei der Ableitung einer `CDaoRecordset` Klasse, die Ihre abgeleitete Klasse muss seinen eigenen Konstruktor bereitstellen. Rufen Sie im Konstruktor einer abgeleiteten Klasse den Konstruktor `CDaoRecordset::CDaoRecordset`, die entsprechenden Parameter zusammen an sie übergibt.

Übergeben Sie NULL an Ihre recordsetkonstruktor haben eine `CDaoDatabase` Objekt erstellt und für Sie automatisch verbunden. Dies ist eine hilfreiche Abkürzung, die nicht erforderlich ist, erstellen und verbinden Sie ein `CDaoDatabase` Objekt vor dem Erstellen eines Recordsets. Wenn die `CDaoDatabase` Objekt ist nicht geöffnet ist, eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt wird auch für Sie, die verwendet Standard-Arbeitsbereich erstellt werden. Weitere Informationen finden Sie unter [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).

##  <a name="close"></a>  CDaoRecordset::Close

Schließen einer `CDaoRecordset` Objekt entfernt es aus der Auflistung der geöffneten Recordsets in der zugehörigen Datenbank.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Da `Close` nicht zerstört die `CDaoRecordset` Objekt ist, können Sie das Objekt durch Aufrufen wiederverwenden `Open` auf die gleiche Datenquelle oder eine andere Datenquelle.

Alle ausstehenden [AddNew](#addnew) oder [bearbeiten](#edit) -Anweisungen abgebrochen und alle ausstehenden Transaktionen ein Rollback. Wenn Sie ausstehende Ergänzungen oder Änderungen beibehalten möchten, rufen Sie [Update](#update) vor dem Aufruf `Close` für jede Recordset.

Rufen Sie `Open` erneut nach dem Aufruf `Close`. Dadurch können Sie die Wiederverwendung des Recordset-Objekts. Eine bessere Alternative ist, rufen Sie [Requery](#requery), sofern möglich.

Verwandte Informationen finden Sie im Thema "Close-Methode" in-DAO-Hilfe.

##  <a name="delete"></a>  CDaoRecordset::Delete

Rufen Sie diese Memberfunktion zum Löschen des aktuellen Datensatzes in einem geöffneten Dynaset oder Tabellentyp Recordset-Objekt.

```
virtual void Delete();
```

### <a name="remarks"></a>Hinweise

Nach einem erfolgreichen Löschvorgang, dem Recordset Felddatenmember werden auf einen Nullwert festgelegt, und müssen Sie explizit eine Recordset Navigation Memberfunktionen aufrufen ( [verschieben](#move), [Seek](#seek), [ SetBookmark](#setbookmark)usw.) um den gelöschten Datensatz zu verschieben. Wenn Sie Datensätze aus einem Recordset löschen, es muss ein aktueller Datensatz im Recordset vor dem Aufruf `Delete`ist, andernfalls löst MFC eine Ausnahme.

`Delete` Entfernt den aktuellen Datensatz und macht es nicht zugegriffen werden kann. Obwohl Sie können nicht bearbeiten oder den gelöschten Datensatz verwenden, bleibt er in der aktuellen. Sobald Sie mit einem anderen Datensatz verschieben, können nicht jedoch, Sie den gelöschten Datensatz wieder aktualisieren.

> [!CAUTION]
>  Muss das Recordset aktualisierbar sein und müssen ein gültiger Datensatz im Recordset aktuelle beim Aufrufen `Delete`. Z. B., wenn Sie einen Datensatz löschen, aber kein Bildlauf zu einem neuen Datensatz vor dem Aufruf `Delete` in diesem Fall `Delete` löst eine [CDaoException](../../mfc/reference/cdaoexception-class.md).

Sie können einen Datensatz wiederherstellen, wenn Sie Transaktionen verwenden, und Sie rufen die [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Member-Funktion. Wenn die Basistabelle der primären Tabelle ist in zahlreiche Beziehung löschen, das Löschen des aktuellen Datensatzes kann auch einen oder mehrere Datensätze in einer Fremdschlüsseltabelle. Weitere Informationen finden Sie unter der Definition "Überlappend löschen" in-DAO-Hilfe.

Im Gegensatz zu `AddNew` und `Edit`, einen Aufruf von `Delete` folgt nicht durch einen Aufruf von `Update`.

Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "-Methode Delete", "Update-Methode" und "Aktualisierbare Property" in-DAO-Hilfe.

##  <a name="dofieldexchange"></a>  CDaoRecordset:: DoFieldExchange

Das Framework ruft diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern eines Recordset-Objekts und den entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch an.

```
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Enthält einen Zeiger auf eine `CDaoFieldExchange` Objekt. Das Framework wird bereits dieses Objekts eingerichtet haben, einen Kontext für den Exchange-Vorgang Feld anzugeben.

### <a name="remarks"></a>Hinweise

Sie bindet auch Parameterdatenmember, falls vorhanden, die Platzhalter für Parameter in der SQL-Anweisung-Zeichenfolge für das Recordset Auswahl. Der Austausch von Felddaten, wird aufgerufen, DAO-Datensatzfeldaustausch (DFX), funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes für die Datenquelle, und aus dem Datensatz in der Datenquelle auf das Recordsetobjekt. Wenn Sie Spalten dynamisch binden, müssen Sie nicht implementieren `DoFieldExchange`.

Die einzige Aktion, die normalerweise nötig sind, um implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse ist, erstellen Sie die Klasse mit dem Klassen-Assistenten, und geben Sie den Namen und Datentypen, der den Felddatenmembern. Sie können auch Code hinzufügen, in was ClassWizard an Parameterdatenmember geschrieben. Wenn alle Felder sind dynamisch gebunden werden, wird diese Funktion inaktiv sein, es sei denn, Sie Parameterdatenmember angeben.

Wenn Sie mit Klassen-Assistent abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` für Sie das folgende Beispiel ähnelt:

[!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]

##  <a name="edit"></a>  CDaoRecordset::Edit

Rufen Sie diese Memberfunktion, um Änderungen an den aktuellen Datensatz zu ermöglichen.

```
virtual void Edit();
```

### <a name="remarks"></a>Hinweise

Wenn Sie Aufrufen der `Edit` Memberfunktion, Änderungen an Feldern des aktuellen Datensatzes in der Kopierpuffer kopiert werden. Rufen Sie nach dem vornehmen der gewünschten Änderungen am Datensatz `Update` zum Speichern der Änderungen. `Edit` Speichert die Werte der Datenelemente des Recordsets. Wenn Sie aufrufen `Edit`, nehmen Änderungen vor, und rufen dann `Edit` in diesem Fall werden die Werte des Datensatzes vor dem ersten einstellungsänderungen wiederhergestellt `Edit` aufrufen.

> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten, und führen Sie dann auf alle Vorgänge, die in einem anderen Datensatz erst nach Aufrufen von verschiebt `Update`, Ihre Änderungen gehen verloren, ohne Warnung. Wenn Sie das Recordset oder die übergeordnete Datenbank schließen, wird darüber hinaus Ihre bearbeitete Datensätze ohne Warnung verworfen.

In einigen Fällen möchten möglicherweise eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Zu diesem Zweck rufen `SetFieldNull` mit dem Parameter "true" markieren Sie das Feld Null; dies auch bewirkt, dass die Spalte aktualisiert werden. Wenn Sie möchten ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert wurde, rufen Sie `SetFieldDirty` mit dem Parameter "true". Dies funktioniert auch, wenn das Feld den Wert Null haben.

Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld geändert automatisch, sodass Sie nur selten aufrufen, müssen [SetFieldDirty](#setfielddirty) selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten werden explizit aktualisiert oder eingefügt werden unabhängig davon, ob welcher Wert im Feld-Datenmember ist. Der DFX-Mechanismus verwendet auch die Verwendung von **UNECHTE NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss explizit das Feld geändert festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Feld Prüfung.

Der Datensatz bleibt gesperrt, ab dem Zeitpunkt, wenn das Recordset-Objekt in einer mehrbenutzerumgebung pessimistisch gesperrt ist, `Edit` wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz ist gesperrt und im Vergleich mit dem Datensatz, der bereits bearbeiteten, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen `Edit`, `Update` fehl und MFC eine Ausnahme auslöst. Sie können ändern, dass der Sperrmodus mit `SetLockingMode`.

> [!NOTE]
>  Optimistische wird immer auf der externen Datenbank-Formate, z. B. ODBC und installierbaren ISAM verwendet.

Der aktuelle Datensatz bleibt nach dem Aufruf von aktuellen `Edit`. Aufzurufende `Edit`, muss ein aktueller Datensatz vorhanden sein. Wenn kein aktueller Datensatz vorhanden ist, oder wenn das Recordset nicht auf eine offene Tabellentyp oder Dynaset eines assistentartigen Recordset-Objekt verwiesen wird, tritt eine Ausnahme auf. Aufrufen von `Edit` bewirkt, dass eine `CDaoException` in den folgenden Situationen ausgelöst:

- Es ist kein aktueller Datensatz vorhanden.

- Die Datenbank oder ein Recordset ist schreibgeschützt.

- Es sind keine Felder im Datensatz aktualisiert.

- Die Datenbank oder ein Recordset wurde für die ausschließliche Verwendung von einem anderen Benutzer geöffnet.

- Ein anderer Benutzer hat die Seite mit Ihren Eintrag gesperrt.

Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Edit` Teil einer Transaktion aufrufen. Beachten Sie, die Sie aufrufen sollten `CDaoWorkspace::BeginTrans` vor dem Aufruf `Edit` und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf `CDaoWorkspace::CommitTrans` ist kein Ersatz für den Aufruf `Update` zum Abschließen der `Edit` Vorgang. Weitere Informationen über Transaktionen finden Sie unter Klasse `CDaoWorkspace`.

Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "-Methode Delete", "Update-Methode" und "Aktualisierbare Property" in-DAO-Hilfe.

##  <a name="fillcache"></a>  FillCache

Rufen Sie diese Memberfunktion, um eine angegebene Anzahl von Datensätzen aus dem Recordset zwischenzuspeichern.

```
void FillCache(
    long* pSize = NULL,
    COleVariant* pBookmark = NULL);
```

### <a name="parameters"></a>Parameter

*pSize*<br/>
Gibt die Anzahl der Zeilen im Cache zu füllen. Wenn Sie diesen Parameter weglassen, wird der Wert durch die Einstellung der CacheSize-Eigenschaft des zugrunde liegenden DAO-Objekts bestimmt.

*pBookmark*<br/>
Ein [COleVariant](../../mfc/reference/colevariant-class.md) ein Lesezeichen angeben. Auffüllen des Caches wird aus dem Datensatz, der durch dieses Lesezeichen angegeben ab. Wenn Sie diesen Parameter weglassen, ist der Cache gefüllt, beginnend mit des Datensatzes von der CacheStart-Eigenschaft, der das zugrunde liegende DAO-Objekt.

### <a name="remarks"></a>Hinweise

Das Zwischenspeichern verbessert die Leistung einer Anwendung, die abgerufen oder an, die Daten von einem Remoteserver abruft. Ein Cache ist Speicherplatz im lokalen Speicher, der das zuletzt auf der Annahme, dass die Daten wahrscheinlich erneut angefordert werden, während die Anwendung ausgeführt wird vom Server abgerufenen Daten enthält. Wenn Daten angefordert werden, überprüft die Microsoft Jet-Datenbank-Engine den Cache für die Daten zuerst anstatt es aus dem Server, wodurch mehr Zeit benötigt, abruft. Zwischenspeichern von Daten auf nicht-ODBC-Datenquellen mit hat keine Auswirkungen, wie die Daten nicht im Cache gespeichert werden.

Statt zu warten, für den Cache mit Datensätzen gefüllt werden soll, wie sie abgerufen werden, Sie können explizit füllen den Cache zu einem beliebigen Zeitpunkt durch Aufrufen der `FillCache` Member-Funktion. Dies ist eine schnellere Möglichkeit, die vom Cache belegt werden, da `FillCache` ruft mehrere Datensätze auf einmal statt jeweils einzeln ab. Beispielsweise wird zwar jeweils eine Seite mit Datensätzen angezeigt wird, dass Ihre Anwendung muss durch Aufrufen `FillCache` zum Abrufen der nächsten Seite mit Datensätzen.

Eine ODBC-Datenbank mit Recordset-Objekte auf Sie zugegriffen haben einen lokalen Cache. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt aus der remote-Datenquelle, und rufen Sie dann die `SetCacheSize` und `SetCacheStart` Memberfunktionen des Recordset-Objekts. Wenn *lSize beim Aufruf* und *lBookmark* erstellen Sie einen Bereich, der teilweise oder vollständig außerhalb des Bereichs, der anhand des `SetCacheSize` und `SetCacheStart`, der Teil des Recordsets außerhalb dieses Bereichs wird ignoriert und nicht in den Cache geladen. Wenn `FillCache` anfordert, mehrere Datensätze als verbleiben in der Remotedatenquelle, nur die übrigen Datensätze abgerufen werden und keine Ausnahme ausgelöst wird.

Datensätze aus dem Cache abgerufen werden nicht gleichzeitig mit der Datenquelle von anderen Benutzern vorgenommene Änderungen wider.

`FillCache` Ruft nur die Datensätze, die noch nicht zwischengespeichert. Um ein Update aller zwischengespeicherten Daten zu erzwingen, rufen die `SetCacheSize` Member-Funktion mit einer *lSize beim Aufruf* Parameter gleich 0 (null) Aufruf `SetCacheSize` erneut mit der *lSize beim Aufruf* Parameter gleich der Größe des Caches Sie ursprünglich angefordert hat, und rufen dann `FillCache`.

Weitere Informationen finden Sie unter dem Thema "Zwischenspeichergröße" in-DAO-Hilfe.

##  <a name="find"></a>  CDaoRecordset::Find

Rufen Sie diese Memberfunktion zum Suchen einer bestimmten Zeichenfolge in einem Typ Dynaset oder Snapshot-Recordset, das mit einem Vergleichsoperator.

```
virtual BOOL Find(
    long lFindType,
    LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parameter

*lFindType*<br/>
Ein Wert, der angibt, der des Typs des gewünschten Suchvorgang. Mögliche Werte sind:

- AFX_DAO_NEXT suchen Sie den nächsten Speicherort einer übereinstimmenden Zeichenfolge.

- AFX_DAO_PREV suchen Sie den vorherigen Speicherort einer übereinstimmenden Zeichenfolge.

- AFX_DAO_FIRST finden Sie den ersten Speicherort einer übereinstimmenden Zeichenfolge.

- Den letzten Speicherort von einer übereinstimmenden Zeichenfolge AFX_DAO_LAST zu finden.

*lpszFilter*<br/>
Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL-Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen. Zum Beispiel:

[!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Finden Sie ersten, nächsten, vorherigen oder letzten Instanz der Zeichenfolge. `Find` ist Sie eine virtuelle Funktion, sodass Sie überschreiben und eine eigene Implementierung hinzufügen können. Die `FindFirst`, `FindLast`, `FindNext`, und `FindPrev` Memberfunktionen rufen die `Find` Member-Funktion, sodass Sie verwenden können `Find` zur Steuerung des Verhaltens von alle Suchvorgänge.

Um einen Datensatz in einem Recordset-Tabelle vom Typ zu suchen, rufen Sie die [Seek](#seek) Member-Funktion.

> [!TIP]
>  Je kleiner die Gruppe von Datensätzen-haben die effektiver `Find` werden. Im Allgemeinen und vor allem bei ODBC-Datenspeichern ist es besser, eine neue Abfrage zu erstellen, die nur die Datensätze abruft, die Sie möchten.

Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in-DAO-Hilfe.

##  <a name="findfirst"></a>  CDaoRecordset::FindFirst

Rufen Sie diese Memberfunktion um den ersten Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.

```
BOOL FindFirst(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parameter

*lpszFilter*<br/>
Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL-Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `FindFirst` Memberfunktion beginnt die Suche am Anfang des Recordset und sucht bis zum Ende des Recordset-Objekts.

Wenn alle beinhalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer von der Verschiebevorgänge mithilfe von Datensatz zu Datensatz verschoben werden sollen. Um einen Datensatz in einem Recordset-Tabelle vom Typ zu suchen, rufen Sie die `Seek` Member-Funktion.

Wenn ein Datensatz den Kriterien nicht gefunden wird, ist die Zeiger für den aktuellen Datensatz unbestimmt, und `FindFirst` gibt NULL zurück. Wenn das Recordset mehr als einem Datensatz enthält, die den Kriterien entsprechen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.

> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass zum Speichern der Änderungen durch Aufrufen der `Update` Member-Funktion, die vor dem Wechsel zu einem anderen Datensatz. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.

Die `Find` Member-Funktionen zu suchen, in den Speicherort, und klicken Sie auf die Richtung, in der folgenden Tabelle angegeben:

|Suchvorgänge|beginnen|Suchrichtung|
|---------------------|-----------|----------------------|
|`FindFirst`|Anfang des recordset|Ende des Recordsets|
|`FindLast`|Ende des Recordsets|Anfang des recordset|
|`FindNext`|Aktueller Datensatz|Ende des Recordsets|
|`FindPrevious`|Aktueller Datensatz|Anfang des recordset|

> [!NOTE]
>  Beim Aufruf `FindLast`, die Microsoft Jet-Datenbank-Engine füllt das Recordset vollständig vor Beginn der Suche auf, wenn dies nicht bereits geschehen ist. Bei der ersten Suche dauert länger als nachfolgende suchen.

Mit einer der Vorgänge suchen ist nicht der gleiche wie das Aufrufen `MoveFirst` oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Führen Sie einen Suchvorgang mit einem Verschiebevorgang.

Bedenken Sie Folgendes bei Verwendung der Suchvorgänge:

- Wenn `Find` gibt, die ungleich NULL, die der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den Zeiger für den aktuellen Datensatz an einem gültigen Datensatz positionieren.

- Sie können keinen Suchvorgang mit einem Vorwärtscursor Bildlauf Momentaufnahme Recordset vom Typ verwenden.

- Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, auch wenn Sie nicht die US-Version der Microsoft Jet-Datenbank-Engine; verwenden Andernfalls kann übereinstimmende Datensätze nicht gefunden werden.

- Beim Arbeiten mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise fest, dass die Suchvorgänge mit langsam, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln sowie in der Parameterabfragen, oder `CDaoQuerydef` Objekte, die bestimmte indizierte Datensätze abgerufen werden.

Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in-DAO-Hilfe.

##  <a name="findlast"></a>  CDaoRecordset::FindLast

Rufen Sie diese Memberfunktion um den letzten Datensatz suchen, der mit einer angegebene Bedingung übereinstimmt.

```
BOOL FindLast(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parameter

*lpszFilter*<br/>
Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL-Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `FindLast` Memberfunktion beginnt die Suche am Ende des Recordset-Objekts und Suche rückwärts bis zum Anfang des Recordset-Objekts.

Wenn alle beinhalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer von der Verschiebevorgänge mithilfe von Datensatz zu Datensatz verschoben werden sollen. Um einen Datensatz in einem Recordset-Tabelle vom Typ zu suchen, rufen Sie die `Seek` Member-Funktion.

Wenn ein Datensatz den Kriterien nicht gefunden wird, ist die Zeiger für den aktuellen Datensatz unbestimmt, und `FindLast` gibt NULL zurück. Wenn das Recordset mehr als einem Datensatz enthält, die den Kriterien entsprechen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht die nächste Instanz hinter dem ersten Vorkommen, und So weiter.

> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie die Änderungen speichern, durch den Aufruf der `Update` Member-Funktion, die vor dem Wechsel zu einem anderen Datensatz. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.

Mit einer der Vorgänge suchen ist nicht der gleiche wie das Aufrufen `MoveFirst` oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Führen Sie einen Suchvorgang mit einem Verschiebevorgang.

Bedenken Sie Folgendes bei Verwendung der Suchvorgänge:

- Wenn `Find` gibt, die ungleich NULL, die der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den Zeiger für den aktuellen Datensatz an einem gültigen Datensatz positionieren.

- Sie können keinen Suchvorgang mit einem Vorwärtscursor Bildlauf Momentaufnahme Recordset vom Typ verwenden.

- Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, auch wenn Sie nicht die US-Version der Microsoft Jet-Datenbank-Engine; verwenden Andernfalls kann übereinstimmende Datensätze nicht gefunden werden.

- Beim Arbeiten mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise fest, dass die Suchvorgänge mit langsam, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln sowie in der Parameterabfragen, oder `CDaoQuerydef` Objekte, die bestimmte indizierte Datensätze abgerufen werden.

Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in-DAO-Hilfe.

##  <a name="findnext"></a>  CDaoRecordset::FindNext

Rufen Sie diese Memberfunktion um den nächsten Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.

```
BOOL FindNext(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parameter

*lpszFilter*<br/>
Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL-Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `FindNext` Memberfunktion beginnt die Suche auf den aktuellen Datensatz und sucht bis zum Ende des Recordset-Objekts.

Wenn alle beinhalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer von der Verschiebevorgänge mithilfe von Datensatz zu Datensatz verschoben werden sollen. Um einen Datensatz in einem Recordset-Tabelle vom Typ zu suchen, rufen Sie die `Seek` Member-Funktion.

Wenn ein Datensatz den Kriterien nicht gefunden wird, ist die Zeiger für den aktuellen Datensatz unbestimmt, und `FindNext` gibt NULL zurück. Wenn das Recordset mehr als einem Datensatz enthält, die den Kriterien entsprechen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.

> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie die Änderungen speichern, durch den Aufruf der `Update` Member-Funktion, die vor dem Wechsel zu einem anderen Datensatz. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.

Mit einer der Vorgänge suchen ist nicht der gleiche wie das Aufrufen `MoveFirst` oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Führen Sie einen Suchvorgang mit einem Verschiebevorgang.

Bedenken Sie Folgendes bei Verwendung der Suchvorgänge:

- Wenn `Find` gibt, die ungleich NULL, die der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den Zeiger für den aktuellen Datensatz an einem gültigen Datensatz positionieren.

- Sie können keinen Suchvorgang mit einem Vorwärtscursor Bildlauf Momentaufnahme Recordset vom Typ verwenden.

- Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, auch wenn Sie nicht die US-Version der Microsoft Jet-Datenbank-Engine; verwenden Andernfalls kann übereinstimmende Datensätze nicht gefunden werden.

- Beim Arbeiten mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise fest, dass die Suchvorgänge mit langsam, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln sowie in der Parameterabfragen, oder `CDaoQuerydef` Objekte, die bestimmte indizierte Datensätze abgerufen werden.

Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in-DAO-Hilfe.

##  <a name="findprev"></a>  CDaoRecordset::FindPrev

Rufen Sie diese Memberfunktion zum vorherigen Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.

```
BOOL FindPrev(LPCTSTR lpszFilter);
```

### <a name="parameters"></a>Parameter

*lpszFilter*<br/>
Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL-Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die `FindPrev` Memberfunktion beginnt die Suche auf den aktuellen Datensatz und sucht rückwärts bis zum Anfang des Recordset-Objekts.

Wenn alle beinhalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer von der Verschiebevorgänge mithilfe von Datensatz zu Datensatz verschoben werden sollen. Um einen Datensatz in einem Recordset-Tabelle vom Typ zu suchen, rufen Sie die `Seek` Member-Funktion.

Wenn ein Datensatz den Kriterien nicht gefunden wird, ist die Zeiger für den aktuellen Datensatz unbestimmt, und `FindPrev` gibt NULL zurück. Wenn das Recordset mehr als einem Datensatz enthält, die den Kriterien entsprechen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.

> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie die Änderungen speichern, durch den Aufruf der `Update` Member-Funktion, die vor dem Wechsel zu einem anderen Datensatz. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.

Mit einer der Vorgänge suchen ist nicht der gleiche wie das Aufrufen `MoveFirst` oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Führen Sie einen Suchvorgang mit einem Verschiebevorgang.

Bedenken Sie Folgendes bei Verwendung der Suchvorgänge:

- Wenn `Find` gibt, die ungleich NULL, die der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den Zeiger für den aktuellen Datensatz an einem gültigen Datensatz positionieren.

- Sie können keinen Suchvorgang mit einem Vorwärtscursor Bildlauf Momentaufnahme Recordset vom Typ verwenden.

- Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, auch wenn Sie nicht die US-Version der Microsoft Jet-Datenbank-Engine; verwenden Andernfalls kann übereinstimmende Datensätze nicht gefunden werden.

- Beim Arbeiten mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise fest, dass die Suchvorgänge mit langsam, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln sowie in der Parameterabfragen, oder `CDaoQuerydef` Objekte, die bestimmte indizierte Datensätze abgerufen werden.

Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in-DAO-Hilfe.

##  <a name="getabsoluteposition"></a>  CDaoRecordset:: GetAbsolutePosition

Gibt die Nummer des aktuellen Datensatzes einem Recordset-Objekt zurück.

```
long GetAbsolutePosition();
```

### <a name="return-value"></a>Rückgabewert

Eine ganze Zahl von 0 auf die Anzahl der Datensätze im Recordset. Entspricht der Position des aktuellen Datensatzes im Recordset.

### <a name="remarks"></a>Hinweise

Der Wert der AbsolutePosition-Eigenschaft das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz im Recordset. Sie können die Anzahl der aufgefüllten Datensätze im Recordset zu ermitteln, durch den Aufruf [GetRecordCount](#getrecordcount). Aufrufen von `GetRecordCount` kann einige Zeit dauern, weil sie alle Datensätze aus, um zu bestimmen, die Anzahl die zugreifen muss.

Wenn es keine aktueller Datensatz ist, als es sind keine Datensätze im Recordset, - 1 zurückgegeben. Wenn der aktuelle Datensatz gelöscht wird, den Wert der AbsolutePosition-Eigenschaft ist nicht definiert, und löst MFC eine Ausnahme aus, wenn darauf verwiesen wird. Für Recordsets vom Typ Dynaset werden neue Einträge am Ende der Sequenz hinzugefügt.

> [!NOTE]
>  Diese Eigenschaft ist nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, klicken Sie auf einer bestimmten Position und die einzige Möglichkeit, den aktuellen Datensatz für alle Typen des Recordset-Objekte zu positionieren. Insbesondere ändert die Position eines bestimmten Datensatzes auf, wenn vorhergehenden Datensätze gelöscht werden. Es gibt auch keine Zusicherung, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets, nicht unbedingt, es sei denn, sie mit der Verwendung einer SQL-Anweisung erstellt wird eine  **ORDERBY** Klausel.

> [!NOTE]
>  Diese Memberfunktion ist nur für Dynaset und Recordsets vom Typ Snapshot gültig.

Weitere Informationen finden Sie unter dem Thema "AbsolutePosition-Eigenschaft" in-DAO-Hilfe.

##  <a name="getbookmark"></a>  CDaoRecordset:: GetBookmark

Rufen Sie diese Memberfunktion um den Wert für die Lesezeichen in einem bestimmten Datensatz zu erhalten.

```
COleVariant GetBookmark();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert, der das Lesezeichen für den aktuellen Datensatz darstellt.

### <a name="remarks"></a>Hinweise

Bei einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, wenn es unterstützt. Rufen Sie `CanBookmark` zu bestimmen, ob ein Recordset Lesezeichen unterstützt.

Sie können das Lesezeichen für den aktuellen Datensatz speichern, indem Sie den Wert des Lesezeichens, das Zuweisen einer `COleVariant` Objekt. Rufen Sie zum schnellen an diesen Datensatz zu einem beliebigen Zeitpunkt nach dem Wechsel zu einem anderen Datensatz zurückgeben `SetBookmark` mit einem Parameter entsprechend dem Wert dieser `COleVariant` Objekt.

> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.

Verwandte Informationen finden Sie im Thema "Lesezeicheneigenschaft" in-DAO-Hilfe.

##  <a name="getcachesize"></a>  CDaoRecordset::GetCacheSize

Rufen Sie diese Memberfunktion, um die Anzahl der zwischengespeicherten Datensätze zu erhalten.

```
long GetCacheSize();
```

### <a name="return-value"></a>Rückgabewert

Ein Wert, der angibt, die Anzahl der Datensätze in einem Recordset Dynaset-Typ, die mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.

### <a name="remarks"></a>Hinweise

Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Dynaset eines assistentartigen Recordset-Objekte abruft. Ein Cache ist ein Leerzeichen im lokalen Speicher, der das den Fall, dass die Daten erneut angefordert werden, während der Ausführung der Anwendung zuletzt vom Server abgerufenen Daten enthält. Wenn Daten angefordert werden, überprüft die Microsoft Jet-Datenbank-Engine den Cache für die angeforderten Daten zuerst statt Abruf aus dem Server, wodurch mehr Zeit benötigt. Daten, die nicht von einer ODBC-Datenquelle stammt, ist nicht im Cache gespeichert.

Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle haben einen lokalen Cache.

Verwandte Informationen finden Sie im Thema "CacheSize, CacheStart-Eigenschaften" in-DAO-Hilfe.

##  <a name="getcachestart"></a>  CDaoRecordset::GetCacheStart

Rufen Sie diese Memberfunktion zum Abrufen des Lesezeichenwert, der den ersten Datensatz im Recordset zwischengespeichert werden.

```
COleVariant GetCacheStart();
```

### <a name="return-value"></a>Rückgabewert

Ein `COleVariant` , der das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden angibt.

### <a name="remarks"></a>Hinweise

Die Microsoft Jet-Datenbank-Engine Datensätze innerhalb des Bereichs des Cache aus dem Cache, und es Anforderungen Datensätze außerhalb des Bereichs des Caches auf dem Server.

> [!NOTE]
>  Aus dem Cache abgerufenen Datensätze nicht gleichzeitig mit der Datenquelle von anderen Benutzern vorgenommenen Änderungen wieder.

Verwandte Informationen finden Sie im Thema "CacheSize, CacheStart-Eigenschaften" in-DAO-Hilfe.

##  <a name="getcurrentindex"></a>  CDaoRecordset::GetCurrentIndex

Rufen Sie diese Memberfunktion, um zu bestimmen, den Index aktuell in Verwendung in einer volltextindizierten Tabelle Typ `CDaoRecordset` Objekt.

```
CString GetCurrentIndex();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` mit dem Namen des Index mit einem Recordset vom Typ Tabelle verwendet. Gibt eine leere Zeichenfolge zurück, wenn kein Index festgelegt wurde.

### <a name="remarks"></a>Hinweise

Dieser Index ist die Grundlage für ordnen der Datensätze in einem Recordset Tabelle Typ und wird verwendet, indem die [Seek](#seek) Member-Funktion, um Datensätze zu suchen.

Ein `CDaoRecordset` Objekt kann mehr als einen Index aufweisen, jedoch können nur einen Index zu einem Zeitpunkt verwenden (obwohl eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt möglicherweise mehrere Indizes definiert ist).

Weitere Informationen finden Sie im Thema "Indexobjekt" und der Definition der "aktuellen Index" in-DAO-Hilfe.

##  <a name="getdatecreated"></a>  CDaoRecordset::GetDateCreated

Rufen Sie diese Memberfunktion zum Abrufen, das Datum und Uhrzeit der Erstellung eine Basistabelle.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Rückgabewert

Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) -Objekt, enthält das Datum und Uhrzeit die Basistabelle erstellt wurde.

### <a name="remarks"></a>Hinweise

Datums-und Uhrzeiteinstellungen abgeleitet werden auf dem Computer, auf denen die Basistabelle erstellt wurde.

Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.

##  <a name="getdatelastupdated"></a>  CDaoRecordset::GetDateLastUpdated

Rufen Sie diese Memberfunktion zum Abrufen von Datum und Uhrzeit der letzten Aktualisierung des Schemas.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Rückgabewert

Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und Uhrzeit der letzten die Basistabellenstruktur (Schema Aktualisierung) enthält.

### <a name="remarks"></a>Hinweise

Datums-und Uhrzeiteinstellungen abgeleitet werden auf dem Computer, auf denen die Struktur der Basistabelle (Schema) zuletzt aktualisiert wurde.

Verwandte Informationen finden Sie im Thema "DateCreated, LastUpdated-Eigenschaften" in-DAO-Hilfe.

##  <a name="getdefaultdbname"></a>  CDaoRecordset::GetDefaultDBName

Rufen Sie diese Memberfunktion um den Namen der Datenbank für dieses Recordset zu bestimmen.

```
virtual CString GetDefaultDBName();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , enthält der Pfad und Name der Datenbank, von dem dieses Recordset abgeleitet ist.

### <a name="remarks"></a>Hinweise

Wenn ein Recordset erstellt wird, ohne einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), und klicken Sie dann diesen Pfad vom Recordset verwendet wird, um die Standarddatenbank zu öffnen. Standardmäßig gibt diese Funktion eine leere Zeichenfolge zurück. Wenn Klassen-Assistent ein neues Recordset aus abgeleitet `CDaoRecordset`, diese Funktion wird für Sie erstellt.

Das folgende Beispiel veranschaulicht die Verwendung der doppelte umgekehrte Schrägstrich (\\\\) wird wie in der Zeichenfolge, erforderlich, damit die Zeichenfolge, die richtig interpretiert werden.

[!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]

##  <a name="getdefaultsql"></a>  CDaoRecordset::GetDefaultSQL

Das Framework ruft diese Member-Funktion, um die Standard-SQL-Anweisung zu erhalten, auf der das Recordset basiert.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die die Standard-SQL-Anweisung enthält.

### <a name="remarks"></a>Hinweise

Dies ist möglicherweise ein Tabellenname oder SQL **wählen** Anweisung.

Sie definieren die Standard-SQL-Anweisung indirekt durch Deklarieren des Recordset-Klasse mit dem Klassen-Assistenten, und der Klassen-Assistent führt diese Aufgabe für Sie.

Wenn Sie eine SQL-null-Zeichenfolge zu übergeben [öffnen](#open), und klicken Sie dann diese Funktion aufgerufen wird, um den Tabellennamen oder SQL für Recordset zu bestimmen.

##  <a name="geteditmode"></a>  CDaoRecordset::GetEditMode

Rufen Sie diese Memberfunktion zum Bestimmen des Status der Bearbeitung, dies ist einer der folgenden Werte ein:

```
short GetEditMode();
```

### <a name="return-value"></a>Rückgabewert

Gibt einen Wert, der den Status der Bearbeiten für den aktuellen Datensatz angibt.

### <a name="remarks"></a>Hinweise

|Wert|Beschreibung|
|-----------|-----------------|
|`dbEditNone`|Keine Bearbeitungsvorgang wird ausgeführt.|
|`dbEditInProgress`|`Edit` wurde aufgerufen.|
|`dbEditAdd`|`AddNew` wurde aufgerufen.|

Weitere Informationen finden Sie unter dem Thema "EditMode-Eigenschaft" in-DAO-Hilfe.

##  <a name="getfieldcount"></a>  CDaoRecordset::GetFieldCount

Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Feldern (Spalten), die im Recordset definiert.

```
short GetFieldCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Felder im Recordset.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter dem Thema "Count-Eigenschaft" in-DAO-Hilfe.

##  <a name="getfieldinfo"></a>  CDaoRecordset::GetFieldInfo

Rufen Sie diese Memberfunktion zum Abrufen von Informationen zu den Feldern in einem Recordset.

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des vordefinierten Felds in die Recordset Fields-Sammlung, für die Suche nach Index.

*FieldInfo*<br/>
Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen werden hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen. Rufen Sie für eine optimale Leistung nur die Ebene der benötigten Informationen ein:

- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Typ, Größe und der Attribute

- `AFX_DAO_SECONDARY_INFO` Primäre Informationen sowie: Ordnungszahl ab, die erforderlich sind, ermöglichen Null Länge Reihenfolge sortieren, Fremdschlüssel, Feld "Quelle" Quelle Namenstabelle

- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären sowie: Default Value Validierungsregel Überprüfung Text

*Wert*<br/>
Der Name des Felds.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen zu suchen.

Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getfieldvalue"></a>  CDaoRecordset:: GetFieldValue

Rufen Sie diese Memberfunktion zum Abrufen von Daten in einem Recordset.

```
virtual void GetFieldValue(
    LPCTSTR lpszName,
    COleVariant& varValue);

virtual void GetFieldValue(
    int nIndex,
    COleVariant& varValue);

virtual COleVariant GetFieldValue(LPCTSTR lpszName);
virtual COleVariant GetFieldValue(int nIndex);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die den Namen eines Felds enthält.

*varValue*<br/>
Ein Verweis auf eine `COleVariant` -Objekt, das den Wert eines Felds gespeichert werden.

*nIndex*<br/>
Ein nullbasierter Index des Felds in die Recordset Fields-Sammlung, für die Suche nach Index.

### <a name="return-value"></a>Rückgabewert

Die beiden Versionen des `GetFieldValue` , die einen Wert zurückgeben Zurückgeben einer [COleVariant](../../mfc/reference/colevariant-class.md) -Objekt, das den Wert eines Felds enthält.

### <a name="remarks"></a>Hinweise

Sie können ein Feld nach Name oder Ordnungsposition nachschlagen.

> [!NOTE]
>  Es ist effizienter, rufen Sie eine der Versionen von dieser Memberfunktion, ein `COleVariant` Objektverweis als Parameter, anstatt eine Version, die gibt Aufrufen einer `COleVariant` Objekt. Die letzten Versionen dieser Funktion werden für die Abwärtskompatibilität beibehalten.

Verwendung `GetFieldValue` und [SetFieldValue](#setfieldvalue) Sie Felder zur Laufzeit statt statisch zu binden von Spalten mit dynamisch binden die [DoFieldExchange](#dofieldexchange) Mechanismus.

`GetFieldValue` und die `DoFieldExchange` Mechanismus kann kombiniert werden, um die Leistung zu verbessern. Verwenden Sie z. B. `GetFieldValue` zum Abrufen eines Werts, die Sie bei Bedarf nur benötigen, und weisen Sie diesen Aufruf auf eine Schaltfläche "Weitere Informationen" in der Schnittstelle.

Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in-DAO-Hilfe.

##  <a name="getindexcount"></a>  CDaoRecordset::GetIndexCount

Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl von Indizes, die auf das Recordset Tabellentyp verfügbar.

```
short GetIndexCount();
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Indizes im Recordset Tabellentyp.

### <a name="remarks"></a>Hinweise

`GetIndexCount` eignet sich für alle Indizes in das Recordset durchlaufen. Verwenden Sie zu diesem Zweck `GetIndexCount` in Verbindung mit [GetIndexInfo](#getindexinfo). Wenn Sie diese Memberfunktion auf Dynaset oder Recordsets vom Typ Snapshot aufrufen, löst MFC eine Ausnahme aus.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getindexinfo"></a>  CDaoRecordset::GetIndexInfo

Rufen Sie diese Memberfunktion zum Abrufen von verschiedenen Arten von Informationen zu einem Index in der Basistabelle, die zugrunde liegende ein Recordset definiert.

```
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index in der Tabelle Indizes-Auflistung, für die Suche nach numerischen Position.

*indexinfo*<br/>
Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.

*dwInfoOptions*<br/>
Optionen, die angeben, welche Informationen über den Index abrufen. Die verfügbaren Optionen werden hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen. Rufen Sie für eine optimale Leistung nur die Ebene der benötigten Informationen ein:

- `AFX_DAO_PRIMARY_INFO` (Standard) Name, Feldinformationen, Felder

- `AFX_DAO_SECONDARY_INFO` Primäre Informationen sowie: primäre "," Unique "," Clustered "," IgnoreNulls, erforderlich, Fremdschlüssel

- `AFX_DAO_ALL_INFO` Informationen zu primären und sekundären sowie: Distinct Count

*Wert*<br/>
Ein Zeiger auf den Namen des Index-Objekt, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie einen Index nach seiner Position in der Auflistung gesucht. Die andere Version können Sie einen Index nach Namen suchen.

Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur hat Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen *DwInfoOptions*. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.

Verwandte Informationen finden Sie im Thema "Attributes-Eigenschaft" in-DAO-Hilfe.

##  <a name="getlastmodifiedbookmark"></a>  CDaoRecordset::GetLastModifiedBookmark

Rufen Sie diese Memberfunktion, um das Lesezeichen des Datensatzes die zuletzt hinzugefügte oder aktualisierte abzurufen.

```
COleVariant GetLastModifiedBookmark();
```

### <a name="return-value"></a>Rückgabewert

Ein `COleVariant` hinzugefügten oder geänderten Datensatz mit einem Lesezeichen, das die zuletzt angibt.

### <a name="remarks"></a>Hinweise

Bei einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, wenn es unterstützt. Rufen Sie [GetBookmark](#getbookmark) zu bestimmen, ob das Recordset Lesezeichen unterstützt. Wenn das Recordset keine Lesezeichen unterstützt eine `CDaoException` ausgelöst.

Wenn Sie einen Eintrag hinzufügen, am Ende des Recordset-Objekts angezeigt wird, und ist nicht der aktuelle Datensatz. Um den neuen Datensatz aktualisieren, rufen Sie `GetLastModifiedBookmark` und rufen dann `SetBookmark` auf den neu hinzugefügten Datensatz zurückgegeben.

Verwandte Informationen finden Sie im Thema "LastModified-Eigenschaft" in-DAO-Hilfe.

##  <a name="getlockingmode"></a>  CDaoRecordset::GetLockingMode

Rufen Sie diese Memberfunktion, um die Sperrung an für das Recordset zu bestimmen.

```
BOOL GetLockingMode();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der Typ der Sperre pessimistische, ist für vollständige datensatzsperrung andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn pessimistische Sperrung, gilt die Datenseite mit dem Datensatz, die Sie bearbeiten, ist gesperrt, sobald Sie aufrufen, die [bearbeiten](#edit) Member-Funktion. Die Seite ist nicht gesperrt, beim Aufrufen der [Update](#update) oder [schließen](#close) Memberfunktion oder einer der Vorgänge verschieben oder suchen.

Bei der optimistischen Sperre wird verwendet, ist die Datenseite mit dem Datensatz gesperrt, nur verwendet werden, während der Aktualisierung des Datensatzes mit der `Update` Member-Funktion.

Der Sperrmodus ist immer optimistische, bei der Arbeit mit ODBC-Datenquellen.

Weitere Informationen finden Sie unter den Themen "Sperren Property" und "Sperren Verhalten in mehreren Benutzern Anwendungen" in-DAO-Hilfe.

##  <a name="getname"></a>  CDaoRecordset::GetName

Rufen Sie diese Memberfunktion auf den Namen des Recordset-Objekts abrufen.

```
CString GetName();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` mit dem Namen des Recordset-Objekts.

### <a name="remarks"></a>Hinweise

Der Name des Recordset-Objekts muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen, aber keine Interpunktionszeichen oder Leerzeichen enthalten.

Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in-DAO-Hilfe.

##  <a name="getparamvalue"></a>  CDaoRecordset::GetParamValue

Rufen Sie diese Memberfunktion zum Abrufen von des aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter-Objekt gespeichert.

```
virtual COleVariant GetParamValue(int nIndex);
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Die numerische Position des Parameters in der zugrunde liegenden DAOParameter-Objekt.

*Wert*<br/>
Der Name des Parameters, dessen Wert soll.

### <a name="return-value"></a>Rückgabewert

Ein Objekt der Klasse [COleVariant](../../mfc/reference/colevariant-class.md) , die den Wert des Parameters enthält.

### <a name="remarks"></a>Hinweise

Sie können die Parameter nach Namen oder durch die numerische Position in der Auflistung zugreifen.

Verwandte Informationen finden Sie im Thema "Parameterobjekt" in-DAO-Hilfe.

##  <a name="getpercentposition"></a>  CDaoRecordset:: GetPercentPosition

Beim Arbeiten mit einer Dynaset oder Snapshot-Type-Recordset, wenn Sie aufrufen `GetPercentPosition` vor dem vollständig auffüllen das Recordset, datenverschiebung ist relativ zur Anzahl der Datensätze zugegriffen wird, wie durch Aufrufen von [GetRecordCount](#getrecordcount).

```
float GetPercentPosition();
```

### <a name="return-value"></a>Rückgabewert

Eine Zahl zwischen 0 und 100, die die ungefähre Position des aktuellen Datensatzes in die Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset angibt.

### <a name="remarks"></a>Hinweise

Sie können bis zum letzten Datensatz verschieben durch Aufrufen von [MoveLast](#movelast) , vollständige die Auffüllung des Recordsets, aber dies dauert eine längere Zeitspanne.

Rufen Sie `GetPercentPosition` auf alle drei Typen von Recordset-Objekte, einschließlich der Tabellen ohne Indizes. Rufen Sie jedoch nicht möglich `GetPercentPosition` auf Vorwärtscursor Bildlauf Momentaufnahmen oder auf einem Recordset nach einer Pass-Through-Abfrage einer externen Datenbank geöffnet. Wenn kein aktueller Datensatz vorhanden ist, oder seine aktuellen Datensatz gelöscht wurde, eine `CDaoException` ausgelöst.

Verwandte Informationen finden Sie im Thema "PercentPosition-Eigenschaft" in-DAO-Hilfe.

##  <a name="getrecordcount"></a>  CDaoRecordset::GetRecordCount

Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze in einem Recordset zugegriffen wurde.

```
long GetRecordCount();
```

### <a name="return-value"></a>Rückgabewert

Gibt die Anzahl der Datensätze, die auf die in einem Recordset-Objekt zurück.

### <a name="remarks"></a>Hinweise

`GetRecordCount` Gibt nicht an wie viele Datensätze in einem Dynaset-Typ oder die Momentaufnahme vom Typ enthalten sind, bis alle Datensätze zugegriffen wurde. Dieser Aufruf der Memberfunktion kann sehr viel Zeit in Anspruch in Anspruch nehmen.

Nachdem der letzte Datensatz zugegriffen wurde, gibt der zurückgegebene Wert die Gesamtzahl nicht gelöschte Datensätze im Recordset an. Um Zugriff auf den letzten Datensatz zu erzwingen, rufen die `MoveLast` oder `FindLast` -Memberfunktion des Recordsets. Sie können auch eine SQL-Anzahl verwenden, um die ungefähre Anzahl der Datensätze zu ermitteln, die die Abfrage zurückgeben wird.

Wenn Ihre Anwendung Daten in einem Recordset Dynaset-Typ, der Rückgabewert von löscht `GetRecordCount` verringert wird. Von anderen Benutzern gelöschten Datensätze werden jedoch nicht widergespiegelt, indem `GetRecordCount` bis der aktuelle Datensatz mit einem gelöschten Datensatz positioniert ist. Wenn Sie die Ausführung einer Transaktion, die die Anzahl der Datensätze wirkt sich auf und anschließend ein der Transaktion Rollback `GetRecordCount` spiegeln nicht die tatsächliche Anzahl der verbleibenden Datensätze.

Der Wert des `GetRecordCount` aus einem Recordset-Momentaufnahme-Typ wird durch Änderungen an den zugrunde liegenden Tabellen nicht beeinflusst.

Der Wert des `GetRecordCount` aus einen Tabellentyp Recordset gibt die ungefähre Anzahl der Datensätze in der Tabelle, und wird sofort beeinflusst, wie Datensätze hinzugefügt und gelöscht werden.

Ein Recordset mit keine Datensätze gibt den Wert 0 zurück. Bei der Arbeit mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` immer - 1 zurückgegeben. Aufrufen der `Requery` Member-Funktion auf einem Recordset setzt den Wert der `GetRecordCount` als ob die Abfrage erneut ausgeführt wurden.

Weitere Informationen finden Sie unter dem Thema "RecordCount-Eigenschaft" in-DAO-Hilfe.

##  <a name="getsql"></a>  CDaoRecordset::GetSQL

Rufen Sie diese Memberfunktion rufen Sie die SQL-Anweisung, die verwendet wurde, des Recordsets Datensätze auswählen, wenn sie geöffnet wurde.

```
CString GetSQL() const;
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die die SQL-Anweisung enthält.

### <a name="remarks"></a>Hinweise

Diese werden in der Regel eine SQL **wählen** Anweisung.

Die Zeichenfolge, die vom `GetSQL` unterscheidet sich in der Regel von einer beliebigen Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die *LpszSQL* Parameter, um die [öffnen](#open) Member-Funktion. Dies ist, da das Recordset eine vollständige SQL-Anweisung, die basierend erstellt auf der Sie übergeben `Open`, was Sie mit der Klassen-Assistenten angegeben haben. und was Sie in angegeben haben möglicherweise die [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) Datenmember.

> [!NOTE]
>  Rufen Sie nur nach dem Aufruf dieser Memberfunktion `Open`.

Weitere Informationen finden Sie unter dem Thema "SQL-Eigenschaft" in-DAO-Hilfe.

##  <a name="gettype"></a>  CDaoRecordset::GetType

Aufgerufen Sie diese Memberfunktion wird nach Öffnen des Recordsets, um zu bestimmen, den Typ des Recordset-Objekts.

```
short GetType();
```

### <a name="return-value"></a>Rückgabewert

Eine der folgenden Werte, der den Typ eines Recordsets angibt:

- `dbOpenTable` Recordset vom Typ Tabelle

- `dbOpenDynaset` Vom Typ Dynaset

- `dbOpenSnapshot` Recordset-Momentaufnahme vom Typ

### <a name="remarks"></a>Hinweise

Verwandte Informationen finden Sie im Thema "Type-Eigenschaft" in-DAO-Hilfe.

##  <a name="getvalidationrule"></a>  CDaoRecordset::GetValidationRule

Rufen Sie diese Memberfunktion, um zu bestimmen, die Regel verwendet, um Daten zu überprüfen.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` -Objekt, das einen Wert, der die Daten in einem Datensatz überprüft werden, da sie einer Tabelle hinzugefügt, geändert oder enthält.

### <a name="remarks"></a>Hinweise

Diese Regel textbasiert ist und angewendet wird jedes Mal, wenn die zugrunde liegende Tabelle geändert wird. Wenn die Daten nicht zulässig ist, löst MFC eine Ausnahme aus. Die zurückgegebene Fehlermeldung lautet der Text der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt, wenn angegeben, oder den Text des Ausdrucks durch die ValidationRule-Eigenschaft des zugrunde liegenden Field-Objekt. Rufen Sie [GetValidationText](#getvalidationtext) zum Abrufen des Texts der Fehlermeldung.

Z. B. ein Feld in einem Datensatz, der den Tag des Monats erfordert möglicherweise eine Validierungsregel wie z. B. "Tag zwischen 1 und 31."

Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" in-DAO-Hilfe.

##  <a name="getvalidationtext"></a>  CDaoRecordset::GetValidationText

Rufen Sie diese Memberfunktion zum Abrufen des Texts der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt.

```
CString GetValidationText();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` Objekt mit dem Text der Nachricht, die angezeigt wird, wenn der Wert eines Felds Überprüfungsregel für das zugrunde liegende Feldobjekt nicht erfüllt.

### <a name="remarks"></a>Hinweise

Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in-DAO-Hilfe.

##  <a name="isbof"></a>  CDaoRecordset::IsBOF

Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf von Datensatz zu Datensatz darüber, ob Sie vor dem ersten Datensatz des Recordsets durchgeführt haben.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset keine Datensätze enthält, oder wenn Sie kein Bildlauf rückwärts vor dem ersten Datensatz durchgeführt haben; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie können auch aufrufen `IsBOF` zusammen mit `IsEOF` bestimmen, ob das Recordset keine Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von `Open`, wenn keine Datensätze, das Recordset enthält `IsBOF` ungleich NULL zurückgibt. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz den aktuellen Datensatz und `IsBOF` gibt 0 zurück.

Wenn der erste Datensatz der aktuelle Datensatz ist ein, und Sie rufen `MovePrev`, `IsBOF` anschließend ungleich NULL zurück. Wenn `IsBOF` ungleich Null gibt und Sie rufen `MovePrev`, wird eine Ausnahme ausgelöst. Wenn `IsBOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und jede Aktion, die einen aktuellen Datensatz erforderlich sind, führt zu einer Ausnahme.

Auswirkungen von bestimmten Methoden auf `IsBOF` und `IsEOF` Einstellungen:

- Aufrufen von `Open*` intern wird der erste Datensatz im Recordset des aktuellen Datensatzes durch Aufrufen von `MoveFirst`. Aus diesem Grund Aufrufen `Open` auf einen leeren Satz von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe die folgende Tabelle für das Verhalten einer fehlgeschlagenen `MoveFirst` oder `MoveLast` aufrufen.)

- Dazu führen, dass alle Move-Vorgänge, die einen Datensatz finden beide `IsBOF` und `IsEOF` 0 zurückgegeben.

- Ein `AddNew` Aufruf, gefolgt von einer `Update` Aufruf, die erfolgreich einen neuen Datensatz einfügt bewirkt, dass `IsBOF` 0, jedoch nur, wenn zurückzugebende `IsEOF` bereits ungleich NULL ist. Der Status der `IsEOF` bleiben stets unverändert. Gemäß der Definition von der Microsoft Jet-Datenbank-Engine ist Zeiger für den aktuellen Datensatz der eine leere Datensatzgruppe am Ende einer Datei, damit alle neuen Datensätze nach den aktuellen Datensatz eingefügt wird.

- Alle `Delete` Aufruf, auch wenn den letzte Datensatz aus einem Recordset, entfernt ändert sich nicht den Wert der `IsBOF` oder `IsEOF`.

In dieser Tabelle sind die Move-Vorgänge zulässig sind, mit verschiedenen Kombinationen von `IsBOF` /  `IsEOF`.

||MoveFirst, MoveLast|MovePrev,<br /><br /> Verschieben Sie die < 0|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie die > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= ungleich NULL ist,<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|
|Beide 0|Allowed|Allowed|Allowed|Allowed|

Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang erfolgreich einen Datensatz findet. Es gibt lediglich an, dass ein Versuch, den angegebenen Vorgang durchzuführen, ist zulässig, und keine Ausnahme generiert. Der Wert des der `IsBOF` und `IsEOF` Memberfunktionen möglicherweise das Verschieben geändert.

Die Auswirkungen der Verschiebevorgänge, die nicht auf dem Wert ein Datensatzes finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle dargestellt wird.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ungleich null|Ungleich null|
|`Move` 0|Keine Änderung|Keine Änderung|
|`MovePrev`, `Move` < 0|Ungleich null|Keine Änderung|
|`MoveNext`, `Move` > 0|Keine Änderung|Ungleich null|

Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaften" in-DAO-Hilfe.

##  <a name="isdeleted"></a>  CDaoRecordset::IsDeleted

Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz gelöscht wurde.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Recordset auf einen gelöschten Datensatz positioniert ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn Sie auf einen Datensatz scrollen und `IsDeleted` gibt "true" (ungleich null), und Sie müssen einen Bildlauf zu einem anderen Datensatz, bevor Sie alle anderen Recordset-Vorgänge ausführen können.

> [!NOTE]
>  Sie müssen nicht den Status "gelöscht" für Daten in einem Recordset Momentaufnahme- oder eine Tabelle Typ zu überprüfen. Da Datensätze aus einer Momentaufnahme nicht gelöscht werden können, besteht keine Notwendigkeit zum Aufrufen `IsDeleted`. Recordsets vom Typ Tabelle werden gelöschte Datensätze tatsächlich aus dem Recordset entfernt. Sobald ein Datensatz, entweder von Ihnen, einen anderen Benutzer oder in einem anderen Recordset gelöscht wurde können nicht Sie wieder an diesen Datensatz scrollen. Daher besteht keine Notwendigkeit zum Aufrufen `IsDeleted`.

Wenn Sie einen Datensatz aus einem Dynaset löschen, wird er aus dem Recordset entfernt, und Sie wieder an diesen Datensatz scrollen können nicht. Wenn ein Datensatz in ein Dynaset wird jedoch gelöscht, oder von einem anderen Benutzer als auch in einem anderen Recordset basierend auf der gleichen Tabelle `IsDeleted` gibt "true" zurück, wenn Sie später zu dieser Datensatz wechseln.

Weitere Informationen finden Sie unter den Themen "-Methode Delete", "Eigenschaft" LastModified "und"EditMode-Eigenschaft"in-DAO-Hilfe.

##  <a name="iseof"></a>  CDaoRecordset::IsEOF

Rufen Sie diese Memberfunktion auf, wie Sie einen Bildlauf von Datensatz zu Datensatz darüber, ob Sie den letzten Datensatz des Recordsets überschritten haben.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset keine Datensätze enthält, oder Sie hinter dem letzten Datensatz gescrollt haben; andernfalls 0.

### <a name="remarks"></a>Hinweise

Sie können auch aufrufen `IsEOF` bestimmen, ob das Recordset keine Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von `Open`, wenn keine Datensätze, das Recordset enthält `IsEOF` ungleich NULL zurückgibt. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz den aktuellen Datensatz und `IsEOF` gibt 0 zurück.

Wenn der letzte Datensatz beim Aufrufen des aktuellen Datensatzes ist `MoveNext`, `IsEOF` anschließend ungleich NULL zurück. Wenn `IsEOF` ungleich Null gibt und Sie rufen `MoveNext`, wird eine Ausnahme ausgelöst. Wenn `IsEOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und jede Aktion, die einen aktuellen Datensatz erforderlich sind, führt zu einer Ausnahme.

Auswirkungen von bestimmten Methoden auf `IsBOF` und `IsEOF` Einstellungen:

- Aufrufen von `Open` intern wird der erste Datensatz im Recordset des aktuellen Datensatzes durch Aufrufen von `MoveFirst`. Aus diesem Grund Aufrufen `Open` auf einen leeren Satz von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe die folgende Tabelle für das Verhalten einer fehlgeschlagenen `MoveFirst` aufrufen.)

- Dazu führen, dass alle Move-Vorgänge, die einen Datensatz finden beide `IsBOF` und `IsEOF` 0 zurückgegeben.

- Ein `AddNew` Aufruf, gefolgt von einer `Update` Aufruf, die erfolgreich einen neuen Datensatz einfügt bewirkt, dass `IsBOF` 0, jedoch nur, wenn zurückzugebende `IsEOF` bereits ungleich NULL ist. Der Status der `IsEOF` bleiben stets unverändert. Gemäß der Definition von der Microsoft Jet-Datenbank-Engine ist Zeiger für den aktuellen Datensatz der eine leere Datensatzgruppe am Ende einer Datei, damit alle neuen Datensätze nach den aktuellen Datensatz eingefügt wird.

- Alle `Delete` Aufruf, auch wenn den letzte Datensatz aus einem Recordset, entfernt ändert sich nicht den Wert der `IsBOF` oder `IsEOF`.

In dieser Tabelle sind die Move-Vorgänge zulässig sind, mit verschiedenen Kombinationen von `IsBOF` /  `IsEOF`.

||MoveFirst, MoveLast|MovePrev,<br /><br /> Verschieben Sie die < 0|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie die > 0|
|------|-------------------------|-----------------------------|------------|-----------------------------|
|`IsBOF`= ungleich NULL ist,<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|
|Beide 0|Allowed|Allowed|Allowed|Allowed|

Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang erfolgreich einen Datensatz findet. Es gibt lediglich an, dass ein Versuch, den angegebenen Vorgang durchzuführen, ist zulässig, und keine Ausnahme generiert. Der Wert des der `IsBOF` und `IsEOF` Memberfunktionen möglicherweise das Verschieben geändert.

Die Auswirkungen der Verschiebevorgänge, die nicht auf dem Wert ein Datensatzes finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle dargestellt wird.

||IsBOF|IsEOF|
|------|-----------|-----------|
|`MoveFirst`, `MoveLast`|Ungleich null|Ungleich null|
|`Move` 0|Keine Änderung|Keine Änderung|
|`MovePrev`, `Move` < 0|Ungleich null|Keine Änderung|
|`MoveNext`, `Move` > 0|Keine Änderung|Ungleich null|

Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaften" in-DAO-Hilfe.

##  <a name="isfielddirty"></a>  CDaoRecordset::IsFieldDirty

Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember ein Dynaset, als "fehlerhaft eingestellt ist" (geändert).

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder geändert werden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das angegebene Feld-Daten-Element als fehlerhaft gekennzeichnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Daten in alle Felddatenmember übertragen werden sollen den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der `Update` Memberfunktion `CDaoRecordset` (nach einem Aufruf von `Edit` oder `AddNew`). Mit diesem Wissen Sie können Schritte weiter, wie z. B. Aufheben der Kennzeichnung der Feld-Datenmember, die die Spalte zu kennzeichnen, sodass Sie sie nicht an die Datenquelle geschrieben wird.

`IsFieldDirty` wird durch implementiert `DoFieldExchange`.

##  <a name="isfieldnull"></a>  CDaoRecordset::IsFieldNull

Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember eines Recordset-Objekts als Null gekennzeichnet wurde.

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder Null sind.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das angegebene Feld-Daten-Element, als Null gekennzeichnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

(Null, in der datenbankterminologie bedeutet "kein Wert having" und entspricht nicht der NULL-Wert in C++.) Wenn ein Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte mit den aktuellen Datensatz interpretiert für die kein Wert vorhanden ist.

> [!NOTE]
>  In bestimmten Situationen mit `IsFieldNull` kann ineffizient sein, wie im folgenden Codebeispiel wird veranschaulicht:

[!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]

> [!NOTE]
>  Wenn Sie dynamische Bindung aufzuzeichnen, verwenden werden, ohne eine Ableitung von `CDaoRecordset`, achten Sie darauf, dass Sie VT_NULL zu verwenden, wie im Beispiel gezeigt.

##  <a name="isfieldnullable"></a>  CDaoRecordset::IsFieldNullable

Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Feld-Datenelement "NULL" ist (möglicherweise auf einen Null-Wert festgelegt NULL in C++ ist nicht identisch mit Null, womit, in der datenbankterminologie "having kein Wert").

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder Null sind.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das angegebene Feld-Daten-Element Null festgelegt werden kann; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, diese ein Feld auf Null, die beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und `Update` wird eine Ausnahme ausgelöst. Die Ausnahme tritt auf, beim Aufrufen `Update`, nicht beim Aufrufen `SetFieldNull`.

##  <a name="isopen"></a>  CDaoRecordset::IsOpen

Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset geöffnet ist.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich Null des Recordset-Objekts `Open` oder `Requery` Member-Funktion wurde zuvor aufgerufen und das Recordset nicht geschlossen wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

##  <a name="m_bcheckcachefordirtyfields"></a>  CDaoRecordset:: M_bcheckcachefordirtyfields

Enthält ein Flag, der angibt, ob zwischengespeicherte Felder automatisch als gekennzeichnet sind, geändert (geändert) und Null.

### <a name="remarks"></a>Hinweise

Das Flag ist standardmäßig auf "true". Die Einstellung in diesem Data-Member steuert den gesamten doppelte Pufferung-Mechanismus. Wenn Sie das Flag auf "true" festlegen, können Sie die Zwischenspeicherung pro Feld-nach-Feld mit dem Mechanismus DFX deaktivieren. Wenn Sie das Flag auf "false" festlegen, müssen Sie aufrufen `SetFieldDirty` und `SetFieldNull` selbst.

Legen Sie diesen Datenmember vor dem Aufruf `Open`. Dieser Mechanismus ist in erster Linie für erleichterte Bedienung. Leistung ist möglicherweise langsamer aufgrund die doppelte Pufferung der Felder, wenn Änderungen vorgenommen werden.

##  <a name="m_nfields"></a>  CDaoRecordset::m_nFields

Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.

### <a name="remarks"></a>Hinweise

Der Konstruktor für das Recordset-Klasse muss initialisiert werden `m_nFields` mit der richtigen Anzahl von statisch gebundenen Felder. Klassen-Assistent schreibt diese Initialisierung für Sie aus, wenn Sie es verwenden, um die Recordset-Klasse zu deklarieren. Sie können es auch manuell schreiben.

Das Framework verwendet diese Zahl zum Verwalten der Interaktion zwischen den Felddatenmembern und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle.

> [!NOTE]
>  Diese Zahl muss entsprechen, die Anzahl von Ausgabespalten in registriert die `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter `CDaoFieldExchange::outputColumn`.

Sie können die Spalten dynamisch mit binden `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue`. Wenn Sie dies tun, müssen Sie nicht erhöht die Anzahl die in `m_nFields` entsprechend der Anzahl der DFX-Funktion aufruft, Ihre `DoFieldExchange` Member-Funktion.

##  <a name="m_nparams"></a>  CDaoRecordset::m_nParams

Enthält die Anzahl der Parameterdatenmember in die Recordset-Klasse, die Anzahl von Parametern, die mit dem Recordset Abfrage übergeben.

### <a name="remarks"></a>Hinweise

Wenn Recordset-Klasse keine Parameter statischen Datenmember verfügt, muss der Konstruktor für die Klasse initialisiert *M_nParams* mit der richtigen Anzahl. Der Wert des *M_nParams* hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen – dies manuell ausführen müssen, müssen Sie auch manuell eine Initialisierung im Klassenkonstruktor entsprechend die Anzahl von Parametern hinzufügen (die muss mindestens so groß wie die Anzahl der "Platzhalter in Ihre *M_strFilter*  oder *M_strSort* Zeichenfolge).

Das Framework verwendet diese Zahl an, wenn sie die Abfrage des Recordsets parametrisiert.

> [!NOTE]
>  Diese Zahl muss entsprechen, die Anzahl der "Params" in registriert die `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter `CFieldExchange::param`.

Verwandte Informationen finden Sie im Thema "Parameterobjekt" in-DAO-Hilfe.

##  <a name="m_pdaorecordset"></a>  CDaoRecordset::m_pDAORecordset

Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Recordset-Objekt zugrunde liegenden der `CDaoRecordset` Objekt.

### <a name="remarks"></a>Hinweise

Verwenden Sie diesen Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen möchten.

Verwandte Informationen finden Sie im Thema "Recordset-Objekts" in-DAO-Hilfe.

##  <a name="m_pdatabase"></a>  CDaoRecordset::m_pDatabase

Enthält einen Zeiger auf die `CDaoDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.

### <a name="remarks"></a>Hinweise

Diese Variable wird auf zwei Arten festgelegt werden. In der Regel, übergeben Sie einen Zeiger auf ein bereits geöffnetes `CDaoDatabase` -Objekt beim Erstellen des Recordsetobjekts. Wenn Sie stattdessen, NULL übergeben `CDaoRecordset` erstellt eine `CDaoDatabase` -Objekt für Sie und öffnet sie. In beiden Fällen `CDaoRecordset` der Zeiger in dieser Variable gespeichert.

Normalerweise Sie nicht direkt benötigen, verwenden Sie den Zeiger, der in gespeicherten `m_pDatabase`. Wenn Sie Ihre eigenen Erweiterungen schreiben `CDaoRecordset`, allerdings müssen möglicherweise den Zeiger zu verwenden. Z. B. möglicherweise den Zeiger, wenn Sie lösen eigene `CDaoException`(s).

Verwandte Informationen finden Sie im Thema "Database-Objekt" in-DAO-Hilfe.

##  <a name="m_strfilter"></a>  CDaoRecordset::m_strFilter

Enthält eine Zeichenfolge, die verwendet wird, zum Erstellen der **, in denen** -Klausel einer SQL­Anweisung.

### <a name="remarks"></a>Hinweise

Er umfasst keine das reservierte Wort **, in denen** das Recordset zu filtern. Die Verwendung dieses Datenelements gilt nicht für Recordsets vom Typ Tabelle zur Verfügung. Die Verwendung von `m_strFilter` wirkt sich nicht beim Öffnen einer Datensatzgruppe mit einem `CDaoQueryDef` Zeiger.

Verwenden Sie die US-Datumsformat (Monat-Tag-Jahr) beim Filtern von Feldern mit Datumsangaben, auch wenn Sie nicht die US-Version der Microsoft Jet-Datenbank-Engine; verwenden Andernfalls können die Daten nicht gefiltert werden, wie zu erwarten.

Verwandte Informationen finden Sie im Thema "Filter-Eigenschaft" in-DAO-Hilfe.

##  <a name="m_strsort"></a>  CDaoRecordset::m_strSort

Enthält eine Zeichenfolge mit der **ORDERBY** -Klausel einer SQL­Anweisung ohne den reservierten Wörtern **ORDERBY**.

### <a name="remarks"></a>Hinweise

Sie können auf Typ Dynaset und Momentaufnahme-Recordset-Objekte sortieren.

Tabellentyp Recordset-Objekte können nicht sortiert werden. Um die Sortierreihenfolge des Recordset Typ Tabelle zu ermitteln, rufen [SetCurrentIndex](#setcurrentindex).

Die Verwendung von *M_strSort* wirkt sich nicht beim Öffnen einer Datensatzgruppe mit einem `CDaoQueryDef` Zeiger.

Weitere Informationen finden Sie unter dem Thema "Sort-Eigenschaft" in-DAO-Hilfe.

##  <a name="move"></a>  CDaoRecordset::Move

Rufen Sie diese Memberfunktion, um das Recordset zu positionieren *lRows* Datensätze aus dem aktuellen Datensatz.

```
virtual void Move(long lRows);
```

### <a name="parameters"></a>Parameter

*lRows*<br/>
Die Anzahl von Datensätzen, vorwärts oder rückwärts bewegen. Positive Werte vorwärts, zum Ende des Recordset-Objekts. Negative Werte werden zurück, bis zum Anfang verschieben.

### <a name="remarks"></a>Hinweise

Sie können entweder vorwärts oder rückwärts bewegen. `Move( 1 )` entspricht dem `MoveNext`, und `Move( -1 )` entspricht `MovePrev`.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie in der Regel beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmt, ob das Recordset alle Datensätze ist. Nach dem Aufruf von `Open` oder `Requery`, rufen Sie entweder `IsBOF` oder `IsEOF`.

> [!NOTE]
>  Wenn Sie direkt hinter dem Anfang oder Ende des Recordset gescrollt haben ( `IsBOF` oder `IsEOF` ungleich NULL zurückgibt), einen Aufruf von `Move` löst eine `CDaoException`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Beim Aufruf `Move` für eine vorwärts gerichtete Bildlauf Momentaufnahme, die *lRows* -Parameter muss eine positive ganze Zahl sein und Lesezeichen sind nicht zulässig, sodass Sie nur vorwärts bewegen können.

Damit wird der ersten, letzten, nächsten oder vorherigen aufzeichnen in einem Recordset den aktuellen Datensatz, Aufruf der `MoveFirst`, `MoveLast`, `MoveNext`, oder `MovePrev` Member-Funktion.

Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext und MovePrevious-Methode" in-DAO-Hilfe.

##  <a name="movefirst"></a>  CDaoRecordset::MoveFirst

Rufen Sie diese Memberfunktion um den ersten Datensatz im Recordset zu machen (sofern vorhanden) des aktuellen Datensatzes.

```
void MoveFirst();
```

### <a name="remarks"></a>Hinweise

Sie müssen keine Aufrufen `MoveFirst` sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt ist der erste Datensatz (sofern vorhanden) automatisch den aktuellen Datensatz.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie in der Regel beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmt, ob das Recordset alle Datensätze ist. Nach dem Aufruf von `Open` oder `Requery`, rufen Sie entweder `IsBOF` oder `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Verwenden der `Move` Funktionen von Datensatz zu Datensatz verschoben, ohne die Anwendung einer Bedingung. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder momentaufnahmetyp Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.

Wenn das Recordset zu einem Recordset vom Typ Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.

Wenn Sie aufrufen `MoveLast` auf einem Recordset-Objekt, das auf einer SQL-Abfrage oder Querydef basiert, bis zum Abschluss die Abfrage erzwungen wird und das Recordset-Objekt wird vollständig aufgefüllt.

Sie können nicht aufgerufen werden die `MoveFirst` oder `MovePrev` Member-Funktion mit den Bildlauf vorwärts-Momentaufnahme.

Rufen Sie um die Position des aktuellen aufzeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Einträgen vorwärts oder rückwärts verschieben `Move`.

Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext und MovePrevious-Methode" in-DAO-Hilfe.

##  <a name="movelast"></a>  CDaoRecordset::MoveLast

Rufen Sie diese Memberfunktion um den letzten Datensatz (sofern vorhanden) zu machen, im Recordset des aktuellen Datensatzes.

```
void MoveLast();
```

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie in der Regel beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmt, ob das Recordset alle Datensätze ist. Nach dem Aufruf von `Open` oder `Requery`, rufen Sie entweder `IsBOF` oder `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Verwenden der `Move` Funktionen von Datensatz zu Datensatz verschoben, ohne die Anwendung einer Bedingung. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder momentaufnahmetyp Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.

Wenn das Recordset zu einem Recordset vom Typ Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.

Wenn Sie aufrufen `MoveLast` auf einem Recordset-Objekt, das auf einer SQL-Abfrage oder Querydef basiert, bis zum Abschluss die Abfrage erzwungen wird und das Recordset-Objekt wird vollständig aufgefüllt.

Rufen Sie um die Position des aktuellen aufzeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Einträgen vorwärts oder rückwärts verschieben `Move`.

Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext und MovePrevious-Methode" in-DAO-Hilfe.

##  <a name="movenext"></a>  CDaoRecordset::MoveNext

Rufen Sie diese Memberfunktion um den nächsten Datensatz im Recordset des aktuellen Datensatzes zu machen.

```
void MoveNext();
```

### <a name="remarks"></a>Hinweise

Es wird empfohlen, die Sie aufrufen `IsBOF` bevor Sie versuchen, die in den vorherigen Datensatz zu verschieben. Ein Aufruf von `MovePrev` löst eine `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie in der Regel beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmt, ob das Recordset alle Datensätze ist. Nach dem Aufruf von `Open` oder `Requery`, rufen Sie entweder `IsBOF` oder `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Verwenden der `Move` Funktionen von Datensatz zu Datensatz verschoben, ohne die Anwendung einer Bedingung. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder momentaufnahmetyp Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.

Wenn das Recordset zu einem Recordset vom Typ Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.

Rufen Sie um die Position des aktuellen aufzeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Einträgen vorwärts oder rückwärts verschieben `Move`.

Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext und MovePrevious-Methode" in-DAO-Hilfe.

##  <a name="moveprev"></a>  CDaoRecordset::MovePrev

Rufen Sie diese Memberfunktion zum vorherigen Datensatz im Recordset des aktuellen Datensatzes zu machen.

```
void MovePrev();
```

### <a name="remarks"></a>Hinweise

Es wird empfohlen, die Sie aufrufen `IsBOF` bevor Sie versuchen, die in den vorherigen Datensatz zu verschieben. Ein Aufruf von `MovePrev` löst eine `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Rufen Sie in der Regel beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmt, ob das Recordset alle Datensätze ist. Nach dem Aufruf von `Open` oder `Requery`, rufen Sie entweder `IsBOF` oder `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Verwenden der `Move` Funktionen von Datensatz zu Datensatz verschoben, ohne die Anwendung einer Bedingung. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder momentaufnahmetyp Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.

Wenn das Recordset zu einem Recordset vom Typ Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.

Sie können nicht aufgerufen werden die `MoveFirst` oder `MovePrev` Member-Funktion mit den Bildlauf vorwärts-Momentaufnahme.

Rufen Sie um die Position des aktuellen aufzeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Einträgen vorwärts oder rückwärts verschieben `Move`.

Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext und MovePrevious-Methode" in-DAO-Hilfe.

##  <a name="open"></a>  CDaoRecordset:: Open

Sie müssen diese Memberfunktion zum Abrufen der Datensätze für das Recordset aufrufen.

```
virtual void Open(
    int nOpenType = AFX_DAO_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    int nOptions = 0);

virtual void Open(
    CDaoTableDef* pTableDef,
    int nOpenType = dbOpenTable,
    int nOptions = 0);

virtual void Open(
    CDaoQueryDef* pQueryDef,
    int nOpenType = dbOpenDynaset,
    int nOptions = 0);
```

### <a name="parameters"></a>Parameter

*nOpenType*<br/>
Einer der folgenden Werte:

- `dbOpenDynaset` Ein Typ Dynaset Recordset mit bidirektionalem Bildlauf. Dies ist die Standardeinstellung.

- `dbOpenTable` Ein Tabellentyp Recordset mit bidirektionalem Bildlauf.

- `dbOpenSnapshot` Ein Momentaufnahme-Type-Recordset mit bidirektionalem Bildlauf.

*lpszSQL*<br/>
Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:

- Ein Nullzeiger.

- Der Name einer oder mehreren Tabledefs und/oder Querydefs (durch Trennzeichen getrennt).

- Eine SQL **wählen** Anweisung (optional mit einem SQL- **, in denen** oder **ORDERBY** Klausel).

- Eine Pass-Through-Abfrage.

*nOptions*<br/>
Ein oder mehrere der unten aufgeführten Optionen. Der Standardwert ist 0. Folgende Werte sind möglich:

- `dbAppendOnly` Sie können nur neue Datensätze (gilt nur für Typ Dynaset-Recordset) anfügen. Diese Option bedeutet in der Tat, dass Datensätze nur angefügt werden können. Die MFC-ODBC-Datenbankklassen haben eine nur-anfügen-Option, die Datensätze abgerufen und angefügt werden kann.

- `dbForwardOnly` Das Recordset ist eine Vorwärts-Momentaufnahme für den Bildlauf.

- `dbSeeChanges` Eine Ausnahme generiert, wenn ein anderer Benutzer die Daten geändert werden, die Sie bearbeiten.

- `dbDenyWrite` Andere Benutzer nicht ändern oder Hinzufügen von Datensätzen.

- `dbDenyRead` Andere Benutzer können keine Datensätze (nur Tabellentyp Recordset) anzeigen.

- `dbReadOnly` Sie können nur Datensätze anzeigen; andere Benutzer können sie ändern.

- `dbInconsistent` Inkonsistente Updates sind (gilt nur für Typ Dynaset-Recordset) zulässig.

- `dbConsistent` Nur einheitliche Aktualisierungen sind (gilt nur für Typ Dynaset-Recordset) zulässig.

> [!NOTE]
>  Die Konstanten `dbConsistent` und `dbInconsistent` gegenseitig aus. Sie können einen verwenden oder die andere aber nicht beide in einer bestimmten Instanz des `Open`.

*pTableDef*<br/>
Ein Zeiger auf eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt. Diese Version ist nur für Recordsets vom Typ Tabelle gültig. Bei Verwendung dieser Option, die `CDaoDatabase` Zeiger, die zum Erstellen der `CDaoRecordset` nicht verwendet wird, wird stattdessen, verwendet die Datenbank, in dem sich die Tabledef befindet.

*pQueryDef*<br/>
Ein Zeiger auf eine [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt. Diese Version ist nur für Dynaset und Recordsets vom Typ Snapshot gültig. Bei Verwendung dieser Option, die `CDaoDatabase` Zeiger, die zum Erstellen der `CDaoRecordset` nicht verwendet wird, wird stattdessen, verwendet die Datenbank, in dem sich die Querydef befindet.

### <a name="remarks"></a>Hinweise

Vor dem Aufruf `Open`, müssen Sie das Recordset-Objekt erstellen. Dafür stehen verschiedene Möglichkeiten zur Verfügung:

- Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das bereits geöffnet ist.

- Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das nicht geöffnet ist. Öffnen des Recordsets einen `CDaoDatabase` Objekt, aber nicht geschlossen es beim Schließen des Recordset-Objekts.

- Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen NULL-Zeiger. Der Recordset ruft `GetDefaultDBName` den Namen des Microsoft Access abrufen. MDB-Datei zu öffnen. Klicken Sie dann Öffnen des Recordsets einen `CDaoDatabase` -Objekt und hält sie zu öffnen, solange das Recordset geöffnet ist. Beim Aufruf `Close` für das Recordset die `CDaoDatabase` Objekt ebenfalls geschlossen.

    > [!NOTE]
    >  Beim Öffnen des Recordsets die `CDaoDatabase` Objekt ist, wird die Datenquelle mit nicht exklusiven Zugriff geöffnet.

Für die Version des `Open` , verwendet der *LpszSQL* Parameter, sobald das Recordset geöffnet ist. Sie können Datensätze in eine der folgenden Arten abrufen. Die erste Möglichkeit besteht, von DFX-Funktionen in Ihre `DoFieldExchange`. Die zweite Option ist die Verwendung dynamischer Bindung durch Aufrufen der `GetFieldValue` Member-Funktion. Diese Optionen können separat oder in Kombination implementiert werden. Wenn sie kombiniert werden, müssen die SQL-Anweisung selbst beim Aufruf von übergeben `Open`.

Bei Verwendung die zweite Version `Open` dort übergeben Sie einer `CDaoTableDef` Objekt, die daraus resultierenden Spalten werden für die Sie über binden `DoFieldExchange` und der DFX-Mechanismus und/oder Bindung dynamisch über `GetFieldValue`.

> [!NOTE]
>  Sie können nur aufrufen `Open` mithilfe einer `CDaoTableDef` -Objekt für Recordsets vom Typ Tabelle.

Die dritte Version bei Verwendung `Open` dort übergeben Sie einer `CDaoQueryDef` -Objekt, dass die Abfrage ausgeführt, und die daraus resultierenden Spalten werden für die Sie über binden `DoFieldExchange` und der DFX-Mechanismus und/oder Bindung dynamisch über `GetFieldValue`.

> [!NOTE]
>  Können Sie nur aufrufen `Open` mithilfe einer `CDaoQueryDef` -Objekt für Dynaset und Recordsets vom Typ Snapshot.

Für die erste Version des `Open` , verwendet der `lpszSQL` Parameter Datensätze werden die ausgewählten basierend auf Kriterien, die in der folgenden Tabelle gezeigt.

|Der Wert des Parameters `lpszSQL`.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|
|--------------------------------------|----------------------------------------|-------------|
|NULL|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||
|Eine durch Trennzeichen getrennte Liste von ein oder mehrere Tabledefs und/oder Querydef Namen.|Alle Spalten dargestellt, der `DoFieldExchange`.|`"Customer"`|
|**Wählen Sie** Spaltenliste **FROM** Tabellenliste|Die angegebenen Spalten aus der angegebenen Tabledef(s) und/oder Querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|

Der üblichen Vorgehensweise wird zum Übergeben von NULL, um `Open`; in diesem Fall `Open` Aufrufe `GetDefaultSQL`, eine überschreibbare Memberfunktion, die Klassen-Assistent beim Erstellen generiert einer `CDaoRecordset`-abgeleitete Klasse. Dieser Wert gibt den Namen des Tabledef(s) und/oder Querydef, die Sie im Klassen-Assistenten angegeben haben. Sie können stattdessen andere Informationen im Angeben der *LpszSQL* Parameter.

Jede Übergabe `Open` eine endgültige SQL-Zeichenfolge für die Abfrage erstellt (die Zeichenfolge möglicherweise die SQL **, in denen** und **ORDERBY** Klauseln angefügt, um die *LpszSQL* Zeichenfolge Sie übergeben), und klicken Sie dann die Abfrage ausführt. Sie können die erstellte Zeichenfolge überprüfen, durch den Aufruf `GetSQL` nach dem Aufruf `Open`.

Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.

Wenn Sie Optionen für das Recordset, wie Sie einen Filter oder eine Sortierung festlegen möchten, legen `m_strSort` oder `m_strFilter` nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf `Open`. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie `Requery`.

Wenn Sie aufrufen `Open` auf ein Dynaset oder Snapshot-Type-Recordset, oder wenn die Datenquelle auf eine SQL-Anweisung oder einer Tabledef, die eine angefügte Tabelle darstellt verweist, können keine `dbOpenTable` für das Typargument; Wenn Sie dies tun, löst MFC eine Ausnahme. Um zu bestimmen, ob ein Objekt Tabledef eine angefügte Tabelle darstellt, erstellen Sie eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt, und rufen die [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Member-Funktion.

Verwenden der `dbSeeChanges` auszugeben, wenn Sie Änderungen, die von einem anderen Benutzer oder ein anderes Programm auf Ihrem Computer beim Bearbeiten oder löschen den gleichen Datensatz abfangen möchten. Wenn zwei Benutzer starten, bearbeiten den gleichen Datensatz, der erste Benutzer aufrufen, z. B. die `Update` Memberfunktion erfolgreich ausgeführt wird. Wenn `Update` wird aufgerufen, durch den zweiten Benutzer eine `CDaoException` ausgelöst. Auf ähnliche Weise, wenn der zweite Benutzer versucht, rufen Sie `Delete` So löschen Sie den Datensatz, und es wurde bereits geändert durch den ersten Benutzer, eine `CDaoException` auftritt.

In der Regel, wenn der Benutzer dies `CDaoException` der Code sollte beim Aktualisieren, aktualisieren Sie den Inhalt der Felder und die geänderte Werte abrufen. Tritt die Ausnahme gerade gelöscht, konnte Ihr Code die Daten des neuen Datensatzes anzeigen, für den Benutzer und eine Meldung gibt an, dass die Daten vor kurzem geändert wurden. An diesem Punkt kann Ihren Code eine Bestätigung anfordern möchte der Benutzer immer noch den Datensatz zu löschen.

> [!TIP]
>  Verwenden Sie die Vorwärts-Option für den Bildlauf (`dbForwardOnly`) zur Verbesserung der Leistung, wenn die Anwendung auf einem einzelnen Durchlauf durch ein Recordset verwendet, die in einer ODBC-Datenquelle geöffnet.

Verwandte Informationen finden Sie im Thema "OpenRecordset Method" in-DAO-Hilfe.

##  <a name="requery"></a>  CDaoRecordset::Requery

Rufen Sie diese Memberfunktion um neu zu erstellen (aktualisieren) einem Recordset.

```
virtual void Requery();
```

### <a name="remarks"></a>Hinweise

Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.

In der Reihenfolge für das Recordset entsprechend der Hinzufügungen und löschungen, die Sie oder andere Benutzer mit der Datenquelle vornehmen, müssen Sie das Recordset erstellen, durch Aufruf `Requery`. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer an die vorhandene Datensätze (aber nicht Additions) Stellen angezeigt. Wenn das Recordset eine Momentaufnahme ist, müssen Sie aufrufen `Requery` entsprechend der Änderungen von anderen Benutzern als auch Ergänzungen und löschungen.

Rufen Sie für ein Dynaset oder eine Momentaufnahme, `Requery` jederzeit das Recordset mit Parameterwerten neu erstellen möchten. Legen Sie den neuen Filter oder sortieren, indem Sie [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) vor dem Aufruf `Requery`. Legen Sie die neuen Parameter Parameterdatenmember vor dem Aufruf neue Werte zuweisen `Requery`.

Wenn der Versuch, die das Recordset neu erstellen ein Fehler auftritt, wird das Recordset geschlossen. Vor dem Aufruf `Requery`, können Sie bestimmen, ob das Recordset, durch den Aufruf erneut abgefragt werden kann die [CanRestart](#canrestart) Member-Funktion. `CanRestart` garantiert nicht, dass `Requery` wird erfolgreich ausgeführt.

> [!CAUTION]
>  Rufen Sie `Requery` erst nach der Sie aufgerufen haben `Open`.

> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.

Sie können nicht aufgerufen werden `Requery` auf ein Dynaset oder Recordset Momentaufnahme vom Typ, wenn der Aufruf `CanRestart` gibt 0 zurück, und Sie können es auf einem Recordset-Tabelle vom Typ.

Wenn beide `IsBOF` und `IsEOF` ungleich NULL zurückgeben, nach dem Aufruf von `Requery`, die Abfrage wurde keine Datensätze und das Recordset enthalten keine Daten zurückgegeben.

Weitere Informationen finden Sie im Thema "Requery-Methode" in-DAO-Hilfe.

##  <a name="seek"></a>  CDaoRecordset::Seek

Rufen Sie diese Memberfunktion um den Datensatz in einem Recordset-Objekt vom Typ indizierte Tabelle zu suchen, die erfüllt wird, die angegebenen Kriterien für den aktuellen index, und vergewissern, dass die zum aktuellen Datensatz.

```
BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKey1,
    COleVariant* pKey2 = NULL,
    COleVariant* pKey3 = NULL);

BOOL Seek(
    LPCTSTR lpszComparison,
    COleVariant* pKeyArray,
    WORD nKeys);
```

### <a name="parameters"></a>Parameter

*lpszComparison*<br/>
Eine der folgenden Ausdrücke: "<","\<=", "=", "> =", oder ">".

*pKey1*<br/>
Ein Zeiger auf eine [COleVariant](../../mfc/reference/colevariant-class.md) , dessen Wert in das erste Feld im Index entspricht. Erforderlich.

*pKey2*<br/>
Ein Zeiger auf eine `COleVariant` , dessen Wert entspricht dem zweiten Feld im Index, sofern vorhanden. Der Standardwert ist NULL.

*pKey3*<br/>
Ein Zeiger auf eine `COleVariant` , dessen Wert entspricht dem dritten Feld im Index, sofern vorhanden. Der Standardwert ist NULL.

*pKeyArray*<br/>
Ein Zeiger auf ein Array von Varianten. Die Größe des Arrays entspricht die Anzahl der Felder im Index.

*nKeys*<br/>
Eine ganze Zahl, die Größe des Arrays, die die Anzahl der Felder im Index entspricht.

> [!NOTE]
>  Geben Sie keine Platzhalter in den Schlüsseln. Bewirkt, dass Platzhalter `Seek` keine übereinstimmenden Datensätze zurückgegeben.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.

### <a name="remarks"></a>Hinweise

Verwenden Sie die zweite (Array) Version `Seek` verarbeiten Indizes vier Felder oder mehr.

`Seek` ermöglicht leistungsstarke Index Recordsets vom Typ Tabelle nach. Sie müssen den aktuellen Index festlegen, durch den Aufruf `SetCurrentIndex` vor dem Aufruf `Seek`. Wenn der Index ein Feld mit einem nicht eindeutigen oder Felder identifiziert `Seek` sucht den ersten Datensatz aus, die die Kriterien erfüllt. Wenn Sie einen Index nicht festlegen, wird eine Ausnahme ausgelöst.

Beachten Sie, dass, wenn Sie ein UNICODE-Recordset nicht erstellen, wird die `COleVariant` Objekte müssen explizit ANSI deklariert werden. Dies kann erfolgen mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *LpszSrc* **,** *VtSrc* **)**  Form des Konstruktors mit *VtSrc* festgelegt `VT_BSTRT` (ANSI) oder mithilfe der `COleVariant` Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *LpszSrc* **,** *VtSrc* **)** mit *VtSrc* festgelegt `VT_BSTRT`.

Beim Aufruf `Seek`, übergeben Sie eine oder mehrere Schlüsselwerte und einem Vergleichsoperator ("<","\<=", "=", "> =", oder ">"). `Seek` durchsucht die angegebene Schlüsselfelder und sucht nach den ersten Datensatz, der die vom angegebenen Kriterien entspricht *LpszComparison* und *pKey1*. Sobald eines gefunden wurde, `Seek` gibt ungleich NULL zurück und macht diesen Datensatz als aktuellen. Wenn `Seek` keine findet eine Übereinstimmung, `Seek` gibt NULL zurück, und der aktuelle Datensatz ist nicht definiert. Bei DAO direkt zu verwenden, müssen Sie explizit die Eigenschaft NoMatch prüfen.

Wenn `lpszComparison` ist "=", "> =", oder ">", `Seek` beginnt am Anfang des Indexes. Wenn *LpszComparison* ist "<" oder "< =", `Seek` startet am Ende des Indexes und rückwärts gesucht werden, es sei denn, es doppelte Einträge am Ende gibt. In diesem Fall `Seek` beginnt an einen beliebigen Eintrag für die doppelte Einträge am Ende des Indexes.

Es muss keine aktuellen Datensatz, bei der Verwendung `Seek`.

Verwenden Sie zum Suchen eines Datensatzes in einem Dynaset oder Snapshot-Type-Recordset, das eine bestimmte Bedingung erfüllt, die Suchvorgänge. Verwenden Sie die Move-Vorgänge von Datensatz zu Datensatz verschoben, um alle Datensätze, nicht nur diejenigen, die eine bestimmte Bedingung erfüllen.

Sie können nicht aufgerufen werden `Seek` auf einer angefügten Tabelle aller geben, da der verbundene Tabellen als Dynaset oder Recordsets vom Typ Snapshot geöffnet werden müssen. Allerdings Aufrufen `CDaoDatabase::Open` um eine installierbare ISAM-Datenbank direkt zu öffnen, rufen Sie `Seek` für Tabellen in der Datenbank zwar die Leistung möglicherweise verlangsamt.

Weitere Informationen finden Sie unter dem Thema "Seek-Methode" in-DAO-Hilfe.

##  <a name="setabsoluteposition"></a>  CDaoRecordset::SetAbsolutePosition

Legt fest, die relative Nummer des aktuellen Datensatzes einem Recordset-Objekt.

```
void SetAbsolutePosition(long lPosition);
```

### <a name="parameters"></a>Parameter

*lPosition*<br/>
Entspricht der Position des aktuellen Datensatzes im Recordset.

### <a name="remarks"></a>Hinweise

Aufrufen von `SetAbsolutePosition` ermöglicht es Ihnen, die Zeiger für den aktuellen Datensatz zu einem bestimmten Datensatz basierend auf seine ordnungspostion im ein Dynaset oder Snapshot-Type-Recordset zu positionieren. Sie können die Nummer des aktuelle Datensatzes auch ermitteln, durch den Aufruf [GetAbsolutePosition](#getabsoluteposition).

> [!NOTE]
>  Diese Memberfunktion ist nur für Dynaset und Recordsets vom Typ Snapshot gültig.

Der Wert der AbsolutePosition-Eigenschaft das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz im Recordset. Festlegen eines Werts größer als die Anzahl der aufgefüllten Datensätze, löst MFC eine Ausnahme ausgelöst. Sie können die Anzahl der aufgefüllten Datensätze im Recordset zu ermitteln, durch den Aufruf der `GetRecordCount` Member-Funktion.

Wenn der aktuelle Datensatz gelöscht wird, den Wert der AbsolutePosition-Eigenschaft ist nicht definiert, und löst MFC eine Ausnahme aus, wenn darauf verwiesen wird. Neue Datensätze werden an das Ende der Sequenz hinzugefügt.

> [!NOTE]
>  Diese Eigenschaft ist nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, klicken Sie auf einer bestimmten Position und die einzige Möglichkeit, den aktuellen Datensatz für alle Typen des Recordset-Objekte zu positionieren, die Lesezeichen unterstützen. Insbesondere ändert die Position eines bestimmten Datensatzes auf, wenn vorhergehenden Datensätze gelöscht werden. Es gibt auch keine Zusicherung, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets, nicht unbedingt, es sei denn, sie mit der Verwendung einer SQL-Anweisung erstellt wird eine  **ORDERBY** Klausel.

Weitere Informationen finden Sie unter dem Thema "AbsolutePosition-Eigenschaft" in-DAO-Hilfe.

##  <a name="setbookmark"></a>  CDaoRecordset:: SetBookmark

Rufen Sie diese Memberfunktion, um auf den Datensatz, der das angegebene Lesezeichen enthält das Recordset zu positionieren.

```
void SetBookmark(COleVariant varBookmark);
```

### <a name="parameters"></a>Parameter

*varBookmark*<br/>
Ein [COleVariant](../../mfc/reference/colevariant-class.md) Objekt mit dem Lesezeichenwert für einen bestimmten Datensatz.

### <a name="remarks"></a>Hinweise

Wenn einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits über ein eindeutiges Lesezeichen. Sie können das Lesezeichen für den aktuellen Datensatz abrufen, durch den Aufruf `GetBookmark` und speichern den Wert in eine `COleVariant` Objekt. Sie können später zu diesem Datensatz zurückkehren, indem `SetBookmark` unter Verwendung des gespeicherten lesezeichenwerts.

> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.

Beachten Sie, dass, wenn Sie ein UNICODE-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann erfolgen mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *LpszSrc* **,** *VtSrc* **)**  Form des Konstruktors mit *VtSrc* festgelegt `VT_BSTRT` (ANSI) oder mithilfe der `COleVariant` Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *LpszSrc* **,** *VtSrc* **)** mit *VtSrc* festgelegt `VT_BSTRT`.

Weitere Informationen finden Sie unter den Themen "Lesezeichen-Eigenschaft" und jeden Eigenschaft"DAO-Hilfe.

##  <a name="setcachesize"></a>  CDaoRecordset:: SetCacheSize

Rufen Sie diese Memberfunktion zum Festlegen der Anzahl der Datensätze, die zwischengespeichert werden.

```
void SetCacheSize(long lSize);
```

### <a name="parameters"></a>Parameter

*lSize beim Aufruf*<br/>
Gibt die Anzahl von Datensätzen. Ein häufig angegebener Wert ist 100. Eine Einstellung mit 0 deaktiviert die Zwischenspeicherung. Die Einstellung muss zwischen 5 und 1200-Datensätze sein. Der Cache kann eine beträchtliche Menge an Arbeitsspeicher verwenden.

### <a name="remarks"></a>Hinweise

Ein Cache ist ein Leerzeichen im lokalen Speicher, der das den Fall, dass die Daten erneut angefordert werden, während der Ausführung der Anwendung zuletzt vom Server abgerufenen Daten enthält. Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Dynaset eines assistentartigen Recordset-Objekte abruft. Wenn Daten angefordert werden, überprüft die Microsoft Jet-Datenbank-Engine den Cache für die angeforderten Daten zuerst statt Abruf aus dem Server, wodurch mehr Zeit benötigt. Daten, die nicht von einer ODBC-Datenquelle stammt, ist nicht im Cache gespeichert.

Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle haben einen lokalen Cache. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt aus der Remotedatenquelle, Aufruf der `SetCacheSize` und `SetCacheStart` Memberfunktionen und rufen Sie dann die `FillCache` Memberfunktion oder Schritt durch die Datensätze mithilfe eines der Move-Vorgänge. Die *lSize beim Aufruf* Parameter, der die `SetCacheSize` Memberfunktion kann auf die Anzahl der Datensätze, die Ihre Anwendung kann gleichzeitig mit arbeiten basieren. Beispielsweise, wenn Sie ein Recordset als Quelle der Daten verwenden, die auf dem Bildschirm angezeigt werden, Sie könnten übergeben die `SetCacheSize` *lSize beim Aufruf* Parameter als 20, 20 Datensätze auf einmal angezeigt.

Verwandte Informationen finden Sie im Thema "CacheSize, CacheStart-Eigenschaften" in-DAO-Hilfe.

##  <a name="setcachestart"></a>  CDaoRecordset:: SetCacheStart

Rufen Sie diese Memberfunktion zum Angeben des Lesezeichens für den ersten Datensatz im Recordset zwischengespeichert werden.

```
void SetCacheStart(COleVariant varBookmark);
```

### <a name="parameters"></a>Parameter

*varBookmark*<br/>
Ein [COleVariant](../../mfc/reference/colevariant-class.md) , der das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden angibt.

### <a name="remarks"></a>Hinweise

Können Sie die Lesezeichenwert, der alle Datensätze für die *VarBookmark* Parameter, der die `SetCacheStart` Member-Funktion. Machen Sie den Datensatz, die Sie verwenden möchten, starten den Cache mit den aktuellen Datensatz, ein Lesezeichen für die Verwendung von diesem Datensatz herzustellen [SetBookmark](#setbookmark), und übergeben Sie den Wert für Lesezeichen als Parameter für die `SetCacheStart` Member-Funktion.

Die Microsoft Jet-Datenbank-Engine Datensätze innerhalb des Bereichs des Cache aus dem Cache, und es Anforderungen Datensätze außerhalb des Bereichs des Caches auf dem Server.

Aus dem Cache abgerufenen Datensätze nicht gleichzeitig mit der Datenquelle von anderen Benutzern vorgenommenen Änderungen wieder.

Um ein Update aller zwischengespeicherten Daten zu erzwingen, übergeben die *lSize beim Aufruf* Parameter der `SetCacheSize` als 0 (null) aufrufen `SetCacheSize` erneut mit der Größe des Caches Sie ursprünglich angefordert hat, und rufen dann die `FillCache` Member-Funktion.

Beachten Sie, dass, wenn Sie ein UNICODE-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann erfolgen mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *LpszSrc* **,** *VtSrc* **)**  Form des Konstruktors mit *VtSrc* festgelegt `VT_BSTRT` (ANSI) oder mithilfe der `COleVariant` Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *LpszSrc* **,** *VtSrc* **)** mit *VtSrc* festgelegt `VT_BSTRT`.

Weitere Informationen finden Sie im Thema CacheSize, CacheStart-Eigenschaften"in-DAO-Hilfe.

##  <a name="setcurrentindex"></a>  CDaoRecordset:: SetCurrentIndex

Rufen Sie diese Memberfunktion, um einen Index für ein Recordset-Tabelle vom Typ festzulegen.

```
void SetCurrentIndex(LPCTSTR lpszIndex);
```

### <a name="parameters"></a>Parameter

*lpszIndex*<br/>
Ein Zeiger, mit dem Namen des Indexes festgelegt werden.

### <a name="remarks"></a>Hinweise

In den Basistabellen werden nicht in einer bestimmten Reihenfolge gespeichert. Einen Index festlegen, ändert die Reihenfolge der Datensätze aus der Datenbank zurückgegeben, aber es hat keine Auswirkungen auf die Reihenfolge, in der die Datensätze gespeichert werden. Der angegebene Index muss bereits definiert sein. Wenn Sie versuchen, eine Indexobjekt verwenden, das nicht vorhanden ist oder wenn der Index nicht festgelegt ist, beim Aufrufen [Seek](#seek), MFC, löst eine Ausnahme aus.

Sie können einen neuen Index für die Tabelle erstellen, durch den Aufruf [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) von und Anhängen von den neuen Index an die Auflistung von Indizes des zugrunde liegenden Tabledef durch Aufrufen von [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#append), und öffnen dann das Recordset.

Aus einem Recordset vom Typ Tabelle zurückgegebene Datensätze können nur von den Indizes, die für die zugrunde liegenden Tabledef definierten sortiert werden. Um Datensätze in einer anderen Reihenfolge sortieren zu können, können Sie öffnen ein Dynaset oder mittels einer SQL-Momentaufnahme-Type-Recordset **ORDERBY** Klausel, die in gespeicherten [CDaoRecordset::m_strSort](#m_strsort).

Weitere Informationen finden Sie im Thema "Indexobjekt" und der Definition der "aktuellen Index" in-DAO-Hilfe.

##  <a name="setfielddirty"></a>  CDaoRecordset:: SetFieldDirty

Rufen Sie diese Memberfunktion zum Kennzeichnen der Felddatenmember des Recordset-Objekts als geändert oder als nicht geändert.

```
void SetFieldDirty(
    void* pv,
    BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Enthält die Adresse eines Datenmembers Feld in der Recordset oder NULL. Wenn der Wert NULL ist, werden alle Felddatenmember der Recordset gekennzeichnet. (NULL in C++ ist nicht identisch mit Null in der Terminologie von Datenbanken, d. h. "müssen keinen Wert.")

*bDirty*<br/>
True, wenn die Felddatenmember wie "(geändert) geändert" gekennzeichnet wird. Andernfalls "false" ist die Felddatenmember gekennzeichnet wird, wie "(unverändert) bereinigen".

### <a name="remarks"></a>Hinweise

Markieren die Felder als nicht geändert wird sichergestellt, dass das Feld nicht aktualisiert wird.

Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld geändert automatisch, sodass Sie nur selten aufrufen, müssen `SetFieldDirty` selbst, aber Sie sollten auch um sicherzustellen, dass die Spalten explizit, aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert in das Feld-Daten ist Member. Der Mechanismus DFX setzt auch die Verwendung von PSEUDONULL. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss das Feld explizit als fehlerhaft festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Feld Prüfung.

> [!NOTE]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).

Verwenden NULL für das erste Argument der Funktion die Funktion für alle gelten `outputColumn` Feldern nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf

[!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]

wird nur festgelegt, `outputColumn` Felder NULL. **Param** Felder nicht betroffen.

Auf einem **Param**, müssen Sie angeben, die tatsächliche Adresse der Person, die **Param** , z. B. arbeiten möchten:

[!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]

Dies bedeutet, dass Sie nicht alle festlegen **Param** Felder für NULL-Werte, mit `outputColumn` Felder.

`SetFieldDirty` wird durch implementiert `DoFieldExchange`.

##  <a name="setfieldnull"></a>  CDaoRecordset::SetFieldNull

Rufen Sie diese Memberfunktion zum Felddatenmember des Recordset-Objekts als Null (insbesondere mit kein Wert) oder als nicht-Null-flag.

```
void SetFieldNull(
    void* pv,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Enthält die Adresse eines Datenmembers Feld in der Recordset oder NULL. Wenn der Wert NULL ist, werden alle Felddatenmember der Recordset gekennzeichnet. (NULL in C++ ist nicht identisch mit Null in der Terminologie von Datenbanken, d. h. "müssen keinen Wert.")

*bNull*<br/>
Legen Sie ungleich NULL, wenn es sich bei der Felddatenmember gekennzeichnet wird, als hätte er keine (Null) ist. Andernfalls 0, wenn der Feld-Datenmember ist, als nicht-Null gekennzeichnet wird.

### <a name="remarks"></a>Hinweise

`SetFieldNull` wird für Felder, die im gebundenen verwendet die `DoFieldExchange` Mechanismus.

Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) geändert" markiert. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits Werte oder Null sind. Wenn sie nicht für ein Feld Null ist, ist eine [CDaoException](../../mfc/reference/cdaoexception-class.md) ausgelöst.

Wenn Sie die doppelte Pufferung-Mechanismus, z. B. verwenden, wenn Sie ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert ein, rufen Sie möchten `SetFieldNull` mit *bNull* auf "true" festgelegt, um gekennzeichnet, die als Null. Wenn ein Feld wurde zuvor Null markiert, und jetzt Sie einen Wert fest möchten, legen Sie einfach den neuen Wert. Sie müssen nicht das Null-Flag mit entfernen `SetFieldNull`. Um zu bestimmen, ob das Feld NULL zulässig ist, rufen Sie [IsFieldNullable](#isfieldnullable).

Wenn Sie die doppelte Pufferung Mechanismus nicht verwenden, wird dann ändern den Wert des Felds nicht automatisch das Feld als geändert und nicht-Null festgelegt. Sie müssen insbesondere die Felder geändert und ungleich Null festlegen. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Feld Prüfung.

Der Mechanismus DFX setzt die Verwendung von PSEUDONULL. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).

> [!NOTE]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).

Verwenden NULL für das erste Argument der Funktion nur für die Funktion angewendet wird `outputColumn` Feldern nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf

[!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]

wird nur festgelegt, `outputColumn` Felder NULL. **Param** Felder nicht betroffen.

##  <a name="setfieldvalue"></a>  CDaoRecordset::SetFieldValue

Rufen Sie diese Memberfunktion um den Wert eines Felds oder die Position oder durch Ändern des Werts der Zeichenfolge festzulegen.

```
virtual void SetFieldValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetFieldValue(
    int nIndex,
    const COleVariant& varValue);

void SetFieldValue(
    LPCTSTR lpszName,
    LPCTSTR lpszValue);

void SetFieldValue(
    int nIndex,
    LPCTSTR lpszValue);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Namen eines Felds.

*varValue*<br/>
Ein Verweis auf eine [COleVariant](../../mfc/reference/colevariant-class.md) Objekt mit dem Wert, der der Inhalt des Feldes.

*nIndex*<br/>
Eine ganze Zahl, die die Ordnungsposition des Felds in die Recordset Fields-Sammlung (nullbasiert) darstellt.

*lpszValue*<br/>
Ein Zeiger auf eine Zeichenfolge, die mit dem Wert, der der Inhalt des Feldes.

### <a name="remarks"></a>Hinweise

Verwendung `SetFieldValue` und [GetFieldValue](#getfieldvalue) Sie Felder zur Laufzeit statt statisch zu binden von Spalten mit dynamisch binden die [DoFieldExchange](#dofieldexchange) Mechanismus.

Beachten Sie, dass Sie ein UNICODE-Recordset nicht erstellen, Sie entweder eine Form der verwenden müssen `SetFieldValue` , die keinen enthalten eine `COleVariant` -Parameter oder die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann erfolgen mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *LpszSrc* **,** *VtSrc* **)**  Form des Konstruktors mit *VtSrc* festgelegt `VT_BSTRT` (ANSI) oder mithilfe der `COleVariant` Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *LpszSrc* **,** *VtSrc* **)** mit *VtSrc* festgelegt `VT_BSTRT`.

Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in-DAO-Hilfe.

##  <a name="setfieldvaluenull"></a>  CDaoRecordset::SetFieldValueNull

Rufen Sie diese Memberfunktion, um das Feld auf einen Null-Wert festgelegt.

```
void SetFieldValueNull(int nIndex);
void SetFieldValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Felds im Recordset, für die Suche über den nullbasierten Index.

*Wert*<br/>
Der Name des Felds im Recordset, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

NULL in C++ ist nicht identisch mit Null, womit, in der datenbankterminologie "müssen keinen Wert."

Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in-DAO-Hilfe.

##  <a name="setlockingmode"></a>  CDaoRecordset::SetLockingMode

Rufen Sie diese Memberfunktion um den Typ der Sperre für das Recordset festzulegen.

```
void SetLockingMode(BOOL bPessimistic);
```

### <a name="parameters"></a>Parameter

*bPessimistic*<br/>
Ein Flag, das den Typ der Sperre angibt.

### <a name="remarks"></a>Hinweise

Wenn pessimistische Sperrung, gilt die 2 KB-Seite mit den Einträgen, die Sie bearbeiten, ist gesperrt, sobald Sie aufrufen, die `Edit` Member-Funktion. Die Seite ist nicht gesperrt, beim Aufrufen der `Update` oder `Close` Memberfunktion oder einer der Vorgänge verschieben oder suchen.

Bei der optimistischen Sperre wird verwendet, ist die 2 KB-Seite, die mit dem Datensatz gesperrt, nur verwendet werden, während der Aktualisierung des Datensatzes mit der `Update` Member-Funktion.

Wenn eine Seite gesperrt ist, kann kein anderer Benutzer die Datensätze auf derselben Seite bearbeiten. Wenn Sie aufrufen `SetLockingMode` und übergeben Sie einen Wert ungleich NULL und ein anderer Benutzer hat bereits die Seite gesperrt, eine Ausnahme ausgelöst, wenn Sie aufrufen `Edit`. Andere Benutzer können Daten aus gesperrte Seiten gelesen werden.

Wenn Sie aufrufen `SetLockingMode` rufen Sie mit dem Wert 0 (null) und höher `Update` während die Seite von einem anderen Benutzer gesperrt ist, wird eine Ausnahme auftritt. Um die Änderungen, die an Ihren Eintrag von einem anderen Benutzer (und alle Änderungen verwerfen), rufen Sie die `SetBookmark` Member-Funktion mit der Lesezeichenwert, der den aktuellen Datensatz.

Der Sperrmodus ist immer optimistische, bei der Arbeit mit ODBC-Datenquellen.

##  <a name="setparamvalue"></a>  CDaoRecordset::SetParamValue

Rufen Sie diese Memberfunktion um den Wert eines Parameters im Recordset zur Laufzeit festzulegen.

```
virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);

virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Die numerische Position des Parameters in der Querydef Parameters-Auflistung.

*var*<br/>
Der festzulegende Wert; finden Sie unter "Hinweise".

*Wert*<br/>
Der Name des Parameters, dessen Wert Sie festlegen möchten.

### <a name="remarks"></a>Hinweise

Der Parameter muss bereits als Teil der SQL-Zeichenfolge des Recordsets hergestellt haben. Sie können die Parameter nach Namen oder anhand der Indexposition in der Auflistung zugreifen.

Geben Sie den Wert für die festzulegende als eine `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md). Beachten Sie, dass, wenn Sie ein UNICODE-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann erfolgen mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** *LpszSrc* **,** *VtSrc* **)**  Form des Konstruktors mit *VtSrc* festgelegt `VT_BSTRT` (ANSI) oder mithilfe der `COleVariant` Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** *LpszSrc* **,** *VtSrc* **)** mit *VtSrc* festgelegt `VT_BSTRT`.

##  <a name="setparamvaluenull"></a>  CDaoRecordset::SetParamValueNull

Rufen Sie diese Memberfunktion um den Parameter auf einen Nullwert festzulegen.

```
void SetParamValueNull(int nIndex);
void SetParamValueNull(LPCTSTR lpszName);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der Index des Felds im Recordset, für die Suche über den nullbasierten Index.

*Wert*<br/>
Der Name des Felds im Recordset, für die Suche anhand des Namens.

### <a name="remarks"></a>Hinweise

NULL in C++ ist nicht identisch mit Null, womit, in der datenbankterminologie "müssen keinen Wert."

##  <a name="setpercentposition"></a>  CDaoRecordset:: SetPercentPosition

Rufen Sie diese Memberfunktion, um einen Wert festzulegen, der den ungefähren Standort des aktuellen Datensatzes in die Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset zu ändern.

```
void SetPercentPosition(float fPosition);
```

### <a name="parameters"></a>Parameter

*fPosition*<br/>
Eine Zahl zwischen 0 und 100.

### <a name="remarks"></a>Hinweise

Füllen Sie das Recordset bei der Arbeit mit einem Dynaset oder Recordset Momentaufnahme vom Typ zuerst durch Verschieben bis zum letzten Datensatz vor dem Aufruf `SetPercentPosition`. Wenn Sie aufrufen `SetPercentPosition` vor dem vollständig auffüllen das Recordset, datenverschiebung ist relativ zur Anzahl der Datensätze zugegriffen wird, wie durch den Wert der [GetRecordCount](#getrecordcount). Sie können bis zum letzten Datensatz verschieben durch Aufrufen von `MoveLast`.

Wenn Sie aufrufen `SetPercentPosition`, der Eintrag auf die ungefähre Position, die auf diesen Wert entsprechend zum aktuellen Thread.

> [!NOTE]
>  Aufrufen von `SetPercentPosition` zum Verschieben des aktuellen Datensatzes zu einem bestimmten Datensatz in einem Recordset wird nicht empfohlen. Rufen Sie die [SetBookmark](#setbookmark) Memberfunktion stattdessen.

Verwandte Informationen finden Sie im Thema "PercentPosition-Eigenschaft" in-DAO-Hilfe.

##  <a name="update"></a>  CDaoRecordset::Update

Rufen Sie nach einem Aufruf von dieser Memberfunktion die `AddNew` oder `Edit` Member-Funktion.

```
virtual void Update();
```

### <a name="remarks"></a>Hinweise

Dieser Aufruf ist erforderlich, zum Abschließen der `AddNew` oder `Edit` Vorgang.

Beide `AddNew` und `Edit` Bearbeitungspuffer, die in der befindet sich die hinzugefügten oder bearbeiteten Daten vorbereiten, für das Speichern in der Datenquelle. `Update` Speichert die Daten. Es werden nur die Felder, markiert oder geändert erkannt, dass aktualisiert.

Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Update` aufrufen (und der entsprechenden `AddNew` oder `Edit` aufrufen) Teil einer Transaktion.

> [!CAUTION]
> Wenn Sie aufrufen `Update` ohne zuerst Aufrufen von entweder `AddNew` oder `Edit`, `Update` löst eine `CDaoException`. Wenn Sie aufrufen `AddNew` oder `Edit`, rufen Sie `Update` vor dem Aufruf [MoveNext](#movenext) oder das Recordset oder die datenquellenverbindung zu schließen. Andernfalls sind Ihre Änderungen verloren gehen, ohne Benachrichtigung.

Der Datensatz bleibt gesperrt, ab dem Zeitpunkt, wenn das Recordset-Objekt in einer mehrbenutzerumgebung pessimistisch gesperrt ist, `Edit` wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz ist gesperrt und im Vergleich mit dem Datensatz, der bereits bearbeiteten, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen `Edit`, `Update` fehl und MFC eine Ausnahme auslöst. Sie können ändern, dass der Sperrmodus mit `SetLockingMode`.

> [!NOTE]
> Optimistische wird immer auf der externen Datenbank-Formate, z. B. ODBC und installierbaren ISAM verwendet.

Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate-Methode", "-Methode Delete", "Eigenschaft" LastModified ","Update-Methode"und"EditMode-Eigenschaft"in-DAO-Hilfe.

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)<br/>
[CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)<br/>
[CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)<br/>
