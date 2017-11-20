---
title: CDaoRecordset-Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
dev_langs: C++
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
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9742093585283350ce2c40ae533cc9e530d94bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdaorecordset-class"></a>CDaoRecordset-Klasse
Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDaoRecordset : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoRecordset::CDaoRecordset](#cdaorecordset)|Erstellt ein `CDaoRecordset`-Objekt.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[AddNew](#addnew)|Für das Hinzufügen eines neuen Datensatzes vorbereitet. Rufen Sie [Update](#update) das Hinzufügen abgeschlossen.|  
|[CDaoRecordset::CanAppend](#canappend)|Gibt einen Wert ungleich NULL, wenn das Recordset über neue Einträge hinzugefügt werden können die [AddNew](#addnew) Memberfunktion.|  
|[CDaoRecordset::CanBookmark](#canbookmark)|Gibt einen Wert ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.|  
|[CDaoRecordset::CanRestart](#canrestart)|Gibt NULL zurück, wenn [Requery](#requery) aufgerufen werden, um das Recordset Abfrage erneut ausführen.|  
|[CDaoRecordset::CanScroll](#canscroll)|Gibt einen Wert ungleich NULL, wenn Sie durch die Datensätze scrollen können zurück.|  
|[CDaoRecordset::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDaoRecordset::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|  
|[CDaoRecordset::Close](#close)|Schließt das Recordset.|  
|[CDaoRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang einen Bildlauf durchführen.|  
|[CDaoRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implements-DAO-Datensatzfeldaustausch (DFX).|  
|[CDaoRecordset::Edit](#edit)|Für die Änderungen an den aktuellen Datensatz vorbereitet. Rufen Sie **Update** um die Bearbeitung abzuschließen.|  
|[FillCache](#fillcache)|Füllt den gesamten oder einen Teil des lokalen Cache für ein Recordset-Objekt, das Daten aus einer ODBC-Datenquelle enthält.|  
|[CDaoRecordset::Find](#find)|Sucht das erste, Next, letzten oder vorherigen Speicherort einer bestimmten Zeichenfolge in einem Typ Dynaset-Recordset, das den angegebenen Kriterien und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindFirst](#findfirst)|Sucht nach dem ersten Datensatz in einem Dynaset oder-Diagramm nach der Momentaufnahme-Recordset, das den angegebenen Kriterien und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindLast](#findlast)|Sucht nach den letzten Datensatz in einem Dynaset oder-Diagramm nach der Momentaufnahme-Recordset, das den angegebenen Kriterien und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindNext](#findnext)|Sucht den nächsten Datensatz in einem Dynaset oder-Diagramm nach der Momentaufnahme-Recordset, das den angegebenen Kriterien und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindPrev](#findprev)|Sucht nach der vorherigen Datensatz in einem Dynaset oder-Diagramm nach der Momentaufnahme-Recordset, das den angegebenen Kriterien und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|Gibt die Nummer des aktuellen Datensatzes des Recordset-Objekts zurück.|  
|[CDaoRecordset:: GetBookmark](#getbookmark)|Gibt einen Wert, der das Lesezeichen auf einen Datensatz darstellt.|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|Gibt einen Wert, der angibt, die Anzahl der Datensätze in einem Typ Dynaset-Recordset, das mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden soll.|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|Gibt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden soll.|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Gibt eine `CString` für eine indizierte Tabellentyp verwendet, enthält den Namen des Indexes die meisten vor kurzem `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit des zugrunde liegenden Basistabelle eine `CDaoRecordset` Objekt erstellt wurde|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum und Uhrzeit der letzten Änderung am Entwurf von einem zugrunde liegenden Basistabelle eine `CDaoRecordset` Objekt.|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Gibt den Namen der Standard-Datenquelle zurück.|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, um die Standard-SQL-Zeichenfolge auszuführende abzurufen.|  
|[CDaoRecordset::GetEditMode](#geteditmode)|Gibt einen Wert, der den Status des bearbeiten für den aktuellen Datensatz angibt.|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in einem Recordset darstellt.|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurückgegeben in das Recordset.|  
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|Ruft die Anzahl der Indizes in einer Tabelle, die zugrunde liegende ein Recordset ab.|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Gibt verschiedene Arten von Informationen zu einem Index zurück.|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Um zu bestimmen, der den zuletzt hinzugefügten oder aktualisierte Datensatz verwendet.|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Gibt einen Wert, der den Typ der Sperre, der angibt während der Bearbeitung aktiviert ist.|  
|[CDaoRecordset::GetName](#getname)|Gibt eine `CString` mit dem Namen des Recordsets.|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|Ruft ab den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter Objekt gespeichert.|  
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|Gibt die Position des aktuellen Datensatzes als Prozentsatz der Gesamtanzahl von Datensätzen zurück.|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in einem Recordset-Objekt zugegriffen.|  
|[CDaoRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset verwendet.|  
|[CDaoRecordset::GetType](#gettype)|Wird aufgerufen, um den Typ eines Recordsets zu bestimmen:-Diagramm nach der Tabelle, Dynaset- oder Snapshot-Typ.|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Gibt eine `CString` mit dem Wert, der Daten überprüft werden, wie er in ein Feld eingegeben wird.|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Ruft den Text, der angezeigt wird, wenn eine Validierungsregel nicht erfüllt wird.|  
|[CDaoRecordset::IsBOF](#isbof)|Gibt ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es ist kein aktueller Datensatz vorhanden.|  
|[CDaoRecordset::IsDeleted](#isdeleted)|Gibt einen Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist.|  
|[CDaoRecordset::IsEOF](#iseof)|Gibt einen Wert ungleich NULL, wenn das Recordset hinter dem letzten Datensatz positioniert wurde wurde zurück. Es ist kein aktueller Datensatz vorhanden.|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz Null (kein Wert mit) ist zurück.|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz auf Null festgelegt werden kann (mit keinen Wert) zurück.|  
|[CDaoRecordset::IsOpen](#isopen)|Gibt NULL zurück, wenn [öffnen](#open) zuvor aufgerufen wurde.|  
|[CDaoRecordset::Move](#move)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|  
|[CDaoRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz im ersten Datensatz des Recordsets.|  
|[CDaoRecordset::MoveLast](#movelast)|Positioniert den aktuellen Datensatz im letzten Datensatz des Recordsets.|  
|[CDaoRecordset::MoveNext](#movenext)|Wird den aktuellen Datensatz auf den nächsten Datensatz im Recordset positioniert.|  
|[CDaoRecordset::MovePrev](#moveprev)|Positioniert den aktuellen Datensatz des vorherigen Datensatzes im Recordset.|  
|[CDaoRecordset:: Open](#open)|Erstellt einen neuen Datensatz aus einer Tabelle, eine Dynaset oder eine Momentaufnahme an.|  
|[CDaoRecordset::Requery](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|  
|[CDaoRecordset::Seek](#seek)|Sucht nach dem Datensatz in einem Typ indizierte Tabelle Recordset-Objekt, das die angegebenen Kriterien für den aktuellen Index und nutzt, die zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Legt die Nummer des aktuellen Datensatzes des Recordset-Objekts.|  
|[CDaoRecordset:: SetBookmark](#setbookmark)|Positioniert das Recordset auf einen Datensatz mit dem angegebenen Lesezeichen.|  
|[CDaoRecordset:: SetCacheSize](#setcachesize)|Legt einen Wert, der angibt, die Anzahl der Datensätze in einem Typ Dynaset-Recordset, das mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden soll.|  
|[CDaoRecordset:: SetCacheStart](#setcachestart)|Legt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden soll.|  
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|Wird aufgerufen, um einen Index für einen Tabellentyp Recordset festlegen.|  
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz, als geändert.|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds in den aktuellen Datensatz auf Null (kein Wert mit) fest.|  
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Legt den Wert eines Felds in einem Recordset fest.|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Legt den Wert eines Felds in einem Recordset auf Null fest. (Wenn kein Wert).|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Legt einen Wert, der den Typ der Sperren, um während der Bearbeitung vollzogen angibt.|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|Legt den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter Objekt gespeichert|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Legt den aktuellen Wert des angegebenen Parameters auf Null (kein Wert mit) fest.|  
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|Legt die Position des aktuellen Datensatzes an einem Speicherort entspricht einem Prozentsatz der Gesamtanzahl von Datensätzen in einem Recordset fest.|  
|[CDaoRecordset::Update](#update)|Schließt eine `AddNew` oder **bearbeiten** Vorgangs durch die neuen oder bearbeiteten Daten speichern, für die Datenquelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoRecordset:: M_bcheckcachefordirtyfields](#m_bcheckcachefordirtyfields)|Enthält ein Flag, der angibt, ob Felder automatisch als geändert markiert sind.|  
|[CDaoRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.|  
|[CDaoRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in der Recordsetklasse – die Anzahl von Parametern übergeben, mit die Abfrage des Recordsets|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Ein Zeiger auf die DAO-Schnittstelle, die zugrunde liegenden Recordsetobjekt.|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Die Quelldatenbank für dieses Resultset. Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|Enthält eine Zeichenfolge verwendet, um eine SQL-Konstrukt **, in denen** Anweisung.|  
|[CDaoRecordset::m_strSort](#m_strsort)|Enthält eine Zeichenfolge verwendet, um eine SQL-Konstrukt **ORDER BY** Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Bekannt als "Recordsets" `CDaoRecordset` Objekte sind in den folgenden drei Versionen verfügbar:  
  
-   Tabellentyp Recordsets stellen eine Basistabelle, die Sie verwenden können, zu untersuchen, hinzufügen, ändern oder Löschen von Datensätzen aus einer einzelnen Datenbanktabelle dar.  
  
-   Recordsets vom Typ Dynaset sind das Ergebnis einer Abfrage, die aktualisierbare Datensätze haben kann. Diese Recordsets sind bei einer Gruppe von Datensätzen, die Sie zum untersuchen, hinzufügen, ändern oder Löschen von Datensätzen aus einem zugrunde liegenden Datenbanktabelle oder Tabellen verwenden können. Recordsets vom Typ Dynaset können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten.  
  
-   Momentaufnahme-Type-Recordsets sind eine statische Kopie einer Gruppe von Datensätzen, die Sie zum Suchen von Daten oder zum Generieren von Berichten verwenden können. Diese Datensätze können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten, aber nicht aktualisiert werden.  
  
 Jede Form des Recordsets stellt einen Satz von Datensätzen, die behoben werden, zu dem Zeitpunkt, die das Recordset geöffnet ist. Wenn Sie einen zu einem Datensatz in einem Recordset-Diagramm nach der Tabelle oder ein Recordset Dynaset-Typ Bildlauf, gibt es Änderungen auf den Eintrag, nachdem das Recordset, die von anderen Benutzern oder von anderen Recordsets in Ihrer Anwendung geöffnet wird wieder. (Ein Recordset-Diagramm nach der Momentaufnahme kann nicht aktualisiert werden.) Sie können `CDaoRecordset` direkt oder leiten Sie eine anwendungsspezifische Recordsetklasse von `CDaoRecordset`. Anschließend können Sie:  
  
-   Führen Sie einen Bildlauf durch die Datensätze.  
  
-   Legen Sie einen Index, und suchen Sie schnell für Datensätze mit [Seek](#seek) (nur Tabellentyp Recordsets).  
  
-   Suchen nach Datensätzen, die basierend auf einem Vergleich von Zeichenfolgen: "<","\<=", "=" "> =", oder ">" (Dynaset und Recordsets Snapshot-Typ).  
  
-   Zum Aktualisieren Sie der Datensätze, und geben Sie einen Sperrmodus (mit Ausnahme der Momentaufnahme-Type-Recordsets).  
  
-   Filtern Sie das Recordset, um die Datensätze zu beschränken, damit aus den verfügbaren für die Datenquelle ausgewählt.  
  
-   Sortieren Sie das Recordset.  
  
-   Parametrisieren Sie das Recordset, um seine Auswahl mit Informationen, die erst zur Laufzeit bekannt anpassen.  
  
 Klasse `CDaoRecordset` stellt eine Schnittstelle ähnelt der Klasse `CRecordset`. Der Hauptunterschied besteht darin, Klasse `CDaoRecordset` greift auf Daten über eine (Datenzugriffsobjekt) basierend auf OLE. Klasse `CRecordset` greift auf das DBMS durch Open Database Connectivity (ODBC) und einem ODBC-Treiber für diese DBMS.  
  
> [!NOTE]
>  DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf der Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können dennoch den Zugriff auf ODBC-Datenquellen mit den DAO-Klassen; DAO-Klassen bieten im Allgemeinen überlegene Funktionen auf, da sie mit dem Microsoft Jet-Datenbankmodul spezifisch sind.  
  
 Sie können entweder `CDaoRecordset` direkt oder leiten Sie eine Klasse von `CDaoRecordset`. Um ein Recordset-Klasse in beiden Fällen zu verwenden, öffnen Sie eine Datenbank, und erstellen Sie einem Recordset-Objekt, und übergeben dem Konstruktor einen Zeiger auf die `CDaoDatabase` Objekt. Sie können auch erstellen eine `CDaoRecordset` Objekts, sodass Sie MFC ein temporäres Kennwort zu erstellen `CDaoDatabase` Objekt für Sie. Rufen Sie dann des Recordsets [öffnen](#open) Member-Funktion, die angibt, ob das Objekt ein Tabellentyp Recordset, ein Recordset Dynaset-Typ oder ein Recordset Snapshot-Typ ist. Aufrufen von **öffnen** wählt Daten aus der Datenbank und ruft den ersten Datensatz.  
  
 Verwenden Sie das Objekt, Member, Funktionen und Datenmember, um durch die Datensätze scrollen und diese verarbeiten. Die verfügbaren Vorgänge richten sich nach, ob das Objekt ein Tabellentyp Recordset, ein Recordset Dynaset-Typ oder ein Recordset Snapshot-Typ ist, und ob es sich um aktualisierbar oder schreibgeschützt werden – dies hängt von der Funktion der Datenbank oder der Open Database Connectivity (ODBC) die Datenquelle. Datensätze zu aktualisieren, die wurde geändert oder hinzugefügt werden, da die **öffnen** aufzurufen, rufen Sie des Objekts [Requery](#requery) Memberfunktion. Rufen Sie des Objekts **schließen** Member-Funktion und zerstören Sie das Objekt aus, wenn Sie damit fertig sind.  
  
 `CDaoRecordset`DAO-Datensatzfeldaustausch (DFX), unterstützen das Lesen und Aktualisieren von Datensatzfelder durch typsicheren C++ Mitglieder verwendet Ihre `CDaoRecordset` oder `CDaoRecordset`-Klasse. Dynamisches Binden von Spalten in einer Datenbank können Sie auch implementieren, ohne mit den DFX Mechanismus [GetFieldValue](#getfieldvalue) und [SetFieldValue](#setfieldvalue).  
  
 Verwandte Informationen finden Sie im Thema "Recordset-Objekt" DAO-Hilfe.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="addnew"></a>AddNew  
 Rufen Sie diese Memberfunktion, um einen neuen Datensatz zu einem Recordset-Diagramm nach der Tabelle oder Dynaset hinzuzufügen.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Felder des Datensatzes sind anfänglich Null. (In der datenbankterminologie von-Null bedeutet "kein Wert having" und entspricht nicht dem als **NULL** in C++.) Um den Vorgang abzuschließen, rufen Sie die [Update](#update) Memberfunktion. **Update** speichert die Änderungen an der Datenquelle.  
  
> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten, und führen Sie einen zu einem anderen Datensatz ohne Aufruf Bildlauf **Update**, Ihre Änderungen gehen verloren, ohne Warnung.  
  
 Wenn Sie einen Datensatz durch den Aufruf zu einem Typ Dynaset Recordset hinzufügen [AddNew](#addnew), der Datensatz ist im Recordset angezeigt und enthalten in der zugrunde liegenden Tabelle, in denen sichtbar zu einer neuen `CDaoRecordset` Objekte.  
  
 Die Position des neuen Datensatzes hängt vom Typ des Recordsets ab:  
  
-   In einem Dynaset-Typ ist Recordset, wo der neue Datensatz eingefügt wird nicht garantiert. Dieses Verhalten ist mit Microsoft Jet 3.0 aus Gründen der Leistung und Parallelität. Wenn Ihr Ziel ist dem neu hinzugefügten Datensatz zum aktuellen Datensatz vornehmen, erhalten Sie das Lesezeichen des letzten Datensatzes geändert und zu diesem Lesezeichen verschieben:  
  
 [!code-cpp[NVC_MFCDatabase#1](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   In einem Tabellentyp Recordset, für die ein Index angegeben wurde, werden die Datensätze entsprechend ihrer Position in der Sortierreihenfolge zurückgegeben. Wenn kein Index angegeben wurden, werden neue Datensätze am Ende des Recordset-Objekts zurückgegeben.  
  
 Der Datensatz, der vor der aktuellen wurde `AddNew` aktuelle bleibt. Wenn Sie den neuen Eintrag aktuelle erstellen möchten, und das Recordset Lesezeichen, Aufruf unterstützt [SetBookmark](#setbookmark) auf das Lesezeichen, die durch die Einstellung der LastModified-Eigenschaft von der zugrunde liegenden DAO-Recordset-Objekt identifiziert. Auf diese Weise eignet sich zur Bestimmung des Wert für den Leistungsindikator (automatisch inkrementierten) Felder in einem Datensatz hinzugefügt. Weitere Informationen finden Sie unter [GetLastModifiedBookmark](#getlastmodifiedbookmark).  
  
 Wenn die Datenbank Transaktionen unterstützt, können Sie machen die `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie in der Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Beachten Sie, die Sie aufrufen sollte [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) vor dem Aufruf `AddNew`.  
  
 Es ist nicht zulässig, rufen Sie `AddNew` für ein Recordset, deren [öffnen](#open) Memberfunktion nicht aufgerufen wurde. Ein `CDaoException` wird ausgelöst, wenn Sie aufrufen `AddNew` für ein Recordset, die angefügt werden kann. Sie können bestimmen, ob das Recordset aktualisierbar, durch den Aufruf ist [CanAppend](#canappend).  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld dirty automatisch, sodass Sie nur selten aufrufen müssen [SetFieldDirty](#setfielddirty) selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten explizit aktualisiert oder unabhängig davon eingefügt werden der Wert in das felddatenelement ist. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDO-NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, ist dann ändern den Wert des Felds nicht automatisch das Feld als modifizierte festgelegt. In diesem Fall werden müssen explizit das Feld dirty festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
> [!NOTE]
>  Wenn Datensätze doppelt gepuffert werden (d. h. automatische Überprüfung aktiviert ist), Aufrufen von `CancelUpdate` wird die Membervariablen mit den Werten, die vor diesem Unternehmen arbeitete wiederherstellen `AddNew` oder **bearbeiten** aufgerufen wurde.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate Method", "LastModified-Eigenschaft" und "EditMode-Eigenschaft" DAO-Hilfe.  
  
##  <a name="canappend"></a>CDaoRecordset::CanAppend  
 Rufen Sie diese Memberfunktion, um festzustellen, ob zuvor geöffnete Recordset Sie beim Hinzufügen neuer Einträge durch Aufrufen können der [AddNew](#addnew) Memberfunktion.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Hinzufügen von neuen Datensätzen; andernfalls 0. `CanAppend`Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet wurde.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Append-Methode" DAO-Hilfe.  
  
##  <a name="canbookmark"></a>CDaoRecordset::CanBookmark  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das zuvor geöffnete Recordset Datensätze mithilfe von Lesezeichen einzeln kennzeichnen Sie können.  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Recordset Lesezeichen, andernfalls 0 unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Bei Verwendung von Recordsets, die vollkommen auf von Microsoft Jet-Datenbank-Engine-Tabellen basieren können außer in-Diagramm nach der Momentaufnahme-Recordsets als Durchführen eines Bildlaufs vorwärts-Recordsets gekennzeichnet werden Lesezeichen verwendet werden. Andere Datenbankprodukte (externe ODBC-Datenquellen) nicht von Lesezeichen unterstützt.  
  
 Verwandte Informationen finden Sie im Thema "Bookmarkable-Eigenschaft" DAO-Hilfe.  
  
##  <a name="cancelupdate"></a>CDaoRecordset::CancelUpdate  
 Die `CancelUpdate` Memberfunktion bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn eine Anwendung ruft z. B. die **bearbeiten** oder `AddNew` Memberfunktion und nicht aufgerufen [Update](#update), `CancelUpdate` bricht alle Änderungen, die nach **Bearbeiten**oder `AddNew` aufgerufen wurde.  
  
> [!NOTE]
>  Wenn Datensätze doppelt gepuffert werden (d. h. automatische Überprüfung aktiviert ist), Aufrufen von `CancelUpdate` wird die Membervariablen mit den Werten, die vor diesem Unternehmen arbeitete wiederherstellen `AddNew` oder **bearbeiten** aufgerufen wurde.  
  
 Es ist keine **bearbeiten** oder `AddNew` Vorgang Ausstehend "," `CancelUpdate` bewirkt, dass MFC eine Ausnahme auslöst. Rufen Sie die [GetEditMode](#geteditmode) Member-Funktion, um festzustellen, ob es ist noch nicht abgeschlossen, die abgebrochen werden kann.  
  
 Verwandte Informationen finden Sie im Thema "CancelUpdate Method" DAO-Hilfe.  
  
##  <a name="canrestart"></a>CDaoRecordset::CanRestart  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset ermöglicht das Neustarten der Abfrage (um ihre Datensätze aktualisieren) durch Aufrufen der **Requery** Memberfunktion.  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL **Requery** kann aufgerufen werden, führen Sie das Recordset Abfrage erneut aus, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Tabellentyp Recordsets unterstützen keine **Requery**.  
  
 Wenn **Requery** wird nicht unterstützt wird, rufen [schließen](#close) dann [öffnen](#open) zum Aktualisieren der Daten. Sie können Aufrufen **Requery** zum Aktualisieren von einem Recordset-Objekt zugrunde liegenden Parameterabfrage nach dem die Parameterwerte geändert wurden.  
  
 Verwandte Informationen finden Sie im Thema "Startfähige Property" in der DAO-Hilfe.  
  
##  <a name="canscroll"></a>CDaoRecordset::CanScroll  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset ermöglicht das Durchführen eines Bildlaufs.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn durch die Datensätze, andernfalls 0 gescrollt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Beim Aufrufen [öffnen](#open) mit **DbForwardOnly**, das Recordset nur vorwärts.  
  
 Verwandte Informationen finden Sie im Thema "Positionieren des aktuellen Zeiger mit DAO" DAO-Hilfe.  
  
##  <a name="cantransact"></a>CDaoRecordset::CanTransact  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset Transaktionen ermöglicht.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn die zugrunde liegenden Datenquelle Transaktionen, andernfalls 0 unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Transaktionen Property" in der DAO-Hilfe.  
  
##  <a name="canupdate"></a>CDaoRecordset::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das Recordset aktualisiert werden kann.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Recordset aktualisiert werden kann (hinzufügen, aktualisieren und Löschen von Datensätzen), andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Recordset möglicherweise schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist oder wenn Sie angegeben **DbReadOnly** für `nOptions` beim Aufruf [öffnen](#open) für das Recordset.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Method bearbeiten", "Method löschen", "Update-Methode" und "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset  
 Erstellt ein `CDaoRecordset`-Objekt.  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt oder den Wert **NULL**. Wenn dies nicht der **NULL** und `CDaoDatabase` des Objekts **öffnen** Memberfunktion nicht aufgerufen wurde, um der Datenquelle hergestellt werden, wird das Recordset versucht wird, öffnen Sie während der eigenen [öffnen ](#open) aufrufen. Wenn Sie übergeben **NULL**, `CDaoDatabase` Objekt wird erstellt und für Sie verwenden die Datenquelleninformationen, die Sie angegeben werden, wenn Sie vom Recordset-Klasse abgeleitet verbunden `CDaoRecordset`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder `CDaoRecordset` direkt oder ableiten eine Klasse anwendungsspezifische `CDaoRecordset`. Klassen-Assistent können Sie die Recordset-Klassen abgeleitet werden.  
  
> [!NOTE]
>  Beim Ableiten einer `CDaoRecordset` Klasse, die abgeleitete Klasse muss einen eigenen Konstruktor bereitstellen. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CDaoRecordset::CDaoRecordset`, die entsprechenden Parametern zusammen an sie übergibt.  
  
 Übergeben Sie **NULL** an Ihre recordsetkonstruktor haben eine `CDaoDatabase` Objekt erstellt und automatisch für Sie verbunden. Dies ist eine hilfreiche Abkürzung, die keine erforderlich zum Erstellen und Verbinden einer `CDaoDatabase` Objekt vor dem Erstellen des Recordsets. Wenn die `CDaoDatabase` Objekt ist nicht geöffnet ist, eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt auch erstellt werden, die der Arbeitsbereich "Standard" verwendet. Weitere Informationen finden Sie unter [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).  
  
##  <a name="close"></a>CDaoRecordset::Close  
 Schließen einer `CDaoRecordset` Objekt entfernt es aus der Auflistung der geöffneten Recordsets in der zugehörigen Datenbank.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Da **schließen** nicht zerstört die `CDaoRecordset` -Objekt, Sie können das Objekt durch den Aufruf wiederverwenden **öffnen** auf derselben Datenquelle oder einer anderen Datenquelle.  
  
 Alle ausstehenden [AddNew](#addnew) oder [bearbeiten](#edit) -Anweisungen abgebrochen und alle anstehenden Transaktionen zurückgesetzt. Wenn Sie ausstehende Ergänzungen oder Änderungen beibehalten möchten, rufen Sie [Update](#update) vor dem Aufruf **schließen** für jede Recordset.  
  
 Sie können Aufrufen **öffnen** erneut nach dem Aufruf **schließen**. Dadurch können Sie das Recordset-Objekt wiederverwenden. Eine bessere Alternative besteht darin Aufrufen [Requery](#requery), sofern dies möglich.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" DAO-Hilfe.  
  
##  <a name="delete"></a>CDaoRecordset::Delete  
 Rufen Sie diese Memberfunktion um den aktuellen Datensatz in einem geöffneten Dynaset oder Tabellentyp Recordset-Objekt zu löschen.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem erfolgreichen Löschvorgang das Recordset-Felddatenmember werden auf einen Null-Wert festgelegt, und müssen Sie explizit eine der Recordset Navigation Memberfunktionen aufrufen ( [verschieben](#move), [Seek](#seek), [ SetBookmark](#setbookmark)usw.) um den gelöschten Datensatz zu verschieben. Beim Löschen von Datensätzen aus einem Recordset es muss ein aktueller Datensatz des Recordsets vor dem Aufruf **löschen**ist, andernfalls löst MFC eine Ausnahme.  
  
 **Löschen Sie** entfernt den aktuellen Datensatz ab und wandelt diesen kann nicht zugegriffen werden. Obwohl Sie nicht bearbeiten oder den gelöschten Datensatz verwenden, bleibt die aktuelle. Sobald Sie mit einem anderen Datensatz wechseln, können nicht allerdings Sie den gelöschten Datensatz aktuelle erneut vornehmen.  
  
> [!CAUTION]
>  Das Recordset aktualisierbar sein muss, und es muss ein gültiger Datensatz aktuell im Recordset beim Aufrufen **löschen**. Angenommen, wenn Sie einen Datensatz löschen, aber kein Bildlauf zu einem neuen Datensatz vor dem Aufruf **löschen** erneut **löschen** löst eine [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Sie können einen Datensatz rückgängig machen, wenn Sie Transaktionen verwenden, und Sie rufen die [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Memberfunktion. Wenn die Basistabelle der Primärtabelle ist in einer Cascade Beziehung löschen, das Löschen des aktuellen Datensatzes möglicherweise auch einen oder mehrere Datensätze in einer Fremdschlüsseltabelle. Weitere Informationen finden Sie unter der Definition "Cascade löschen" DAO-Hilfe.  
  
 Im Gegensatz zu `AddNew` und **bearbeiten**, einen Aufruf von **löschen** ist nicht gefolgt von einem Aufruf von **Update**.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Method bearbeiten", "Method löschen", "Update-Methode" und "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="dofieldexchange"></a>CDaoRecordset:: DoFieldExchange  
 Das Framework ruft diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern eines Recordset-Objekt und den entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch an.  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Enthält einen Zeiger auf eine `CDaoFieldExchange` Objekt. Das Framework wird bereits dieses Objekt eingerichtet haben, geben Sie einen Kontext für das Feld Austauschvorgang durch.  
  
### <a name="remarks"></a>Hinweise  
 Außerdem wird Ihre Parameterdatenmember bindet, ggf. Parameterplatzhalter in der SQL-Anweisungszeichenfolge für die Auswahl des Recordsets. Der Austausch von Felddaten, DAO-Datensatzfeldaustausch (DFX), aufgerufen funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes für die Datenquelle und aus dem Datensatz in der Datenquelle auf das Recordsetobjekt. Wenn Sie Spalten dynamisch binden, müssen Sie nicht implementieren `DoFieldExchange`.  
  
 Die einzige Aktion, die Sie ergreifen müssen normalerweise implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse zum Erstellen einer Klasse mit dem Klassen-Assistenten, und geben Sie den Namen und Datentypen von den Felddatenmembern ist. Sie können auch Code hinzufügen, in was ClassWizard geschrieben, um Parameterdatenmember anzugeben. Wenn alle Felder sind dynamisch gebunden werden, wird diese Funktion inaktiv sein, es sei denn, Sie Parameterdatenmember angeben.  
  
 Wenn Sie mit ClassWizard abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` , die im folgende Beispiel ähnelt:  
  
 [!code-cpp[NVC_MFCDatabase#2](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>CDaoRecordset::Edit  
 Rufen Sie diese Memberfunktion zum Zulassen von Änderungen an den aktuellen Datensatz.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Hinweise  
 Sobald Sie rufen die **bearbeiten** Memberfunktion ist, Änderungen an Feldern des aktuellen Datensatzes in den Kopierpuffer kopiert werden. Nachdem Sie die gewünschten Änderungen auf den Datensatz vorgenommen haben, rufen **Update** zum Speichern der Änderungen. **Bearbeiten Sie** speichert die Werte der Datenelemente für das Recordset. Beim Aufrufen **bearbeiten**, nehmen Änderungen vor, und rufen dann **bearbeiten** erneut, die Werte des Datensatzes werden wiederhergestellt, was sie vor dem ersten wären **bearbeiten** aufrufen.  
  
> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten, und führen Sie dann auf jeden Vorgang, der in einem anderen Datensatz ohne den ersten Aufruf verschiebt **Update**, Ihre Änderungen gehen verloren, ohne Warnung. Wenn Sie das Recordset oder die übergeordnete Datenbank schließen, wird darüber hinaus der bearbeitete Datensatz ohne Warnung verworfen.  
  
 In einigen Fällen empfiehlt es sich um eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Zu diesem Zweck rufen `SetFieldNull` mit einem Parameter des **"true"** , markieren Sie das Feld Null; Dies bewirkt auch, dass die Spalte aktualisiert werden. Wenn Sie wünschen, dass ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert hat, rufen Sie `SetFieldDirty` mit einem Parameter des **"true"**. Dies funktioniert auch, wenn das Feld den Wert Null war.  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld dirty automatisch, sodass Sie nur selten aufrufen müssen [SetFieldDirty](#setfielddirty) selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten explizit aktualisiert oder unabhängig davon eingefügt werden der Wert in das felddatenelement ist. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDO-NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, ist dann ändern den Wert des Felds nicht automatisch das Feld als modifizierte festgelegt. In diesem Fall werden müssen explizit das Feld dirty festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
 Der Datensatz bleibt gesperrt, ab dem Zeitpunkt, wenn das Recordset-Objekt in einer mehrbenutzerumgebung pessimistisch gesperrt ist, **bearbeiten** wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz gesperrt und mit dem Datensatz der vorab bearbeitete verglichen werden, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen **bearbeiten**, **Update** fehl und MFC eine Ausnahme auslöst. Sie können ändern, dass der Sperrmodus mit `SetLockingMode`.  
  
> [!NOTE]
>  Eingeschränktes Sperren wird immer auf externe Datenbank-Formaten, z. B. ODBC und installierbaren ISAM verwendet.  
  
 Der aktuelle Datensatz bleibt nach dem Aufruf von aktuellen **bearbeiten**. Aufzurufende **bearbeiten**, muss ein aktueller Datensatz vorhanden sein. Wenn es kein aktueller Datensatz ist oder das Recordset nicht auf eine offene Tabellentyp oder Typ Dynaset Recordset-Objekt verwiesen wird, tritt eine Ausnahme auf. Aufrufen von **bearbeiten** bewirkt, dass eine `CDaoException` in den folgenden Situationen ausgelöst:  
  
-   Es ist kein aktueller Datensatz vorhanden.  
  
-   Die Datenbank oder ein Recordset ist schreibgeschützt.  
  
-   Es sind keine Felder im Datensatz aktualisiert.  
  
-   Die Datenbank oder ein Recordset wurde für die ausschließliche Verwendung von einem anderen Benutzer geöffnet.  
  
-   Ein anderer Benutzer hat die Seite mit Ihren Eintrag gesperrt.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **bearbeiten** Teil einer Transaktion aufrufen. Beachten Sie, die Sie aufrufen sollte `CDaoWorkspace::BeginTrans` vor dem Aufruf **bearbeiten** und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf `CDaoWorkspace::CommitTrans` ist kein Ersatz für den Aufruf von **Update** zum Abschließen der **bearbeiten** Vorgang. Weitere Informationen über Transaktionen finden Sie in der Klasse `CDaoWorkspace`.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Method bearbeiten", "Method löschen", "Update-Methode" und "Aktualisierbare Property" in der DAO-Hilfe.  
  
##  <a name="fillcache"></a>FillCache  
 Rufen Sie diese Memberfunktion, um eine angegebene Anzahl von Datensätzen aus dem Recordset zwischenzuspeichern.  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pSize`  
 Gibt die Anzahl der Zeilen im Cache zu füllen. Wenn Sie diesen Parameter weglassen, wird der Wert durch die Einstellung der Eigenschaft CacheSize für das zugrunde liegende DAO-Objekt bestimmt.  
  
 `pBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) angeben eines Lesezeichens. Der Cache wird aus dem Datensatz, der durch dieses Lesezeichen angegeben ab gefüllt. Wenn Sie diesen Parameter weglassen, wird der Cache gefüllt beginnend mit des Datensatzes von der CacheStart-Eigenschaft, der das zugrunde liegende DAO-Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Das Zwischenspeichern verbessert die Leistung einer Anwendung, die abgerufen oder abruft, liest Daten von einem Remoteserver. Ein Cache ist Speicherplatz im lokalen Speicher, der das zuletzt auf der Annahme, dass die Daten wahrscheinlich erneut angefordert werden, während die Anwendung ausgeführt wird vom Server abgerufenen Daten enthält. Wenn Daten angefordert werden, überprüft der Microsoft Jet-Datenbankmodul den Cache für die Daten zunächst statt es vom Server, die mehr Zeit in Anspruch abgerufen. Mit nicht-ODBC-Datenquellen Zwischenspeichern von Daten hat keine Auswirkungen, wie die Daten nicht im Cache gespeichert ist.  
  
 Anstatt zu warten, für den Cache mit Datensätzen gefüllt werden soll, wenn der Abrufvorgang ausgeführt wird, können Sie explizit den Cache zu einem beliebigen Zeitpunkt ausfüllen, durch Aufrufen der `FillCache` Memberfunktion. Dies ist eine schnellere Methode zum Auffüllen des Cache da `FillCache` ruft mehrere Datensätze auf einmal statt jeweils einzeln ab. Z. B. während jeweils eine Seite mit Datensätzen angezeigt wird, dass Ihre Anwendungsaufruf `FillCache` beim Abrufen der nächsten Seite mit Datensätzen.  
  
 Eine ODBC-Datenbank mit Recordset-Objekte zugegriffen haben einen lokalen Cache. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt aus der remote-Datenquelle, und rufen Sie anschließend die `SetCacheSize` und `SetCacheStart` Memberfunktionen des Recordsets. Wenn `lSize` und *lBookmark* erstellen Sie einen Bereich, die teilweise oder vollständig außerhalb des Bereichs von angegebenen `SetCacheSize` und `SetCacheStart`, der Teil des Recordsets außerhalb dieses Bereichs wird ignoriert, und ist nicht in den Cache geladen. Wenn `FillCache` anfordert, mehrere Datensätze als verbleiben in der Remotedatenquelle, nur die verbleibenden Einträge abgerufen werden und keine Ausnahme ausgelöst wird.  
  
 Datensätze, die aus dem Cache abgerufenen spiegeln nicht gleichzeitig auf die Quelldaten von anderen Benutzern vorgenommene Änderungen.  
  
 `FillCache`Ruft nur Datensätze, die nicht bereits im Cache ab. Aufrufen, um ein Update aller zwischengespeicherten Daten zu erzwingen, die `SetCacheSize` Memberfunktion mit einem `lSize` Parameter gleich 0 (null) aufrufen `SetCacheSize` erneut mit der `lSize` Parameter gleich der Größe des Caches Sie ursprünglich angefordert hatten, und rufen dann `FillCache`.  
  
 Verwandte Informationen finden Sie im Thema "Zwischenspeichergröße" DAO-Hilfe.  
  
##  <a name="find"></a>CDaoRecordset::Find  
 Rufen Sie diese Memberfunktion zum Suchen einer bestimmten Zeichenfolge in einem Typ Dynaset oder Snapshot-Recordset, das mit einem Vergleichsoperator.  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 *lFindType*  
 Ein Wert, der angibt, der des Typs des gewünschten Suchvorgang. Mögliche Werte sind:  
  
- **AFX_DAO_NEXT** die nächste Position einer übereinstimmenden Zeichenfolge suchen.  
  
- **AFX_DAO_PREV** suchen Sie den vorherigen Speicherort des einer übereinstimmenden Zeichenfolge.  
  
- **AFX_DAO_FIRST** suchen Sie den ersten Speicherort eines einer übereinstimmenden Zeichenfolge.  
  
- **AFX_DAO_LAST** suchen Sie den letzten Speicherort einer übereinstimmenden Zeichenfolge.  
  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL­Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCDatabase#3](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie ersten, nächsten, vorherigen oder letzte Instanz der Zeichenfolge. **Suchen** ist eine virtuelle Funktion, damit Sie außer Kraft setzen und eine eigene Implementierung hinzufügen können. Die `FindFirst`, `FindLast`, `FindNext`, und `FindPrev` Memberfunktionen rufen die **suchen** Memberfunktion ist, damit Sie verwenden können **suchen** zum Steuern des Verhaltens von Vorgängen für alle suchen .  
  
 Um einen Datensatz in einem Recordset-Diagramm nach der Tabelle zu suchen, rufen Sie die [Seek](#seek) Memberfunktion.  
  
> [!TIP]
>  Je kleiner der Satz von Datensätzen stehen Ihnen, die effektiver **suchen** werden. Im Allgemeinen und insbesondere mit ODBC-Daten ist es besser, eine neue Abfrage zu erstellen, die nur Datensätze abruft, die Sie möchten.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" DAO-Hilfe.  
  
##  <a name="findfirst"></a>CDaoRecordset::FindFirst  
 Rufen Sie diese Memberfunktion um den ersten Datensatz zu suchen, der einer angegebenen Bedingung entspricht.  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL­Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindFirst` Memberfunktion beginnt die Suche vom Anfang des Recordsets und Suchvorgänge bis zum Ende des Recordsets.  
  
 Wenn alle enthalten sein, die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) eines der Verschiebevorgänge verwenden, um von Datensatz zu Datensatz verschoben, werden sollen. Um einen Datensatz in einem Recordset-Diagramm nach der Tabelle zu suchen, rufen Sie die `Seek` Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, die Zeiger für den aktuellen Datensatz unbestimmt ist, ist und `FindFirst` gibt 0 (null) zurück. Wenn das Recordset mehrere Datensätze enthält, die die Kriterien erfüllt `FindFirst` sucht das erste Vorkommen `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, müssen Sie zum Speichern der Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie mit einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.  
  
 Die **suchen** Memberfunktionen zu suchen, in den Speicherort, und klicken Sie auf die Richtung, in der folgenden Tabelle angegeben:  
  
|Suchen von Vorgängen|Beginnen|Suchrichtung|  
|---------------------|-----------|----------------------|  
|`FindFirst`|Beginn der Datensatzgruppe|Ende des Recordsets|  
|`FindLast`|Ende des Recordsets|Beginn der Datensatzgruppe|  
|`FindNext`|Aktueller Datensatz|Ende des Recordsets|  
|**FindPrevious**|Aktueller Datensatz|Beginn der Datensatzgruppe|  
  
> [!NOTE]
>  Beim Aufruf `FindLast`, das Microsoft Jet-Datenbankmodul füllt das Recordset vollständig vor Beginn der Suche, wenn dies nicht bereits ausgeführt wurde. Die erste Suche dauert länger als die nachfolgenden Suchvorgänge.  
  
 Mithilfe einer der Vorgänge suchen entspricht nicht dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt, die ungleich NULL ist, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger an einem gültigen Datensatz positionieren.  
  
-   Sie können kein Suchvorgangs mit einem Vorwärtscursor Durchführen eines Bildlaufs-Diagramm nach der Momentaufnahme-Recordset.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann übereinstimmenden Datensätzen nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise feststellen, die Operationen mit langsam ist, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte abrufen indizierte Datensätze.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" DAO-Hilfe.  
  
##  <a name="findlast"></a>CDaoRecordset::FindLast  
 Rufen Sie diese Memberfunktion um den letzten Datensatz zu suchen, der einer angegebenen Bedingung entspricht.  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL­Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindLast` Memberfunktion beginnt die Suche am Ende des Recordsets und sucht rückwärts bis zum Anfang des Recordsets.  
  
 Wenn alle enthalten sein, die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) eines der Verschiebevorgänge verwenden, um von Datensatz zu Datensatz verschoben, werden sollen. Um einen Datensatz in einem Recordset-Diagramm nach der Tabelle zu suchen, rufen Sie die `Seek` Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, die Zeiger für den aktuellen Datensatz unbestimmt ist, ist und `FindLast` gibt 0 (null) zurück. Wenn das Recordset mehrere Datensätze enthält, die die Kriterien erfüllt `FindFirst` sucht das erste Vorkommen `FindNext` sucht die nächste Instanz nach dem ersten Vorkommens und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie mit einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen entspricht nicht dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt, die ungleich NULL ist, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger an einem gültigen Datensatz positionieren.  
  
-   Sie können kein Suchvorgangs mit einem Vorwärtscursor Durchführen eines Bildlaufs-Diagramm nach der Momentaufnahme-Recordset.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann übereinstimmenden Datensätzen nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise feststellen, die Operationen mit langsam ist, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte abrufen indizierte Datensätze.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" DAO-Hilfe.  
  
##  <a name="findnext"></a>CDaoRecordset::FindNext  
 Rufen Sie diese Memberfunktion um den nächsten Datensatz zu suchen, der einer angegebenen Bedingung entspricht.  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL­Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindNext` Memberfunktion beginnt die Suche am aktuellen Datensatz und durchsucht am Ende des Recordsets.  
  
 Wenn alle enthalten sein, die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) eines der Verschiebevorgänge verwenden, um von Datensatz zu Datensatz verschoben, werden sollen. Um einen Datensatz in einem Recordset-Diagramm nach der Tabelle zu suchen, rufen Sie die `Seek` Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, die Zeiger für den aktuellen Datensatz unbestimmt ist, ist und `FindNext` gibt 0 (null) zurück. Wenn das Recordset mehrere Datensätze enthält, die die Kriterien erfüllt `FindFirst` sucht das erste Vorkommen `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie mit einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen entspricht nicht dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt, die ungleich NULL ist, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger an einem gültigen Datensatz positionieren.  
  
-   Sie können kein Suchvorgangs mit einem Vorwärtscursor Durchführen eines Bildlaufs-Diagramm nach der Momentaufnahme-Recordset.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann übereinstimmenden Datensätzen nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise feststellen, die Operationen mit langsam ist, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte abrufen indizierte Datensätze.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" DAO-Hilfe.  
  
##  <a name="findprev"></a>CDaoRecordset::FindPrev  
 Rufen Sie diese Memberfunktion zum vorherigen Datensatz zu suchen, der einer angegebenen Bedingung entspricht.  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (z. B. die **, in denen** -Klausel in einer SQL­Anweisung ohne das Wort **, in denen**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindPrev` Memberfunktion beginnt die Suche am aktuellen Datensatz und sucht rückwärts bis zum Anfang des Recordsets.  
  
 Wenn alle enthalten sein, die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) eines der Verschiebevorgänge verwenden, um von Datensatz zu Datensatz verschoben, werden sollen. Um einen Datensatz in einem Recordset-Diagramm nach der Tabelle zu suchen, rufen Sie die `Seek` Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, die Zeiger für den aktuellen Datensatz unbestimmt ist, ist und `FindPrev` gibt 0 (null) zurück. Wenn das Recordset mehrere Datensätze enthält, die die Kriterien erfüllt `FindFirst` sucht das erste Vorkommen `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, werden Sie sicher, dass Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie mit einem anderen Datensatz verschieben, ohne zu aktualisieren, sind Ihre Änderungen verloren gehen, ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen entspricht nicht dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch die ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt, die ungleich NULL ist, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger an einem gültigen Datensatz positionieren.  
  
-   Sie können kein Suchvorgangs mit einem Vorwärtscursor Durchführen eines Bildlaufs-Diagramm nach der Momentaufnahme-Recordset.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann übereinstimmenden Datensätzen nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken und große Dynasets werden Sie möglicherweise feststellen, die Operationen mit langsam ist, insbesondere bei der Arbeit mit großen Recordsets. Sie können die Leistung verbessern, indem Sie mit SQL-Abfragen mit angepasst **ORDERBY** oder **, in denen** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte abrufen indizierte Datensätze.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" DAO-Hilfe.  
  
##  <a name="getabsoluteposition"></a>CDaoRecordset:: GetAbsolutePosition  
 Gibt die Nummer des aktuellen Datensatzes des Recordset-Objekts zurück.  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl von 0 auf die Anzahl der Datensätze im Recordset. Entspricht der Position des aktuellen Datensatzes im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der AbsolutePosition-Eigenschaft für das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz des Recordsets. Sie können die Anzahl der aufgefüllten Datensätze im Recordset bestimmen, durch den Aufruf [GetRecordCount](#getrecordcount). Aufrufen von `GetRecordCount` kann einige Zeit dauern, da alle Datensätze, um zu bestimmen, die Anzahl die zugegriffen werden muss.  
  
 Wenn es liegt kein aktueller Datensatz im Recordset keine Datensätze vorliegen, - 1 zurückgegeben. Wenn der aktuelle Datensatz gelöscht wird, der AbsolutePosition-Eigenschaftswert ist nicht definiert, und löst MFC eine Ausnahme aus, wenn darauf verwiesen wird. Für Recordsets vom Typ Dynaset werden neue Datensätze am Ende der Sequenz hinzugefügt.  
  
> [!NOTE]
>  Diese Eigenschaft dient nicht als Ersatz-Datensatznummer verwendet werden. Lesezeichen sind weiterhin die empfohlene Methode der beibehalten und die Rückgabe an einer angegebenen Position und die einzige Möglichkeit, den aktuellen Datensatz für alle Typen des Recordset-Objekte zu positionieren. Insbesondere ändert die Position eines bestimmten Datensatzes auf, wenn vorhergehenden Datensätze gelöscht werden. Es gibt keine Garantie dafür, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets nicht garantiert ist, es sei denn, sie mit der Verwendung einer SQL-Anweisung erstellt wird auch ein  **ORDERBY** Klausel.  
  
> [!NOTE]
>  Diese Memberfunktion gilt nur für Dynaset und-Diagramm nach der Momentaufnahme Recordsets zur Verfügung.  
  
 Verwandte Informationen finden Sie im Thema "AbsolutePosition-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getbookmark"></a>CDaoRecordset:: GetBookmark  
 Rufen Sie diese Memberfunktion zum Abrufen des lesezeichenwerts in einem bestimmten Datensatz.  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der das Lesezeichen im aktuellen Datensatz darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, sofern diese unterstützt. Rufen Sie `CanBookmark` zu bestimmen, ob ein Recordset Lesezeichen unterstützt.  
  
 Sie können das Lesezeichen für den aktuellen Datensatz durch Zuweisen des Werts des Lesezeichens, das Speichern einer `COleVariant` Objekt. Um schnell an diesen Datensatz zu einem beliebigen Zeitpunkt nach dem Verschieben zu einem anderen Datensatz zurückzugeben, rufen `SetBookmark` mit einem Parameter, die entsprechend dem Wert dieses `COleVariant` Objekt.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Verwandte Informationen finden Sie im Thema "Lesezeicheneigenschaft" DAO-Hilfe.  
  
##  <a name="getcachesize"></a>CDaoRecordset::GetCacheSize  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl der Datensätze, die zwischengespeichert.  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, die Anzahl der Datensätze in einem Typ Dynaset-Recordset, das mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Recordset-Objekte vom Typ Dynaset abruft. Ein Cache ist ein Leerzeichen im lokalen Speicher, der enthält die Daten, die zuletzt vom Server abgerufen werden, dass die Daten erneut angefordert werden, während die Anwendung ausgeführt wird. Wenn Daten angefordert werden, überprüft der Microsoft Jet-Datenbankmodul den Cache für die angeforderten Daten zunächst anstatt abrufen aus dem Server mehr Zeit in Anspruch. Daten, die nicht von einer ODBC-Datenquelle stammt, ist nicht im Cache gespeichert.  
  
 Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle haben einen lokalen Cache.  
  
 Weitere Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getcachestart"></a>CDaoRecordset::GetCacheStart  
 Rufen Sie diese Memberfunktion zum Abrufen des Lesezeichenwert des ersten Datensatzes im Recordset zwischengespeichert werden soll.  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COleVariant` , das Lesezeichen des ersten Datensatzes angibt, in das Recordset zwischengespeichert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Das Microsoft Jet-Datenbankmodul Datensätze innerhalb des Bereichs der Cache aus dem Cache anfordert, und fordert Datensätze außerhalb des Bereichs Cache vom Server.  
  
> [!NOTE]
>  Datensätze, die aus dem Cache abgerufene spiegeln nicht gleichzeitig auf die Quelldaten von anderen Benutzern vorgenommene Änderungen.  
  
 Weitere Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex  
 Rufen Sie diese Memberfunktion, um zu bestimmen, den Index aktuell in Verwendung in einer indizierten Tabellentyp `CDaoRecordset` Objekt.  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` mit dem Namen des Indexes derzeit in Verwendung mit einem Tabellentyp Recordset. Gibt eine leere Zeichenfolge zurück, wenn kein Index festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Index bildet die Grundlage für die Reihenfolge der Datensätze in einem Recordset-Diagramm nach der Tabelle, und wird verwendet, durch die [Seek](#seek) Member-Funktion, um Datensätze zu suchen.  
  
 Ein `CDaoRecordset` Objekt kann mehr als einen Index aufweisen, jedoch können jeweils nur einen Index verwenden (obwohl eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt verfügt möglicherweise über mehrere Indizes definiert ist).  
  
 Weitere Informationen finden Sie im Thema "Indexobjekt" und die Definition "aktuellen Index" DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>CDaoRecordset::GetDateCreated  
 Rufen Sie diese Memberfunktion, um das Datum und die Uhrzeit der Erstellung eine Basistabelle abzurufen.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das Datum und Uhrzeit der Erstellung die Basistabelle enthält.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt wurde.  
  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated  
 Rufen Sie diese Memberfunktion zum Abrufen von Datum und Uhrzeit der letzten Aktualisierung des Schemas.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der letzten die Basistabellenstruktur (Schema Aktualisierung) enthält.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabellenstruktur (Schema) zuletzt aktualisiert wurde.  
  
 Weitere Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName  
 Rufen Sie diese Memberfunktion auf den Namen der Datenbank für Recordsets ermitteln.  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , enthält der Pfad und Name der Datenbank, von dem dieses Recordset abgeleitet ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Recordset erstellt wird, ohne einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), wird dieser Pfad vom Recordset verwendet wird, um die Standarddatenbank zu öffnen. Diese Funktion wird standardmäßig eine leere Zeichenfolge zurückgegeben. Wenn ClassWizard leitet ein neues Recordset aus `CDaoRecordset`, diese Funktion wird für Sie erstellt.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines umgekehrten Schrägstriche (\\\\) in der Zeichenfolge ist erforderlich, damit die Zeichenfolge ordnungsgemäß interpretiert werden soll.  
  
 [!code-cpp[NVC_MFCDatabase#4](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL  
 Das Framework ruft diese Memberfunktion, um die Standard-SQL-Anweisung zu erhalten, auf der sich die Datensatzgruppe basiert.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , die die Standard-SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist möglicherweise ein Tabellenname oder ein SQL **wählen** Anweisung.  
  
 Sie definieren die Standard-SQL-Anweisung indirekt durch Deklarieren des Recordset-Klasse mit ClassWizard und ClassWizard diese Aufgabe für Sie ausführt.  
  
 Wenn Sie eine null-SQL-Zeichenfolge zu übergeben [öffnen](#open), und klicken Sie dann diese Funktion aufgerufen wird, um zu bestimmen, den Tabellennamen oder SQL für das Recordset.  
  
##  <a name="geteditmode"></a>CDaoRecordset::GetEditMode  
 Rufen Sie diese Memberfunktion zum Bestimmen des Status der Bearbeitung, dies ist eine der folgenden Werte:  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der den Status des bearbeiten für den aktuellen Datensatz angibt.  
  
### <a name="remarks"></a>Hinweise  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**dbEditNone**|Kein bearbeiten-Vorgang wird ausgeführt.|  
|**dbEditInProgress**|**Bearbeiten Sie** aufgerufen wurde.|  
|**dbEditAdd**|`AddNew`wurde aufgerufen.|  
  
 Verwandte Informationen finden Sie im Thema "EditMode-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getfieldcount"></a>CDaoRecordset::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Feldern (Spalten), die im Recordset definiert.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getfieldinfo"></a>CDaoRecordset::GetFieldInfo  
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
 `nIndex`  
 Der nullbasierte Index des Felds vordefinierte in das Recordset Fields-Auflistung, für die Suche nach Index.  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen. Rufen Sie für optimale Leistung nur die Ebene der von Ihnen benötigten Informationen ein:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ, Größe, Attribute  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Ordnungszahl Position ist erforderlich, können 0 (null) Länge Reihenfolge sortieren ausländischen Name, Quellfeld Quelltabelle  
  
- `AFX_DAO_ALL_INFO`Informationen zu primären und sekundären plus: Default Value Validierungsregel, Validierung Text  
  
 `lpszName`  
 Der Name des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getfieldvalue"></a>CDaoRecordset:: GetFieldValue  
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
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die den Namen eines Felds enthält.  
  
 `varValue`  
 Ein Verweis auf eine `COleVariant` -Objekt, das den Wert eines Felds gespeichert werden.  
  
 `nIndex`  
 Ein nullbasierter Index des Felds in das Recordset Fields-Auflistung, für die Suche nach Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Die beiden Versionen des `GetFieldValue` , die einen Wert zurückgeben Zurückgeben einer [COleVariant](../../mfc/reference/colevariant-class.md) -Objekt, das den Wert eines Felds enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Feld nach Name oder Ordnungsposition nachschlagen.  
  
> [!NOTE]
>  Es ist effizienter, rufen eine der Versionen von dieser Memberfunktion, ein `COleVariant` -Objektverweis als einen Parameter, anstatt eine Version, die zurückgegeben ein `COleVariant` Objekt. Die letzten Versionen dieser Funktion werden für die Abwärtskompatibilität beibehalten.  
  
 Verwendung `GetFieldValue` und [SetFieldValue](#setfieldvalue) Felder dynamisch zur Laufzeit statt statisch Binden von Spalten mit Binden der [DoFieldExchange](#dofieldexchange) Mechanismus.  
  
 `GetFieldValue`und die `DoFieldExchange` Mechanismus kann kombiniert werden, um die Leistung zu verbessern. Verwenden Sie z. B. `GetFieldValue` zum Abrufen eines Werts, die nur bei Bedarf werden müssen, und weisen diesen Aufruf mit einer Schaltfläche "Weitere Informationen" in der Schnittstelle.  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getindexcount"></a>CDaoRecordset::GetIndexCount  
 Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl der Indizes, die auf den Tabellentyp Recordset verfügbar.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Indizes in das Recordset-Diagramm nach der Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 `GetIndexCount`eignet sich für das Durchlaufen aller Indizes in das Recordset. Verwenden Sie zu diesem Zweck `GetIndexCount` in Verbindung mit [GetIndexInfo](#getindexinfo). Wenn Sie diese Memberfunktion auf Dynaset oder Snapshot-Typ aufrufen, löst MFC eine Ausnahme aus.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo  
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
 `nIndex`  
 Der nullbasierte Index in die Tabelle Indizes Auflistung für die Suche nach numerischen Position.  
  
 `indexinfo`  
 Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über den Index abgerufen. Die verfügbaren Optionen sind hier aufgeführt, zusammen mit der sie die Funktion zurückgibt verursachen. Rufen Sie für optimale Leistung nur die Ebene der von Ihnen benötigten Informationen ein:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Feldinformationen, Felder  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: primären, eindeutiger, gruppierter, IgnoreNulls, erforderlich, Fremdschlüssel  
  
- `AFX_DAO_ALL_INFO`Informationen zu primären und sekundären plus: Distinct Count  
  
 `lpszName`  
 Ein Zeiger auf den Namen des Index-Objekts, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie einen Index anhand seiner Position in der Auflistung gesucht. Die andere Version können Sie einen Index nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur enthält Member, die die Elemente in der Beschreibung der oben aufgeführten Informationen entsprechen `dwInfoOptions`. Wenn Sie die Informationen auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie an.  
  
 Verwandte Informationen finden Sie im Thema "Attribute Property" in der DAO-Hilfe.  
  
##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark  
 Rufen Sie diese Memberfunktion zum Abrufen des Lesezeichens für die meisten kürzlich hinzugefügte oder aktualisierte Datensatz an.  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COleVariant` hinzugefügten oder geänderten Datensatz mit einem Lesezeichen, das die zuletzt angibt.  
  
### <a name="remarks"></a>Hinweise  
 Bei einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, sofern diese unterstützt. Rufen Sie [GetBookmark](#getbookmark) zu bestimmen, ob das Recordset Lesezeichen unterstützt. Wenn das Recordset keine Lesezeichen unterstützt eine `CDaoException` ausgelöst wird.  
  
 Wenn Sie einen Datensatz hinzufügen, wird am Ende des Recordsets angezeigt und ist nicht der aktuelle Datensatz. Um den neuen Datensatz aktualisieren, rufen `GetLastModifiedBookmark` und rufen dann `SetBookmark` auf den neu hinzugefügten Datensatz zurückgegeben.  
  
 Verwandte Informationen finden Sie im Thema "LastModified-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getlockingmode"></a>CDaoRecordset::GetLockingMode  
 Rufen Sie diese Memberfunktion um den Typ der für das Recordset faktisch Sperren zu bestimmen.  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn der Typ der Sperre eingeschränkte, andernfalls 0 zum Sperren der vollständige Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Pessimistische Sperren beim aktiviert ist, wird der Datenseite mit dem Datensatz, der von Ihnen bearbeiteten ist gesperrt, sobald Sie rufen die [bearbeiten](#edit) Memberfunktion. Die Seite ist nicht gesperrt, beim Aufrufen der [Update](#update) oder [schließen](#close) Memberfunktion oder die Vorgänge zum Verschieben oder suchen.  
  
 Wenn optimistischen Sperrung wirksam ist, wird die Datenseite, enthält des Datensatzes gesperrt, nur, wenn der Eintrag aktualisiert wird, mit der **Update** Memberfunktion.  
  
 Bei der Arbeit mit ODBC-Datenquellen wird das Sperrverhalten immer optimistic.  
  
 Weitere Informationen finden Sie unter den Themen "Sperren-Eigenschaft" und "Sperren Verhalten in Multiuser Applications" in der DAO-Hilfe.  
  
##  <a name="getname"></a>CDaoRecordset::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Recordsets.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` mit dem Namen des Recordsets.  
  
### <a name="remarks"></a>Hinweise  
 Der Name des Recordset-Objekts muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Er kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getparamvalue"></a>CDaoRecordset::GetParamValue  
 Rufen Sie diese Memberfunktion zum Abrufen des aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter Objekt gespeichert.  
  
```  
virtual COleVariant GetParamValue(int nIndex);  
virtual COleVariant GetParamValue(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Die numerische Position des Parameters in der zugrunde liegenden DAOParameter-Objekt.  
  
 `lpszName`  
 Der Name des Parameters, dessen Wert.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Objekt der Klasse [COleVariant](../../mfc/reference/colevariant-class.md) , die den Wert des Parameters enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Parameter nach Namen oder die numerische Position in der Auflistung zugreifen.  
  
 Verwandte Informationen finden Sie im Thema "Parameterobjekt" DAO-Hilfe.  
  
##  <a name="getpercentposition"></a>CDaoRecordset:: GetPercentPosition  
 Beim Arbeiten mit einem Dynaset oder Snapshot-Type-Recordset, beim Aufrufen `GetPercentPosition` vor der vollständigen Auffüllung das Recordset, wird der Betrag der Verschiebung relativ zur Anzahl der Datensätze zugegriffen wird, wie durch den Aufruf angegeben [GetRecordCount](#getrecordcount).  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zahl zwischen 0 und 100, die die ungefähre Position des aktuellen Datensatzes in das Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset angibt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können wechselt zur letzten Datensatz durch den Aufruf [MoveLast](#movelast) auf vollständige des Auffüllens eines Recordsets, doch dadurch möglicherweise sehr lange dauern, Zeit.  
  
 Sie können Aufrufen `GetPercentPosition` auf alle drei Typen von Recordset-Objekte, einschließlich Tabellen ohne Indizes. Allerdings können Sie nicht aufrufen `GetPercentPosition` Vorwärtscursor Durchführen eines Bildlaufs Momentaufnahmen oder auf einem Recordset aus einer Pass-Through-Abfrage einer externen Datenbank geöffnet. Wenn es kein aktueller Datensatz ist oder He aktuellen Datensatz gelöscht wurde, eine `CDaoException` ausgelöst wird.  
  
 Verwandte Informationen finden Sie im Thema "PercentPosition-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getrecordcount"></a>CDaoRecordset::GetRecordCount  
 Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze im Recordset zugegriffen wurde.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Datensätze in einem Recordset-Objekt zugegriffen.  
  
### <a name="remarks"></a>Hinweise  
 `GetRecordCount`Gibt nicht an wie viele Datensätze in einem Dynaset oder Snapshot-Type-Recordset enthalten sind, bis alle Datensätze zugegriffen wurde. Dieser memberfunktionsaufruf dauert sehr viel Zeit in Anspruch.  
  
 Nachdem der letzte Datensatz zugegriffen wurde, gibt der zurückgegebene Wert die Gesamtzahl der nicht gelöschten Datensätze im Recordset an. Rufen Sie zum Erzwingen des letzten Datensatzes auf der `MoveLast` oder `FindLast` -Memberfunktion des Recordsets. Eine SQL-Count können auch um die ungefähre Anzahl der Datensätze zu ermitteln, die die Abfrage zurückgibt.  
  
 Wie Ihre Anwendung Datensätze in einem Recordset Dynaset-Typ, der Rückgabewert der löscht `GetRecordCount` verringert. Von anderen Benutzern gelöschten Datensätze werden jedoch nicht wiedergegeben, indem `GetRecordCount` bis zum aktuelle Datensatz auf einen gelöschten Datensatz positioniert ist. Wenn Sie eine Transaktion, die die Anzahl der Datensätze wirkt sich auf Ausführen, und anschließend ein der Transaktion Rollback `GetRecordCount` der tatsächlichen Anzahl verbleibender Datensätze nicht widerspiegelt.  
  
 Der Wert des `GetRecordCount` aus einem Recordset-Diagramm nach der Momentaufnahme wird durch Änderungen an den zugrunde liegenden Tabellen nicht beeinflusst.  
  
 Der Wert des `GetRecordCount` aus einen Tabellentyp Recordset gibt die ungefähre Anzahl von Datensätzen in der Tabelle wieder und ist direkt betroffen, wenn Datensätze hinzugefügt oder gelöscht werden.  
  
 Ein Recordset mit keine Einträge gibt einen Wert von 0 zurück. Beim Arbeiten mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` immer - 1 zurückgegeben. Aufrufen der **Requery** Member-Funktion auf einem Recordset setzt den Wert der `GetRecordCount` als ob die Abfrage erneut ausgeführt wurden.  
  
 Verwandte Informationen finden Sie im Thema "RecordCount-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getsql"></a>CDaoRecordset::GetSQL  
 Rufen Sie diese Memberfunktion, um die SQL-Anweisung zu erhalten, die verwendet wurde, zum Auswählen von Datensätzen für das Recordset, wenn es geöffnet wurde.  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , die die SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist im Allgemeinen wird eine SQL **wählen** Anweisung.  
  
 Die zurückgegebene Zeichenfolge `GetSQL` unterscheidet sich in der Regel eine beliebige Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die `lpszSQL` Parameter an die [öffnen](#open) Memberfunktion. Dies ist, da das Recordset eine vollständige SQL­Anweisung anhand der erstellt an übergebene **öffnen**, was mit ClassWizard angegebenen und was Sie angegeben haben möglicherweise die [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) Datenmember.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf **öffnen**.  
  
 Verwandte Informationen finden Sie im Thema "SQL-Eigenschaft" DAO-Hilfe.  
  
##  <a name="gettype"></a>CDaoRecordset::GetType  
 Rufen Sie diese Memberfunktion auf, nach dem Öffnen des Recordsets, um den Typ des Recordset-Objekts zu bestimmen.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte, die den Typ eines Recordsets angibt:  
  
- **Übergeben** Tabellentyp Recordset  
  
- **DbOpenDynaset** Typ Dynaset  
  
- **DbOpenSnapshot** -Diagramm nach der Momentaufnahme-Recordset  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
##  <a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule  
 Rufen Sie diese Memberfunktion zum Bestimmen der Regel verwendet, um Daten zu überprüfen.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt, das einen Wert, der die Daten in einem Datensatz überprüft werden, da sie einer Tabelle hinzugefügt, geändert oder enthält.  
  
### <a name="remarks"></a>Hinweise  
 Diese Regel wird der textbasierte und angewendet wird jedes Mal, wenn die zugrunde liegende Tabelle geändert wird. Wenn die Daten nicht zulässig ist, löst MFC eine Ausnahme aus. Die zurückgegebene Fehlermeldung lautet der Text der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt, wenn angegeben, oder der Text des Ausdrucks durch die ValidationRule-Eigenschaft des zugrunde liegenden Field-Objekt. Sie können Aufrufen [GetValidationText](#getvalidationtext) zum Abrufen des Texts der Fehlermeldung.  
  
 Z. B. ein Feld in einem Datensatz, der den Tag des Monats erfordert möglicherweise eine Validierungsregel wie z. B. "Tag zwischen 1 und 31."  
  
 Verwandte Informationen finden Sie im Thema "ValidationRule-Eigenschaft" DAO-Hilfe.  
  
##  <a name="getvalidationtext"></a>CDaoRecordset::GetValidationText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt mit dem Text der Nachricht, die angezeigt wird, wenn der Wert eines Felds Überprüfungsregel für den zugrunde liegenden Field-Objekt nicht erfüllt.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" DAO-Hilfe.  
  
##  <a name="isbof"></a>CDaoRecordset::IsBOF  
 Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf aus Datensatz zu Datensatz zur Feststellung, ob Sie vor dem ersten Datensatz des Recordsets überschritten haben.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält oder wenn Sie kein Bildlauf rückwärts vor dem ersten Datensatz durchgeführt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können auch aufrufen `IsBOF` zusammen mit `IsEOF` zu bestimmen, ob das Recordset alle Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf **öffnen**, wenn das Recordset keine Datensätze enthält `IsBOF` ungleich NULL zurückgegeben. Wenn Sie ein Recordset, die über mindestens ein Datensatz öffnen, der erste Datensatz zum aktuellen Datensatz ist und `IsBOF` gibt 0 zurück.  
  
 Wenn der erste Datensatz zum aktuellen Datensatz und Sie rufen `MovePrev`, `IsBOF` anschließend ungleich NULL zurück. Wenn `IsBOF` zurück, die ungleich NULL ist und Sie rufen `MovePrev`, wird eine Ausnahme ausgelöst. Wenn `IsBOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert eine Ausnahme ausgelöst wird.  
  
 Auswirkungen der spezifischen Methoden auf `IsBOF` und `IsEOF` Einstellungen:  
  
-   Aufrufen von **öffnen** intern wird der erste Datensatz im Recordset den aktuellen Datensatz durch den Aufruf **MoveFirst**. Aus diesem Grund Aufrufen **öffnen** auf eine leere Menge von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe die folgende Tabelle für das Verhalten eines Fehlers bei **MoveFirst** oder `MoveLast` aufrufen.)  
  
-   Alle Verschiebevorgänge, die einen Datensatz wurde erfolgreich ermittelt dazu führen, dass beide `IsBOF` und `IsEOF` auf "0" zurückgeben.  
  
-   Ein `AddNew` Aufruf, gefolgt von einer **Update** Aufruf, die erfolgreich einen neuen Datensatz einfügt bewirkt `IsBOF` zurückzugebenden 0, jedoch nur, wenn `IsEOF` bereits ungleich NULL ist. Der Status der `IsEOF` immer bleibt unverändert. Gemäß der Microsoft Jet-Datenbankmodul ist Zeiger des aktuellen Datensatzes auf ein leeres Recordset am Ende einer Datei, damit nach der der aktuelle Datensatz ein neuer Datensatz eingefügt wird.  
  
-   Alle **löschen** Aufruf, auch wenn den letzte Datensatz aus einem Recordset entfernt ändert sich nicht den Wert der `IsBOF` oder `IsEOF`.  
  
 Diese Tabelle zeigt, welche Verschiebevorgänge zulässig sind, mit verschiedenen Kombinationen von `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> < 0 verschieben|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie die > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= ungleich NULL,<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|  
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|  
|Beide 0|Allowed|Allowed|Allowed|Allowed|  
  
 Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang einen Datensatz wurde erfolgreich ermittelt werden. Er gibt lediglich an, dass ein Versuch, den angegebenen Vorgang durchzuführen, zulässig ist, und keine Ausnahme generiert. Der Wert, der die `IsBOF` und `IsEOF` Memberfunktionen möglicherweise ändern, durch das verschieben.  
  
 Die Auswirkung der Verschiebevorgänge, die keinen Datensatz für den Wert der finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle gezeigt wird.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ungleich|Ungleich|  
|**Verschieben Sie** 0|Keine Änderung|Keine Änderung|  
|`MovePrev`, **Verschieben** < 0|Ungleich|Keine Änderung|  
|`MoveNext`, **Verschieben** > 0|Keine Änderung|Ungleich|  
  
 Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="isdeleted"></a>CDaoRecordset::IsDeleted  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz gelöscht wurde.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset, auf einen gelöschten Datensatz positioniert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen zu einem Datensatz Bildlauf und `IsDeleted` gibt **"true"** (ungleich null), klicken Sie dann Sie müssen einen Bildlauf zu einem anderen Datensatz, bevor Sie andere Recordset-Vorgänge ausführen können.  
  
> [!NOTE]
>  Sie müssen nicht den Status "gelöscht" für Datensätze in einem Recordset Snapshot- oder-Diagramm nach der Tabelle überprüfen. Da die Datensätze aus einer Momentaufnahme gelöscht werden können, besteht keine Notwendigkeit zum Aufrufen `IsDeleted`. Für Recordsets-Diagramm nach der Tabelle werden gelöschte Datensätze tatsächlich aus dem Recordset entfernt. Sobald ein Datensatz, indem Sie einen anderen Benutzer oder in einem anderen Recordset gelöscht wurde können nicht Sie wieder an diesen Datensatz einen Bildlauf durchführen. Daher besteht keine Notwendigkeit zum Aufrufen `IsDeleted`.  
  
 Wenn Sie einen Datensatz aus einem Dynaset löschen, wird vom Recordset entfernt, und Sie können nicht wieder an diesen Datensatz einen Bildlauf ausführen. Wenn ein Datensatz in einem Dynaset wird jedoch gelöscht, von einem anderen Benutzer oder in einem anderen Recordset basierend auf der gleichen Tabelle `IsDeleted` zurück **"true"** Wenn Sie später einen Bildlauf nach diesen Datensatz.  
  
 Weitere Informationen finden Sie unter den Themen "Method löschen", "LastModified-Eigenschaft" und "EditMode-Eigenschaft" DAO-Hilfe.  
  
##  <a name="iseof"></a>CDaoRecordset::IsEOF  
 Rufen Sie diese Memberfunktion auf, wie Sie einen Bildlauf aus Datensatz zu Datensatz zur Feststellung, ob Sie den letzten Datensatz des Recordsets überschritten haben.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält oder wenn Sie hinter dem letzten Datensatz gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können auch aufrufen `IsEOF` zu bestimmen, ob das Recordset alle Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf **öffnen**, wenn das Recordset keine Datensätze enthält `IsEOF` ungleich NULL zurückgegeben. Wenn Sie ein Recordset, die über mindestens ein Datensatz öffnen, der erste Datensatz zum aktuellen Datensatz ist und `IsEOF` gibt 0 zurück.  
  
 Wenn der letzte Datensatz zum aktuellen Datensatz beim Aufrufen ist `MoveNext`, `IsEOF` anschließend ungleich NULL zurück. Wenn `IsEOF` zurück, die ungleich NULL ist und Sie rufen `MoveNext`, wird eine Ausnahme ausgelöst. Wenn `IsEOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert eine Ausnahme ausgelöst wird.  
  
 Auswirkungen der spezifischen Methoden auf `IsBOF` und `IsEOF` Einstellungen:  
  
-   Aufrufen von **öffnen** intern wird der erste Datensatz im Recordset den aktuellen Datensatz durch den Aufruf **MoveFirst**. Aus diesem Grund Aufrufen **öffnen** auf eine leere Menge von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe die folgende Tabelle für das Verhalten eines Fehlers bei **MoveFirst** aufrufen.)  
  
-   Alle Verschiebevorgänge, die einen Datensatz wurde erfolgreich ermittelt dazu führen, dass beide `IsBOF` und `IsEOF` auf "0" zurückgeben.  
  
-   Ein `AddNew` Aufruf, gefolgt von einer **Update** Aufruf, die erfolgreich einen neuen Datensatz einfügt bewirkt `IsBOF` zurückzugebenden 0, jedoch nur, wenn `IsEOF` bereits ungleich NULL ist. Der Status der `IsEOF` immer bleibt unverändert. Gemäß der Microsoft Jet-Datenbankmodul ist Zeiger des aktuellen Datensatzes auf ein leeres Recordset am Ende einer Datei, damit nach der der aktuelle Datensatz ein neuer Datensatz eingefügt wird.  
  
-   Alle **löschen** Aufruf, auch wenn den letzte Datensatz aus einem Recordset entfernt ändert sich nicht den Wert der `IsBOF` oder `IsEOF`.  
  
 Diese Tabelle zeigt, welche Verschiebevorgänge zulässig sind, mit verschiedenen Kombinationen von `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> < 0 verschieben|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie die > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`= ungleich NULL,<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|  
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|  
|Beide 0|Allowed|Allowed|Allowed|Allowed|  
  
 Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang einen Datensatz wurde erfolgreich ermittelt werden. Er gibt lediglich an, dass ein Versuch, den angegebenen Vorgang durchzuführen, zulässig ist, und keine Ausnahme generiert. Der Wert, der die `IsBOF` und `IsEOF` Memberfunktionen möglicherweise ändern, durch das verschieben.  
  
 Die Auswirkung der Verschiebevorgänge, die keinen Datensatz für den Wert der finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle gezeigt wird.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ungleich|Ungleich|  
|**Verschieben Sie** 0|Keine Änderung|Keine Änderung|  
|`MovePrev`, **Verschieben** < 0|Ungleich|Keine Änderung|  
|`MoveNext`, **Verschieben** > 0|Keine Änderung|Ungleich|  
  
 Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Feld Daten Mitglied ein Dynaset als "fehlerhaft" markiert wurde (geändert).  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene felddatenelement als sauber markiert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten in alle Felddatenmember übertragen werden sollen den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der **Update** Memberfunktion von `CDaoRecordset` (nach einem Aufruf **Bearbeiten**oder `AddNew`). Mit diesem Wissen Sie können Schritte weiter, z. B. Aufheben der Kennzeichnung der Felddatenmember auf die Spalte zu kennzeichnen, sodass sie nicht an die Datenquelle geschrieben wird.  
  
 `IsFieldDirty`wird durch implementiert `DoFieldExchange`.  
  
##  <a name="isfieldnull"></a>CDaoRecordset::IsFieldNull  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Felddatenmember eines Recordsets als Null gekennzeichnet wurde.  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene felddatenelement als Null gekennzeichnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 (In der datenbankterminologie von-Null bedeutet "kein Wert having" und entspricht nicht dem als **NULL** in C++.) Wenn ein Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte des aktuellen Datensatzes interpretiert kein Wert vorhanden ist.  
  
> [!NOTE]
>  In bestimmten Situationen mit `IsFieldNull` kann ineffizient sein, wie im folgenden Codebeispiel wird veranschaulicht:  
  
 [!code-cpp[NVC_MFCDatabase#5](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  Wenn Sie dynamische Bindung aufzuzeichnen, ohne eine Ableitung von verwenden `CDaoRecordset`, achten Sie darauf, dass Sie verwenden **VT_NULL** wie im Beispiel gezeigt.  
  
##  <a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Feld-Datenelement "NULL-Werte zulassen" ist (können auf einen Null-Wert festgelegt werden C++ **NULL** entspricht nicht dem als Null, was die in der Terminologie von Datenbanken bedeutet "kein Wert having").  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene felddatenelement Null festgelegt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, diese ein Feld auf Null beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und **aktualisieren** wird eine Ausnahme ausgelöst. Die Ausnahme tritt auf, wenn Sie aufrufen **Update**, nicht beim Aufrufen von `SetFieldNull`.  
  
##  <a name="isopen"></a>CDaoRecordset::IsOpen  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich Null des Recordset-Objekts **öffnen** oder **Requery** Memberfunktion zuvor aufgerufen wurde und das Recordset nicht geschlossen wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: M_bcheckcachefordirtyfields  
 Enthält ein Flag, das angibt, ob zwischengespeicherte Felder automatisch markiert werden als modifizierte Seiten (geändert) und Null.  
  
### <a name="remarks"></a>Hinweise  
 Das Flag wird standardmäßig auf **"true"**. Die Einstellung in dieses Datenelement steuert den gesamten Doppelpufferung-Mechanismus. Wenn Sie das Flag auf **"true"**, Sie können das Zwischenspeichern auf Grundlage Feld-nach-Feld mit dem Mechanismus DFX deaktivieren. Wenn Sie das Flag auf **"false"**, rufen Sie `SetFieldDirty` und `SetFieldNull` selbst.  
  
 Legen Sie dieses Datenelement vor dem Aufruf **öffnen**. Dieser Mechanismus wird in erster Linie für einfach zu verwendende. Leistung ist möglicherweise langsamer aufgrund der Doppelpufferung Felder Änderungen vorgenommen werden.  
  
##  <a name="m_nfields"></a>CDaoRecordset::m_nFields  
 Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor für das Recordset-Klasse muss initialisiert werden `m_nFields` mit die richtige Anzahl von statisch gebundenen Felder. ClassWizard schreibt diese Initialisierung für Sie aus, wenn Sie es verwenden, um die Recordset-Klasse deklarieren. Sie können Sie auch manuell erstellen.  
  
 Das Framework verwendet diese Zahl zum Verwalten der Interaktion zwischen den Felddatenmembern und den entsprechenden Spalten des aktuellen Datensatzes für die Datenquelle an.  
  
> [!NOTE]
>  Diese Zahl muss entspricht der Anzahl von Ausgabespalten in registriert `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter **CDaoFieldExchange::outputColumn**.  
  
 Sie können Spalten dynamisch mithilfe von binden `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue`. Wenn Sie dies tun, müssen Sie nicht erhöhen der Anzahl die in der `m_nFields` entsprechend der Anzahl der DFX-Funktion aufruft, Ihrem `DoFieldExchange` Memberfunktion.  
  
##  <a name="m_nparams"></a>CDaoRecordset::m_nParams  
 Enthält die Anzahl der Parameterdatenmember in der Recordsetklasse – die Anzahl von Parametern übergeben, mit die Abfrage des Recordsets.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Recordset-Klasse Parameterdatenmember verfügt, muss der Konstruktor für die Klasse initialisieren `m_nParams` mit der korrekten Anzahl. Der Wert des `m_nParams` hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen – die Sie ausführen müssen, manuell – Sie müssen auch manuell eine Initialisierung im Klassenkonstruktor entsprechend die Anzahl von Parametern hinzufügen (die muss mindestens so groß wie die Anzahl der "Platzhalter in Ihre **M_strFilter**  oder `m_strSort` Zeichenfolge).  
  
 Das Framework verwendet diese Zahl an, wenn sie das Recordset-Abfrage parametrisiert.  
  
> [!NOTE]
>  Diese Zahl muss entsprechen, die Anzahl der "Params" im registriert `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter **CFieldExchange::param**.  
  
 Verwandte Informationen finden Sie im Thema "Parameterobjekt" DAO-Hilfe.  
  
##  <a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Recordset-Objekt zugrunde liegenden der `CDaoRecordset` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie this-Zeiger, wenn Sie die DAO-Schnittstelle direkt zugreifen müssen.  
  
 Verwandte Informationen finden Sie im Thema "Recordset-Objekt" DAO-Hilfe.  
  
##  <a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase  
 Enthält einen Zeiger auf die `CDaoDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable wird auf zwei Arten festgelegt. In der Regel, übergeben Sie einen Zeiger auf ein bereits geöffnetes `CDaoDatabase` Objekt, wenn Sie das Recordset-Objekt erstellen. Wenn Sie übergeben **NULL** stattdessen **CDaoRecordset** erstellt eine `CDaoDatabase` Objekt für Sie und öffnet sie. In beiden Fällen `CDaoRecordset` den Zeiger in dieser Variable gespeichert.  
  
 Normalerweise Sie nicht direkt benötigen, verwenden Sie den Zeiger in gespeicherten **M_pDatabase**. Wenn Sie eine eigene Erweiterungen geschrieben werden sollen `CDaoRecordset`, allerdings müssen Sie den Zeiger zu verwenden. Beispielsweise benötigen Sie möglicherweise den Zeiger Wenn Sie lösen eigene `CDaoException`(s).  
  
 Verwandte Informationen finden Sie im Thema "Datenbankobjekt" DAO-Hilfe.  
  
##  <a name="m_strfilter"></a>CDaoRecordset::m_strFilter  
 Enthält eine Zeichenfolge, mit dem Erstellen, der **, in dem** -Klausel einer SQL­Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Es umfasst nicht das reservierte Wort **, in denen** das Recordset filtern. Die Verwendung dieses Datenelements ist nicht anwendbar zu Recordsets-Diagramm nach der Tabelle. Die Verwendung von **M_strFilter** wirkt sich nicht beim Öffnen einer Datensatzgruppe mit einem `CDaoQueryDef` Zeiger.  
  
 Verwenden Sie das US-Datumsformat (Monat-Tag-Jahr) beim Filtern von Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls können die Daten nicht gefiltert werden, wie erwartet.  
  
 Verwandte Informationen finden Sie im Thema "Filtereigenschaft" DAO-Hilfe.  
  
##  <a name="m_strsort"></a>CDaoRecordset::m_strSort  
 Enthält eine Zeichenfolge mit der **ORDERBY** -Klausel einer SQL­Anweisung ohne den reservierten Wörtern **ORDERBY**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können die Sortierung nach Typ Dynaset und Snapshot Recordset-Objekte.  
  
 Tabellentyp Recordset-Objekte können nicht sortiert werden. Um die Sortierreihenfolge eines Recordsets-Diagramm nach der Tabelle zu ermitteln, rufen [SetCurrentIndex](#setcurrentindex).  
  
 Die Verwendung von `m_strSort` wirkt sich nicht beim Öffnen einer Datensatzgruppe mit einem `CDaoQueryDef` Zeiger.  
  
 Verwandte Informationen finden Sie im Thema "Sortiereigenschaft" DAO-Hilfe.  
  
##  <a name="move"></a>CDaoRecordset::Move  
 Rufen Sie diese Memberfunktion zum Positionieren Sie des Recordsets `lRows` Datensätze aus dem aktuellen Datensatz.  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>Parameter  
 `lRows`  
 Die Anzahl der Datensätze um vorwärts oder rückwärts bewegen. Positive Werte vorwärts, am Ende des Recordsets. Negative Werte rückwärts, an den Anfang.  
  
### <a name="remarks"></a>Hinweise  
 Sie können vorwärts oder rückwärts bewegen. `Move( 1 )`entspricht dem `MoveNext`, und `Move( -1 )` entspricht `MovePrev`.  
  
> [!CAUTION]
>  Aufrufen einer der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie im Allgemeinen sowohl `IsBOF` und `IsEOF` vor Verschiebevorgangs bestimmen, ob das Recordset alle Datensätze verfügt. Nach dem Aufruf **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie hinter dem Anfang oder Ende des Recordsets gescrollt haben ( `IsBOF` oder `IsEOF` ungleich NULL zurückgibt), einen Aufruf von **verschieben** löst eine `CDaoException`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der **verschieben** Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Beim Aufruf **verschieben** auf einem Vorwärtscursor Durchführen eines Bildlaufs Snapshot der `lRows` -Parameter muss eine positive ganze Zahl sein und Lesezeichen sind nicht zulässig, sodass Sie nur vorwärts bewegen können.  
  
 Um den ersten, letzten zu machen, nächsten oder vorherigen Zeichnen in einem Recordset den aktuellen Datensatz, Aufruf der **MoveFirst**, `MoveLast`, `MoveNext`, oder `MovePrev` Memberfunktion.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious Methoden" DAO-Hilfe.  
  
##  <a name="movefirst"></a>CDaoRecordset::MoveFirst  
 Rufen Sie diese Memberfunktion zum Freigeben des ersten Datensatzes in das Recordset (sofern vorhanden) den aktuellen Datensatz.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen keine Aufrufen **MoveFirst** sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt wird der erste Datensatz (sofern vorhanden) automatisch zum aktuellen Datensatz.  
  
> [!CAUTION]
>  Aufrufen einer der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie im Allgemeinen sowohl `IsBOF` und `IsEOF` vor Verschiebevorgangs bestimmen, ob das Recordset alle Datensätze verfügt. Nach dem Aufruf **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der **verschieben** Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben, ohne eine Bedingung anwenden. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder-Diagramm nach der Momentaufnahme Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.  
  
 Wenn das Recordset zu einem Recordset-Diagramm nach der Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Beim Aufrufen `MoveLast` auf einem Recordset-Objekt, das basierend auf einer SQL-Abfrage oder DAO Querydef, die Abfrage bis zum Abschluss erzwungen wird und das Recordset-Objekt ist vollständig aufgefüllt.  
  
 Sie können nicht aufgerufen werden der **MoveFirst** oder `MovePrev` Memberfunktion mit einem Vorwärtscursor Durchführen eines Bildlaufs Snapshot.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt einen bestimmten Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious Methoden" DAO-Hilfe.  
  
##  <a name="movelast"></a>CDaoRecordset::MoveLast  
 Rufen Sie diese Memberfunktion um den letzten Datensatz (sofern vorhanden) stellen im Recordset der aktuelle Datensatz ein.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Aufrufen einer der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie im Allgemeinen sowohl `IsBOF` und `IsEOF` vor Verschiebevorgangs bestimmen, ob das Recordset alle Datensätze verfügt. Nach dem Aufruf **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der **verschieben** Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben, ohne eine Bedingung anwenden. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder-Diagramm nach der Momentaufnahme Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.  
  
 Wenn das Recordset zu einem Recordset-Diagramm nach der Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Beim Aufrufen `MoveLast` auf einem Recordset-Objekt, das basierend auf einer SQL-Abfrage oder DAO Querydef, die Abfrage bis zum Abschluss erzwungen wird und das Recordset-Objekt ist vollständig aufgefüllt.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt einen bestimmten Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious Methoden" DAO-Hilfe.  
  
##  <a name="movenext"></a>CDaoRecordset::MoveNext  
 Rufen Sie diese Memberfunktion um den nächsten Datensatz in das Recordset zum aktuellen Datensatz zu machen.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, Sie rufen `IsBOF` , bevor Sie versuchen, auf den vorherigen Datensatz zu verschieben. Ein Aufruf von `MovePrev` löst eine `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.  
  
> [!CAUTION]
>  Aufrufen einer der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie im Allgemeinen sowohl `IsBOF` und `IsEOF` vor Verschiebevorgangs bestimmen, ob das Recordset alle Datensätze verfügt. Nach dem Aufruf **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der **verschieben** Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben, ohne eine Bedingung anwenden. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder-Diagramm nach der Momentaufnahme Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.  
  
 Wenn das Recordset zu einem Recordset-Diagramm nach der Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt einen bestimmten Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious Methoden" DAO-Hilfe.  
  
##  <a name="moveprev"></a>CDaoRecordset::MovePrev  
 Rufen Sie diese Memberfunktion um den vorherigen Datensatz im Recordset der aktuelle Datensatz zu machen.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, Sie rufen `IsBOF` , bevor Sie versuchen, auf den vorherigen Datensatz zu verschieben. Ein Aufruf von `MovePrev` löst eine `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.  
  
> [!CAUTION]
>  Aufrufen einer der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Rufen Sie im Allgemeinen sowohl `IsBOF` und `IsEOF` vor Verschiebevorgangs bestimmen, ob das Recordset alle Datensätze verfügt. Nach dem Aufruf **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der **verschieben** Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben, ohne eine Bedingung anwenden. Verwenden Sie die Vorgänge suchen, suchen Sie nach Einträgen in ein Dynaset oder-Diagramm nach der Momentaufnahme Recordsetobjekt, das eine bestimmte Bedingung erfüllen. Um einen Datensatz in einem Tabellentyp Recordset-Objekt zu suchen, rufen Sie `Seek`.  
  
 Wenn das Recordset zu einem Recordset-Diagramm nach der Tabelle verweist, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie nicht den aktuellen Index festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Sie können nicht aufgerufen werden der **MoveFirst** oder `MovePrev` Memberfunktion mit einem Vorwärtscursor Durchführen eines Bildlaufs Snapshot.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt einen bestimmten Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious Methoden" DAO-Hilfe.  
  
##  <a name="open"></a>CDaoRecordset:: Open  
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
 `nOpenType`  
 Einer der folgenden Werte:  
  
- **DbOpenDynaset** einem Typ Dynaset Recordset mit bidirektionalem Bildlauf. Dies ist die Standardeinstellung.  
  
- **Übergeben** ein Tabellentyp Recordset mit bidirektionalem Bildlauf.  
  
- **DbOpenSnapshot** einem-Diagramm nach der Momentaufnahme-Recordset mit bidirektionalem Bildlauf.  
  
 `lpszSQL`  
 Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:  
  
-   Ein **NULL** Zeiger.  
  
-   Der Name der ein oder mehrere Tabledefs und/oder Querydefs (durch Trennzeichen getrennt).  
  
-   Eine SQL **wählen** Anweisung (optional mit einem SQL- **, in denen** oder **ORDERBY** Klausel).  
  
-   Eine Pass-Through-Abfrage.  
  
 `nOptions`  
 Ein oder mehrere der unten aufgeführten Optionen. Der Standardwert ist 0. Folgende Werte sind möglich:  
  
- **DbAppendOnly** können Sie nur neue Datensätze (nur vom Typ Dynaset-Recordset) anfügen. Diese Option also als solcher Datensätze können nur angefügt werden. Die MFC-ODBC-Datenbankklassen haben eine nur Anhängen-Option, die Datensätze abgerufen und angefügt werden kann.  
  
- **DbForwardOnly** das Recordset ist eine Momentaufnahme für Vorwärtscursor Durchführen eines Bildlaufs.  
  
- **DbSeeChanges** eine Ausnahme generiert, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
- **DbDenyWrite** anderer Benutzer können nicht geändert oder Datensätze hinzufügen.  
  
- **DbDenyRead** andere Benutzer können keine Datensätze (nur Tabellentyp Recordset) anzeigen.  
  
- **DbReadOnly** nur Datensätze angezeigt; die anderen Benutzer geändert werden können.  
  
- **DbInconsistent** inkonsistente Updates sind zulässig (nur vom Typ Dynaset-Recordset).  
  
- **DbConsistent** nur konsistenter Updates (nur vom Typ Dynaset-Recordset) zulässig sind.  
  
> [!NOTE]
>  Die Konstanten **DbConsistent** und **DbInconsistent** gegenseitig aus. Sie können eine oder zur anderen, jedoch nicht beide Typen in eine bestimmte Instanz des **öffnen**.  
  
 *pTableDef*  
 Ein Zeiger auf eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt. Diese Version ist nur für den Tabellentyp Recordsets ungültig. Bei Verwendung dieser Option die `CDaoDatabase` Zeiger, die zum Erstellen der `CDaoRecordset` nicht verwendet wird, stattdessen wird die Datenbank, die in der Tabledef befindet verwendet.  
  
 *pQueryDef*  
 Ein Zeiger auf eine [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt. Diese Version ist nur für Dynaset und-Diagramm nach der Momentaufnahme-Recordsets ungültig. Bei Verwendung dieser Option die `CDaoDatabase` Zeiger, die zum Erstellen der `CDaoRecordset` nicht verwendet wird, stattdessen wird die Datenbank, die in der Querydef befindet verwendet.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Aufruf **öffnen**, müssen Sie das Recordset-Objekt erstellen. Dafür stehen verschiedene Möglichkeiten zur Verfügung:  
  
-   Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das bereits geöffnet ist.  
  
-   Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das nicht geöffnet ist. Öffnen des Recordsets einen `CDaoDatabase` -Objekt, aber nicht geschlossen es beim Schließen des Recordset-Objekts.  
  
-   Beim Erstellen des Recordset-Objekts übergeben einer **NULL** Zeiger. Der Recordset-Objekt ruft `GetDefaultDBName` um den Namen der Microsoft Access abrufen. MDB-Datei zu öffnen. Öffnet das Recordset dann eine `CDaoDatabase` Objekt und hält sie zu öffnen, solange das Recordset geöffnet ist. Beim Aufruf **schließen** für das Recordset die `CDaoDatabase` auch-Objekt geschlossen wird.  
  
    > [!NOTE]
    >  Beim Öffnen des Recordsets der `CDaoDatabase` -Objekt, er öffnet die Datenquelle mit nicht exklusiven Zugriff.  
  
 Für die Version des **öffnen** , verwendet der `lpszSQL` Parameter, sobald das Recordset geöffnet ist. Sie können Datensätze in eine von mehreren Möglichkeiten abrufen. Die erste Möglichkeit besteht in der DFX-Funktionen haben Ihrer `DoFieldExchange`. Die zweite Möglichkeit besteht, verwenden Sie die dynamische Bindung durch Aufrufen der `GetFieldValue` Memberfunktion. Diese Optionen können separat oder in Kombination implementiert werden. Wenn sie kombiniert werden, müssen in der SQL-Anweisung selbst beim Aufruf von übergeben **öffnen**.  
  
 Bei Verwendung die zweite Version **öffnen** , in dem Sie übergeben ein `CDaoTableDef` -Objekt, die daraus resultierenden Spalten über binden stehen `DoFieldExchange` und der DFX-Mechanismus, und/oder die Bindung dynamisch über `GetFieldValue`.  
  
> [!NOTE]
>  Sie können nur aufrufen, **öffnen** verwenden eine `CDaoTableDef` für Recordsets der Tabellentyp Objekt.  
  
 Bei Verwendung die dritte Version des **öffnen** , in dem Sie übergeben eine `CDaoQueryDef` -Objekt, dass die Abfrage wird ausgeführt, und die daraus resultierenden Spalten stehen über binden `DoFieldExchange` und der DFX-Mechanismus, und/oder Sie dynamisch binden über `GetFieldValue`.  
  
> [!NOTE]
>  Sie können nur aufrufen, **öffnen** mit eine `CDaoQueryDef` Objekt für Dynaset und Recordsets Momentaufnahme vom Typ.  
  
 Für die erste Version des **öffnen** , verwendet der `lpszSQL` Parameter, Datensätze werden die ausgewählten basierend auf Kriterien, die in der folgenden Tabelle gezeigt.  
  
|Der Wert des Parameters `lpszSQL`.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||  
|Eine durch Trennzeichen getrennte Liste ein oder mehrere Tabledefs und/oder Querydef Namen.|Alle Spalten dargestellt, der `DoFieldExchange`.|`"Customer"`|  
|**Wählen Sie** Spaltenliste **FROM** Tabellenliste|Die angegebenen Spalten von der angegebenen Tabledef(s) und/oder Querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 Der übliche Vorgehensweise ist die Übergabe **NULL** auf **öffnen**; in diesem Fall **öffnen** Aufrufe `GetDefaultSQL`, eine überschreibbare Memberfunktion, die Klassen-Assistent beim Erstellen generiert einer `CDaoRecordset`-Klasse. Dieser Wert gibt die Tabledef(s) und/oder Querydef Namen in ClassWizard angegebenen. Sie können stattdessen andere Informationen im `lpszSQL`-Parameter angeben.  
  
 Jede Übergabe **öffnen** eine endgültige SQL-Zeichenfolge für die Abfrage erstellt (die Zeichenfolge möglicherweise die SQL **, in dem** und **ORDERBY** Klauseln angefügt, um die `lpszSQL` Sie eine Zeichenfolge weitergegeben wurde) und führt dann die Abfrage. Sie können die erstellte Zeichenfolge überprüfen, durch den Aufruf `GetSQL` nach dem Aufruf **öffnen**.  
  
 Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 Wenn Sie Optionen für das Recordset, z. B. einen Filter oder eine Sortierung festlegen möchten, legen `m_strSort` oder **M_strFilter** nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf **öffnen**. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie **Requery**.  
  
 Beim Aufrufen **öffnen** auf eine Dynaset oder Snapshot-Type-Recordset, oder wenn die Datenquelle auf eine SQL-Anweisung oder einer Tabledef, die eine angefügte Tabelle darstellt verweist, können Sie keine **übergeben** für den Typ -Argument auf. Wenn Sie dies tun, löst MFC eine Ausnahme aus. Um zu bestimmen, ob ein Objekt Tabledef eine angefügte Tabelle darstellt, erstellen eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt, und rufen die [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Memberfunktion.  
  
 Verwenden der **DbSeeChanges** auszugeben, wenn Sie Änderungen, die von einem anderen Benutzer oder ein anderes Programm auf Ihrem Computer ausgeführt wird, wenn Sie bearbeiten oder löschen den gleichen Datensatz abfangen möchten. Wenn zwei Benutzer beginnen, bearbeiten den gleichen Datensatz, der erste Benutzer aufrufen, z. B. die **Update** Memberfunktion erfolgreich ausgeführt wird. Wenn **Update** wird aufgerufen, durch den zweiten Benutzer eine `CDaoException` ausgelöst wird. Auf ähnliche Weise, wenn der zweite Benutzer versucht, rufen Sie **löschen** So löschen Sie den Datensatz, und es bereits geändert wurde der erste Benutzer, eine `CDaoException` auftritt.  
  
 In der Regel, wenn der Benutzer dies erhält `CDaoException` beim Aktualisieren des Datensatzes, Code den Inhalt der Felder aktualisieren und die geänderten Werte abrufen. Tritt die Ausnahme gerade gelöscht, konnte der Code die Daten des neuen Datensatzes angezeigt werden für den Benutzer und eine Meldung, dass die Daten zuletzt geändert wurden. An diesem Punkt kann Ihr Code eine Bestätigung anfordern, dass der Benutzer weiterhin den Datensatz löschen möchte.  
  
> [!TIP]
>  Verwenden Sie die Bildlaufoption Vorwärtscursor ( **DbForwardOnly**) zur Verbesserung der Leistung, wenn Ihre Anwendung eine Pass-through ein Recordset durchführt geöffnet, aus einer ODBC-Datenquelle.  
  
 Verwandte Informationen finden Sie im Thema "OpenRecordset Method" DAO-Hilfe.  
  
##  <a name="requery"></a>CDaoRecordset::Requery  
 Rufen Sie diese Memberfunktion um neu zu erstellen (aktualisieren) einem Recordset.  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>Hinweise  
 Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 In der Reihenfolge für das Recordset entsprechend der Hinzufügungen und löschungen, die Sie oder andere Benutzer an der Datenquelle ausführen möchten, müssen Sie das Recordset erstellen, durch Aufruf **Requery**. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer ihre vorhandene Datensätze (aber nicht Additions) Stellen angezeigt. Wenn das Recordset eine Momentaufnahme ist, müssen Sie aufrufen **Requery** auf Änderungen von anderen Benutzern als auch Hinzufügungen und löschungen sind.  
  
 Rufen Sie für ein Dynaset oder eine Momentaufnahme, **Requery** jederzeit das Recordset mit Parameterwerten neu erstellt werden sollen. Legen Sie die neue filtern oder sortieren, indem Sie [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) vor dem Aufruf **Requery**. Neue Parameter festlegen, Parameterdatenmember vor dem Aufruf neue Werte zuweisen **Requery**.  
  
 Schlägt der Versuch, das Recordset neu erstellen, wird das Recordset geschlossen. Vor dem Aufruf **Requery**, können Sie bestimmen, ob das Recordset durch den Aufruf erneut abgefragt werden kann die [CanRestart](#canrestart) Memberfunktion. `CanRestart`garantiert nicht, dass **Requery** wird erfolgreich ausgeführt.  
  
> [!CAUTION]
>  Rufen Sie **Requery** erst nach dem aufgerufenen **öffnen**.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Kann nicht aufgerufen werden **Requery** auf eine Dynaset oder Snapshot-Type-Recordset Aufrufen `CanRestart` 0 zurück, noch können Sie es auf einem Recordset-Diagramm nach der Tabelle.  
  
 Wenn beide `IsBOF` und `IsEOF` ungleich NULL zurückgeben, nach dem Aufruf **Requery**, die Abfrage hat keine Datensätze und das Recordset enthalten keine Daten zurückgegeben.  
  
 Verwandte Informationen finden Sie im Thema "Requery-Methode" DAO-Hilfe.  
  
##  <a name="seek"></a>CDaoRecordset::Seek  
 Rufen Sie diese Memberfunktion um den Datensatz in einem Recordset-Objekt vom Typ indizierte Tabelle zu suchen, die die angegebenen Kriterien für den aktuellen index, und vergewissern, dass der aktuelle Datensatz erfüllt.  
  
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
 `lpszComparison`  
 Einer der folgenden Ausdrücke: "<","\<=", "=" "> =", oder ">".  
  
 `pKey1`  
 Ein Zeiger auf eine [COleVariant](../../mfc/reference/colevariant-class.md) , deren Wert dem ersten Feld im Index entspricht. Erforderlich.  
  
 *pKey2*  
 Ein Zeiger auf eine `COleVariant` , dessen Wert entspricht dem zweiten Feld im Index, sofern vorhanden. Standardmäßig **NULL**.  
  
 *pKey3*  
 Ein Zeiger auf eine `COleVariant` , dessen Wert entspricht dem dritten Feld im Index, sofern vorhanden. Standardmäßig **NULL**.  
  
 *pKeyArray*  
 Ein Zeiger auf ein Array von Variant. Die Größe des Arrays entspricht der Anzahl der Felder im Index.  
  
 *nKeys*  
 Eine ganze Zahl, die Größe des Arrays, also die Anzahl der Felder im Index entspricht.  
  
> [!NOTE]
>  Geben Sie keine Platzhalter in den Schlüsseln. Bewirkt, dass Platzhalter `Seek` ohne übereinstimmende Datensätze zurückgegeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die zweite (Array) Version der `Seek` Indizes vier Felder oder mehr zu behandeln.  
  
 `Seek`Ermöglicht hohe Leistung einen Index zu suchen, die auf den Tabellentyp Recordsets. Sie müssen den aktuellen Index festlegen, durch den Aufruf `SetCurrentIndex` vor dem Aufruf `Seek`. Wenn der Index ein nicht eindeutig oder Primärschlüsselfelder, identifiziert `Seek` sucht nach dem ersten Datensatz, der die Kriterien erfüllt. Wenn Sie einen Index nicht festgelegt, wird eine Ausnahme ausgelöst.  
  
 Beachten Sie, dass, wenn Sie eine Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekte müssen explizit ANSI deklariert werden. Dies kann geschehen, indem Sie mit der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form-Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Beim Aufruf `Seek`, Sie übergeben ein oder mehrere Schlüsselwerte und einen Vergleichsoperator ("<","\<=", "=" "> =", oder ">"). `Seek`durchsucht die angegebene Schlüsselfelder und sucht nach dem ersten Datensatz, der die vom angegebenen Kriterien erfüllt `lpszComparison` und `pKey1`. Einmal gefunden, `Seek` ungleich NULL zurückgibt, und macht diesen Datensatz als aktuellen. Wenn `Seek` keine Übereinstimmung findet `Seek` gibt NULL zurück, und der aktuelle Datensatz ist nicht definiert. Bei DAO direkt zu verwenden, müssen Sie explizit die Eigenschaft NoMatch einchecken.  
  
 Wenn `lpszComparison` ist "=" "> =", oder ">", `Seek` beginnt am Anfang des Indexes. Wenn `lpszComparison` ist "<" oder "< =", `Seek` beginnt am Ende des Indexes und rückwärts durchsucht, es sei denn, es doppelte Einträge am Ende sind. In diesem Fall `Seek` beginnt an einen beliebigen Eintrag für die doppelte Einträge am Ende des Indexes.  
  
 Es muss nicht in ein aktueller Datensatz werden bei Verwendung von `Seek`.  
  
 Verwenden Sie zum Suchen eines Datensatzes in einem Dynaset oder Snapshot-Type-Recordset, das eine bestimmte Bedingung erfüllt, die suchen-Vorgänge. Verwenden Sie die Move-Vorgänge von Datensatz zu Datensatz verschoben, um alle Datensätze, nicht nur diejenigen, die eine bestimmte Bedingung erfüllen.  
  
 Kann nicht aufgerufen werden `Seek` auf einer angefügten Tabelle eines beliebigen eingeben, da der verbundene Tabellen als Dynaset oder-Diagramm nach der Momentaufnahme Recordsets hergestellt werden müssen. Allerdings beim Aufrufen `CDaoDatabase::Open` um eine installierbare ISAM-Datenbank direkt zu öffnen, rufen Sie `Seek` für Tabellen in dieser Datenbank zwar die Leistung möglicherweise beeinträchtigt.  
  
 Verwandte Informationen finden Sie im Thema "Seek-Methode" DAO-Hilfe.  
  
##  <a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition  
 Legt die relative Datensatznummer des aktuellen Datensatzes des Recordset-Objekts.  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *lPosition*  
 Entspricht der Position des aktuellen Datensatzes im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `SetAbsolutePosition` ermöglicht es Ihnen, den aktuellen Datensatz Zeiger zu einem bestimmten Datensatz basierend auf ihre Ordnungsposition in einer Dynaset oder Snapshot-Type-Recordset zu positionieren. Sie können auch die aktuelle Datensatznummer bestimmen, durch den Aufruf [GetAbsolutePosition](#getabsoluteposition).  
  
> [!NOTE]
>  Diese Memberfunktion gilt nur für Dynaset und-Diagramm nach der Momentaufnahme Recordsets zur Verfügung.  
  
 Der Wert der AbsolutePosition-Eigenschaft für das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz des Recordsets. Festlegen eines Werts größer als die Anzahl der aufgefüllten Datensätze, löst MFC eine Ausnahme auslöst. Sie können die Anzahl der aufgefüllten Datensätze im Recordset bestimmen, durch Aufrufen der `GetRecordCount` Memberfunktion.  
  
 Wenn der aktuelle Datensatz gelöscht wird, der AbsolutePosition-Eigenschaftswert ist nicht definiert, und löst MFC eine Ausnahme aus, wenn darauf verwiesen wird. Neue Datensätze werden am Ende der Sequenz hinzugefügt.  
  
> [!NOTE]
>  Diese Eigenschaft dient nicht als Ersatz-Datensatznummer verwendet werden. Lesezeichen sind weiterhin die empfohlene Methode der beibehalten und die Rückgabe an einer angegebenen Position und die einzige Möglichkeit, den aktuellen Datensatz für alle Typen des Recordset-Objekte zu positionieren, die Lesezeichen unterstützen. Insbesondere ändert die Position eines bestimmten Datensatzes auf, wenn vorhergehenden Datensätze gelöscht werden. Es gibt keine Garantie dafür, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets nicht garantiert ist, es sei denn, sie mit der Verwendung einer SQL-Anweisung erstellt wird auch ein  **ORDERBY** Klausel.  
  
 Verwandte Informationen finden Sie im Thema "AbsolutePosition-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setbookmark"></a>CDaoRecordset:: SetBookmark  
 Rufen Sie diese Memberfunktion des Recordsets auf den Datensatz mit dem angegebenen Lesezeichen positionieren.  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) Objekt mit dem Lesezeichenwert für einen bestimmten Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Wenn einem Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen. Sie können das Lesezeichen für den aktuellen Datensatz abzurufen, durch den Aufruf `GetBookmark` und speichern den Wert einer `COleVariant` Objekt. Sie können später an diesen Datensatz zurückgeben, durch den Aufruf `SetBookmark` mit dem gespeicherten Lesezeichenwert.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Beachten Sie, dass, wenn Sie eine Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann geschehen, indem Sie mit der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form-Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie unter den Themen "Lesezeicheneigenschaft" und Bookmarkable-Eigenschaft"DAO-Hilfe.  
  
##  <a name="setcachesize"></a>CDaoRecordset:: SetCacheSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Anzahl von Datensätzen, die zwischengespeichert werden.  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>Parameter  
 `lSize`  
 Gibt die Anzahl der Datensätze. Ein häufig angegebener Wert ist 100. Die Einstellung 0 deaktiviert das Zwischenspeichern. Die Einstellung muss zwischen 5 und 1200 Datensätzen. Der Cache kann eine beträchtliche Menge an Arbeitsspeicher verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Cache ist ein Leerzeichen im lokalen Speicher, der enthält die Daten, die zuletzt vom Server abgerufen werden, dass die Daten erneut angefordert werden, während die Anwendung ausgeführt wird. Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Recordset-Objekte vom Typ Dynaset abruft. Wenn Daten angefordert werden, überprüft der Microsoft Jet-Datenbankmodul den Cache für die angeforderten Daten zunächst anstatt abrufen aus dem Server mehr Zeit in Anspruch. Daten, die nicht von einer ODBC-Datenquelle stammt, ist nicht im Cache gespeichert.  
  
 Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle haben einen lokalen Cache. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt aus der Remotedatenquelle Aufruf der `SetCacheSize` und `SetCacheStart` Memberfunktionen und rufen Sie dann die `FillCache` Memberfunktion oder Schritt durch die Datensätze mit einer der Vorgänge verschieben. Die `lSize` Parameter von der `SetCacheSize` Memberfunktion kann auf die Anzahl der Datensätze, die Ihre Anwendung kann gleichzeitig mit funktionieren basieren. Beispielsweise, wenn Sie ein Recordset als Quelle der Daten verwenden, die auf dem Bildschirm angezeigt werden, Sie übergeben die `SetCacheSize` `lSize` Parameter als 20, 20 Datensätze gleichzeitig anzuzeigen.  
  
 Weitere Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der Hilfe von DAO ein.  
  
##  <a name="setcachestart"></a>CDaoRecordset:: SetCacheStart  
 Rufen Sie diese Memberfunktion, um anzugeben, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden soll.  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) , das Lesezeichen des ersten Datensatzes angibt, in das Recordset zwischengespeichert werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie die Lesezeichenwert eines beliebigen Datensatzes für die `varBookmark` Parameter von der `SetCacheStart` Memberfunktion. Machen Sie den Datensatz, die Sie verwenden möchten, starten den Cache mit den aktuellen Datensatz, ein Lesezeichen für die Verwendung von diesem Datensatz herstellen [SetBookmark](#setbookmark), und übergeben Sie die Lesezeichenwert als Parameter für die `SetCacheStart` Memberfunktion.  
  
 Das Microsoft Jet-Datenbankmodul Datensätze innerhalb des Bereichs der Cache aus dem Cache anfordert, und fordert Datensätze außerhalb des Bereichs Cache vom Server.  
  
 Datensätze, die aus dem Cache abgerufene spiegeln nicht gleichzeitig auf die Quelldaten von anderen Benutzern vorgenommene Änderungen.  
  
 Übergeben, um ein Update aller zwischengespeicherten Daten zu erzwingen, die `lSize` Parameter `SetCacheSize` als 0 (null) aufrufen `SetCacheSize` erneut mit der Größe des Caches Sie ursprünglich angefordert hatten, und rufen dann die `FillCache` Memberfunktion.  
  
 Beachten Sie, dass, wenn Sie eine Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann geschehen, indem Sie mit der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form-Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie im Thema CacheSize, CacheStart-Eigenschaften"in der DAO-Hilfe.  
  
##  <a name="setcurrentindex"></a>CDaoRecordset:: SetCurrentIndex  
 Rufen Sie diese Memberfunktion, um einen Index für einen Tabellentyp Recordset festlegen.  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 Ein Zeiger mit dem Namen des Indexes festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 Datensätze in den Basistabellen werden nicht in einer bestimmten Reihenfolge gespeichert. Wenn Sie einen Index festlegen, ändert die Reihenfolge der Datensätze aus der Datenbank zurückgegeben, aber er hat keinen Einfluss auf die Reihenfolge, in der die Datensätze gespeichert werden. Der angegebene Index muss bereits definiert sein. Wenn Sie versuchen, ein Indexobjekt verwendet wird, die nicht vorhanden ist oder wenn der Index nicht festgelegt ist, beim Aufrufen von [Seek](#seek), löst MFC eine Ausnahme.  
  
 Sie können einen neuen Index für die Tabelle erstellen, durch den Aufruf [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) und den neuen Index auf die Auflistung der Indizes des zugrunde liegenden Tabledef anfügen, durch den Aufruf [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#append), und Klicken Sie dann erneut öffnen des Recordsets.  
  
 Aus einem Recordset-Diagramm nach der Tabelle zurückgegebenen Datensätze können nur von den Indizes, die für die zugrunde liegenden Tabledef definierten sortiert werden. Um Datensätze in einer anderen Reihenfolge sortieren zu können, können Sie öffnen ein Dynaset oder Snapshot-Type-Recordset mit einer SQL **ORDERBY** -Klausel in gespeicherten [CDaoRecordset::m_strSort](#m_strsort).  
  
 Weitere Informationen finden Sie im Thema "Indexobjekt" und die Definition "aktuellen Index" DAO-Hilfe.  
  
##  <a name="setfielddirty"></a>CDaoRecordset:: SetFieldDirty  
 Rufen Sie diese Memberfunktion zum Kennzeichnen der Felddatenmember des Recordset-Objekts als geändert oder als unverändert.  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des eine felddatenelement im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember der Recordset gekennzeichnet sind. (C++ **NULL** entspricht nicht dem als Null in der Terminologie von Datenbanken, d. h. "kann kein Wert".)  
  
 `bDirty`  
 **"True"** ist der Felddatenmember als "(geändert) modifizierte Seiten" markiert werden. Andernfalls **"false"** ist das felddatenelement als "(unverändert) bereinigen" markiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Markieren von Feldern als unverändert wird sichergestellt, dass das Feld nicht aktualisiert wird.  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld dirty automatisch, sodass Sie nur selten aufrufen müssen `SetFieldDirty` selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten werden explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert in die Felddaten ist Member. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDONULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, ist dann ändern den Wert des Felds nicht automatisch das Feld als modifizierte festgelegt. In diesem Fall werden müssen das Feld als modifizierte explizit festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion auf, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mit **NULL** für das erste Argument der Funktion die Funktion für alle gelten **OutputColumn** Felder, nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#6](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder sind nicht betroffen.  
  
 Auf einer **Param**, geben Sie an die tatsächliche Adresse der Person **Param** auf, wie z. B. zusammenarbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase#7](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 Dies bedeutet, dass Sie nicht alle festlegen **Param** Felder **NULL**, wie Sie mit **OutputColumn** Felder.  
  
 `SetFieldDirty`wird durch implementiert `DoFieldExchange`.  
  
##  <a name="setfieldnull"></a>CDaoRecordset::SetFieldNull  
 Rufen Sie diese Memberfunktion zum Kennzeichnen der Felddatenmember des Recordset-Objekts als Null (insbesondere mit kein Wert) oder als nicht Null.  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des eine felddatenelement im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember der Recordset gekennzeichnet sind. (C++ **NULL** entspricht nicht dem als Null in der Terminologie von Datenbanken, d. h. "kann kein Wert".)  
  
 `bNull`  
 Wert ungleich NULL, wenn die Felddatenmember gekennzeichnet wird, dass kein Wert (Null) ist. Andernfalls 0, wenn das felddatenelement wird als ungleich Null gekennzeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 `SetFieldNull`wird für Felder im gebundenen verwendet die `DoFieldExchange` Mechanismus.  
  
 Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) modifizierte Seiten" markiert. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits über Werte verfügen oder Null sind. Wenn es nicht angemessen zu sorgen, dass ein Feld Null ist, ist eine [CDaoException](../../mfc/reference/cdaoexception-class.md) ausgelöst wird.  
  
 Wenn Sie die doppelte Pufferung-Mechanismus, z. B. verwenden gegebenenfalls speziell ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert ein, rufen Sie `SetFieldNull` mit `bNull` festgelegt **"true"** so kennzeichnen Sie es als Null. Wenn ein Feld wurde zuvor Null markiert, und jetzt Sie ihm einen Wert zuzuweisen möchten, legen Sie einfach den neuen Wert. Sie müssen nicht mit der Null-Flag entfernen `SetFieldNull`. Aufrufen, um zu bestimmen, ob das Feld Null sein darf, [IsFieldNullable](#isfieldnullable).  
  
 Wenn Sie die doppelte Pufferung Mechanismus nicht verwenden, ist ändern Sie den Wert des Felds nicht automatisch das Feld als dirty und ungleich Null festgelegt. Sie müssen die Felder speziell dirty und ungleich Null festlegen. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
 DFX-Mechanismus setzt die Verwendung von **PSEUDONULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion auf, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mit **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder, nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#8](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder sind nicht betroffen.  
  
##  <a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue  
 Rufen Sie diese Memberfunktion um den Wert eines Felds durch Ordnungsposition oder durch Ändern des Werts der Zeichenfolge festzulegen.  
  
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
 `lpszName`  
 Ein Zeiger auf eine Zeichenfolge, die mit dem Namen eines Felds.  
  
 `varValue`  
 Ein Verweis auf eine [COleVariant](../../mfc/reference/colevariant-class.md) Objekt, das den Wert des Felds Inhalt enthält.  
  
 `nIndex`  
 Eine ganze Zahl, die die Ordnungsposition in das Recordset Fields-Auflistung (nullbasiert) des Felds darstellt.  
  
 `lpszValue`  
 Ein Zeiger auf eine Zeichenfolge, die den Wert des Felds Inhalt enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `SetFieldValue` und [GetFieldValue](#getfieldvalue) Felder dynamisch zur Laufzeit statt statisch Binden von Spalten mit Binden der [DoFieldExchange](#dofieldexchange) Mechanismus.  
  
 Beachten Sie, dass ein Unicode-Recordset nicht erstellt werden, entweder eine Form der verwenden müssen `SetFieldValue` , die keinen enthalten eine `COleVariant` Parameter, oder die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann geschehen, indem Sie mit der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form-Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull  
 Rufen Sie diese Memberfunktion, um das Feld auf einen Null-Wert festgelegt.  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Felds im Recordset, für die Suche über einen nullbasierten Index.  
  
 `lpszName`  
 Der Name des Felds im Recordset, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 C++ **NULL** entspricht nicht dem als Null, womit, in der Terminologie von Datenbanken "kann kein Wert".  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" DAO-Hilfe.  
  
##  <a name="setlockingmode"></a>CDaoRecordset::SetLockingMode  
 Rufen Sie diese Memberfunktion zum Festlegen des Typs von Sperren für das Recordset.  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>Parameter  
 *bPessimistic*  
 Ein Flag, das den Typ der Sperre angibt.  
  
### <a name="remarks"></a>Hinweise  
 Pessimistische Sperren beim aktiviert ist, ist die 2 KB-Seite, die mit dem Datensatz, der von Ihnen bearbeiteten ist gesperrt, sobald Sie rufen die **bearbeiten** Memberfunktion. Die Seite ist nicht gesperrt, beim Aufrufen der **Update** oder **schließen** Memberfunktion oder die Vorgänge zum Verschieben oder suchen.  
  
 Wenn optimistischen Sperrung wirksam ist, wird die 2 KB-Seite, die mit dem Datensatz gesperrt, nur, wenn der Eintrag aktualisiert wird, mit der **Update** Memberfunktion.  
  
 Wenn eine Seite gesperrt ist, kann kein anderer Benutzer Datensätze auf derselben Seite bearbeiten. Beim Aufrufen `SetLockingMode` und übergeben Sie einen Wert ungleich NULL und ein anderer Benutzer hat bereits die Seite gesperrt, eine Ausnahme wird ausgelöst, wenn Sie rufen **bearbeiten**. Andere Benutzer können Daten aus gesperrte Seiten lesen.  
  
 Beim Aufrufen `SetLockingMode` aufrufen, mit dem Wert 0 (null) und höher **Update** während die Seite von einem anderen Benutzer gesperrt ist, wird eine Ausnahme auftritt. Um die Änderungen an Ihrem Datensatz von einem anderen Benutzer (und Ihre Änderungen verwerfen), rufen Sie die `SetBookmark` Memberfunktion mit dem Lesezeichenwert, der den aktuellen Datensatz.  
  
 Bei der Arbeit mit ODBC-Datenquellen wird das Sperrverhalten immer optimistic.  
  
##  <a name="setparamvalue"></a>CDaoRecordset::SetParamValue  
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
 `nIndex`  
 Die numerische Position des Parameters in der Querydef Parameters-Auflistung.  
  
 `var`  
 Der festzulegende Wert; finden Sie unter "Hinweise".  
  
 `lpszName`  
 Der Name des Parameters, dessen Wert festgelegt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Der Parameter muss bereits als Teil der SQL-Zeichenfolge des Recordsets eingerichtet wurde. Sie können die Parameter nach Namen oder die Indexposition in der Auflistung zugreifen.  
  
 Geben Sie den Wert für die festzulegende als ein `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md). Beachten Sie, dass, wenn Sie eine Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann geschehen, indem Sie mit der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form-Konstruktor mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
##  <a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull  
 Rufen Sie diese Memberfunktion um den Parameter auf einen Null-Wert festgelegt.  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Felds im Recordset, für die Suche über einen nullbasierten Index.  
  
 `lpszName`  
 Der Name des Felds im Recordset, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 C++ **NULL** entspricht nicht dem als Null, womit, in der Terminologie von Datenbanken "kann kein Wert".  
  
##  <a name="setpercentposition"></a>CDaoRecordset:: SetPercentPosition  
 Rufen Sie diese Memberfunktion, um einen Wert festzulegen, der die ungefähre Position des aktuellen Datensatzes in das Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset ändert.  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *fPosition*  
 Eine Zahl zwischen 0 und 100.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Arbeit mit einem Dynaset oder Snapshot-Type-Recordset zu füllen zunächst das Recordset umgezogen bis zum letzten Datensatz vor dem Aufruf `SetPercentPosition`. Beim Aufrufen `SetPercentPosition` vor der vollständigen Auffüllung das Recordset, wird der Betrag der Verschiebung relativ zur Anzahl der Datensätze verfügbar, weil durch den Wert des angegebenen [GetRecordCount](#getrecordcount). Sie können wechselt zur letzten Datensatzes durch Aufrufen von `MoveLast`.  
  
 Sobald Sie aufrufen `SetPercentPosition`, zum aktuellen Thread der Datensatz der ungefähren Position, dieser Wert entspricht.  
  
> [!NOTE]
>  Aufrufen von `SetPercentPosition` so verschieben Sie der aktuelle Datensatz zu einem bestimmten Datensatz in einem Recordset wird nicht empfohlen. Rufen Sie die [SetBookmark](#setbookmark) Memberfunktion stattdessen.  
  
 Verwandte Informationen finden Sie im Thema "PercentPosition-Eigenschaft" DAO-Hilfe.  
  
##  <a name="update"></a>CDaoRecordset::Update  
 Rufen Sie diese Memberfunktion auf, nach einem Aufruf von der `AddNew` oder **bearbeiten** Memberfunktion.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist erforderlich, um das Abschließen der `AddNew` oder **bearbeiten** Vorgang.  
  
 Beide `AddNew` und **bearbeiten** vorbereiten Bearbeitungspuffer, in dem die hinzugefügten oder bearbeiteten Daten platziert ist, für die Speicherung der Datenquelle. **Update** speichert die Daten. Nur Felder erkannt, dass geändert oder markiert werden aktualisiert.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **Update** aufrufen (und der entsprechenden `AddNew` oder **bearbeiten** aufrufen) Teil einer Transaktion.  
  
> [!CAUTION]
>  Beim Aufrufen **Update** ohne Aufruf eines `AddNew` oder **bearbeiten**, **Update** löst eine `CDaoException`. Beim Aufrufen `AddNew` oder **bearbeiten**, rufen Sie **Update** vor dem Aufruf [MoveNext](#movenext) oder schließen Sie das Recordset oder Verbindung mit der Datenquelle. Andernfalls sind Ihre Änderungen verloren gehen, ohne Benachrichtigung.  
  
 Der Datensatz bleibt gesperrt, ab dem Zeitpunkt, wenn das Recordset-Objekt in einer mehrbenutzerumgebung pessimistisch gesperrt ist, **bearbeiten** wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz gesperrt und mit dem Datensatz der vorab bearbeitete verglichen werden, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen **bearbeiten**, **Update** fehl und MFC eine Ausnahme auslöst. Sie können ändern, dass der Sperrmodus mit `SetLockingMode`.  
  
> [!NOTE]
>  Eingeschränktes Sperren wird immer auf externe Datenbank-Formaten, z. B. ODBC und installierbaren ISAM verwendet.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate Method", "Method löschen", "LastModified-Eigenschaft", "Update-Methode" und "EditMode-Eigenschaft" DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)
