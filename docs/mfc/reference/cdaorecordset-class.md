---
title: CDaoRecordset-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- recordsets, types
- CDaoRecordset class
- records, CDaoRecordSet
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3d3d830a7d423a2653819e9cbf160538e486cfb0
ms.lasthandoff: 02/24/2017

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
|[AddNew](#addnew)|Vorbereitet für einen neuen Datensatz hinzufügen. Rufen Sie [Update](#update) zum Abschluss.|  
|[CDaoRecordset::CanAppend](#canappend)|Gibt einen Wert ungleich NULL, wenn das Recordset über neue Datensätze hinzugefügt werden können die [AddNew](#addnew) Member-Funktion.|  
|[CDaoRecordset::CanBookmark](#canbookmark)|Gibt einen Wert ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|  
|[CDaoRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.|  
|[CDaoRecordset::CanRestart](#canrestart)|Gibt einen Wert ungleich NULL, wenn [Requery](#requery) aufgerufen werden, um die Recordset Abfrage auszuführen.|  
|[CDaoRecordset::CanScroll](#canscroll)|Gibt einen Wert ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|  
|[CDaoRecordset::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDaoRecordset::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|  
|[CDaoRecordset::Close](#close)|Schließt das Recordset.|  
|[CDaoRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang blättern.|  
|[CDaoRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, um die exchange-Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implements-DAO-Datensatzfeldaustausch (DFX).|  
|[CDaoRecordset::Edit](#edit)|Vorbereitet für Änderungen an den aktuellen Datensatz. Rufen Sie **Update** um die Bearbeitung abzuschließen.|  
|[FillCache](#fillcache)|Füllt den gesamten oder einen Teil eines lokalen Caches für ein Recordset-Objekt, das Daten aus einer ODBC-Datenquelle enthält.|  
|[CDaoRecordset::Find](#find)|Sucht nach der ersten, nächsten, vorherigen oder letzten Speicherort einer bestimmten Zeichenfolge in einem Typ Dynaset-Recordset, das den angegebenen Kriterien und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindFirst](#findfirst)|Sucht nach dem ersten Datensatz in einem Dynaset oder Snapshot-Typ-Recordset, das den angegebenen Kriterien und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindLast](#findlast)|Sucht den letzten Datensatz in einem Dynaset oder Snapshot-Typ-Recordset, das den angegebenen Kriterien und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindNext](#findnext)|Sucht den nächsten Datensatz in einem Dynaset oder Snapshot-Typ-Recordset, das den angegebenen Kriterien und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::FindPrev](#findprev)|Sucht den vorherigen Datensatz in einem Dynaset oder Snapshot-Typ-Recordset, das den angegebenen Kriterien und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset:: GetAbsolutePosition](#getabsoluteposition)|Gibt die Nummer des aktuellen Datensatzes des Recordset-Objekts zurück.|  
|[CDaoRecordset:: GetBookmark](#getbookmark)|Gibt einen Wert, der das Lesezeichen für einen Datensatz darstellt.|  
|[CDaoRecordset::GetCacheSize](#getcachesize)|Gibt einen Wert, der angibt, die Anzahl der Datensätze in einem Recordset vom Typ Dynaset mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.|  
|[CDaoRecordset::GetCacheStart](#getcachestart)|Gibt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden.|  
|[CDaoRecordset::GetCurrentIndex](#getcurrentindex)|Gibt eine `CString` mit dem Namen des Indexes die zuletzt für eine indizierte Tabellentyp verwendet `CDaoRecordset`.|  
|[CDaoRecordset::GetDateCreated](#getdatecreated)|Gibt das Datum und die Uhrzeit der zugrunde liegenden Basistabelle ein `CDaoRecordset` Objekt erstellt wurde|  
|[CDaoRecordset::GetDateLastUpdated](#getdatelastupdated)|Gibt das Datum und Uhrzeit der letzten Änderung für den Entwurf einer zugrunde liegenden Basistabelle ein `CDaoRecordset` Objekt.|  
|[CDaoRecordset::GetDefaultDBName](#getdefaultdbname)|Gibt den Namen der Standard-Datenquelle zurück.|  
|[CDaoRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, um die Standard-SQL-Zeichenfolge ausführen abzurufen.|  
|[CDaoRecordset::GetEditMode](#geteditmode)|Gibt einen Wert, der den Bearbeitungsstatus für den aktuellen Datensatz angibt.|  
|[CDaoRecordset::GetFieldCount](#getfieldcount)|Gibt einen Wert, der die Anzahl der Felder in einem Recordset darstellt.|  
|[CDaoRecordset::GetFieldInfo](#getfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurückgegeben in das Recordset.|  
|[CDaoRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CDaoRecordset::GetIndexCount](#getindexcount)|Ruft die Anzahl der Indizes in einer Tabelle mit dem zugrunde liegenden Recordset ab.|  
|[CDaoRecordset::GetIndexInfo](#getindexinfo)|Gibt verschiedene Arten von Informationen zu einem Index zurück.|  
|[CDaoRecordset::GetLastModifiedBookmark](#getlastmodifiedbookmark)|Um zu bestimmen, der den zuletzt hinzugefügten oder aktualisierte Datensatz verwendet.|  
|[CDaoRecordset::GetLockingMode](#getlockingmode)|Gibt einen Wert, der die Art der Sperrung, die angibt während der Bearbeitung wirksam ist.|  
|[CDaoRecordset::GetName](#getname)|Gibt eine `CString` mit dem Namen des Recordset-Objekts.|  
|[CDaoRecordset::GetParamValue](#getparamvalue)|Ruft den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter-Objekt gespeichert.|  
|[CDaoRecordset:: GetPercentPosition](#getpercentposition)|Gibt die Position des aktuellen Datensatzes als Prozentsatz der Gesamtzahl der Datensätze.|  
|[CDaoRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze in einem Recordset-Objekt zugegriffen.|  
|[CDaoRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset verwendet.|  
|[CDaoRecordset::GetType](#gettype)|Wird aufgerufen, um den Typ eines Recordset-Objekts zu bestimmen: Tabellentyp, vom Typ Dynaset oder Snapshot-Typ.|  
|[CDaoRecordset::GetValidationRule](#getvalidationrule)|Gibt eine `CString` mit dem Wert, der Daten überprüft werden, wenn es in ein Feld eingegeben werden.|  
|[CDaoRecordset::GetValidationText](#getvalidationtext)|Ruft den Text ab, der angezeigt wird, wenn eine Validierungsregel nicht erfüllt wird.|  
|[CDaoRecordset::IsBOF](#isbof)|Gibt einen Wert ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.|  
|[CDaoRecordset::IsDeleted](#isdeleted)|Gibt einen Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist.|  
|[CDaoRecordset::IsEOF](#iseof)|Gibt einen Wert ungleich NULL, wenn das Recordset wurde nach dem letzten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.|  
|[CDaoRecordset::IsFieldDirty](#isfielddirty)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CDaoRecordset::IsFieldNull](#isfieldnull)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz (mit kein Wert) Null ist.|  
|[CDaoRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld des aktuellen Datensatzes auf Null festgelegt werden kann (mit kein Wert) zurück.|  
|[CDaoRecordset::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn [öffnen](#open) zuvor aufgerufen wurde.|  
|[CDaoRecordset::Move](#move)|Positioniert das Recordset mit einer angegebenen Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|  
|[CDaoRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz für den ersten Datensatz im Recordset.|  
|[CDaoRecordset::MoveLast](#movelast)|Den aktuellen Datensatz positioniert auf den letzten Datensatz im Recordset.|  
|[CDaoRecordset::MoveNext](#movenext)|Den aktuellen Datensatz positioniert auf den nächsten Datensatz im Recordset.|  
|[CDaoRecordset::MovePrev](#moveprev)|Den aktuellen Datensatz positioniert auf den vorherigen Datensatz im Recordset.|  
|[CDaoRecordset:: Open](#open)|Erstellt einen neuen Datensatz aus einer Tabelle, Dynaset oder Snapshot.|  
|[CDaoRecordset::Requery](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|  
|[CDaoRecordset::Seek](#seek)|Sucht den Datensatz in einem Typ indizierte Tabelle Recordset-Objekt, das die angegebenen Kriterien für den aktuellen Index und macht diesen zum aktuellen Datensatz erfüllt.|  
|[CDaoRecordset::SetAbsolutePosition](#setabsoluteposition)|Legt die Nummer des aktuellen Datensatzes des Recordset-Objekts.|  
|[CDaoRecordset:: SetBookmark](#setbookmark)|Positioniert das Recordset einen Datensatz mit dem angegebenen Lesezeichen.|  
|[CDaoRecordset:: SetCacheSize](#setcachesize)|Legt einen Wert, der angibt, die Anzahl der Datensätze in einem Recordset vom Typ Dynaset mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.|  
|[CDaoRecordset:: SetCacheStart](#setcachestart)|Legt einen Wert, der angibt, das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden.|  
|[CDaoRecordset:: SetCurrentIndex](#setcurrentindex)|Wird aufgerufen, um einen Index für ein Recordset vom Typ Tabelle festzulegen.|  
|[CDaoRecordset:: SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz, als geändert.|  
|[CDaoRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds im aktuellen Datensatz auf Null (kein Wert mit) fest.|  
|[CDaoRecordset::SetFieldValue](#setfieldvalue)|Legt den Wert eines Felds in einem Recordset fest.|  
|[CDaoRecordset::SetFieldValueNull](#setfieldvaluenull)|Legt den Wert eines Felds in einem Recordset auf Null fest. (Wenn kein Wert).|  
|[CDaoRecordset::SetLockingMode](#setlockingmode)|Legt einen Wert, der den Typ der erfolgt, um die während der Bearbeitung vollzogen angibt.|  
|[CDaoRecordset::SetParamValue](#setparamvalue)|Stellt den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter-Objekt gespeichert|  
|[CDaoRecordset::SetParamValueNull](#setparamvaluenull)|Legt den aktuellen Wert des angegebenen Parameters auf Null (kein Wert mit).|  
|[CDaoRecordset:: SetPercentPosition](#setpercentposition)|Legt die Position des aktuellen Datensatzes an einem Speicherort auf einen Prozentsatz der Gesamtzahl der Datensätze in einem Recordset entsprechend fest.|  
|[CDaoRecordset::Update](#update)|Schließt eine `AddNew` oder **bearbeiten** Vorgang durch, indem die neuen oder bearbeiteten Daten für die Datenquelle zu speichern.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDaoRecordset:: M_bcheckcachefordirtyfields](#m_bcheckcachefordirtyfields)|Enthält ein Flag, der angibt, ob Felder automatisch als geändert markiert werden.|  
|[CDaoRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.|  
|[CDaoRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in der Recordset-Klasse – die Anzahl der Parameter zu übergeben, mit die Abfrage des Recordsets|  
|[CDaoRecordset::m_pDAORecordset](#m_pdaorecordset)|Ein Zeiger auf die DAO-Schnittstelle, die zugrunde liegenden Recordset-Objekts.|  
|[CDaoRecordset::m_pDatabase](#m_pdatabase)|Die Quelldatenbank für dieses Resultset. Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) Objekt.|  
|[CDaoRecordset::m_strFilter](#m_strfilter)|Enthält eine Zeichenfolge, die zum Erstellen von SQL **, in denen** Anweisung.|  
|[CDaoRecordset::m_strSort](#m_strsort)|Enthält eine Zeichenfolge, die zum Erstellen von SQL **ORDER BY** Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Bekannt als "Recordsets" `CDaoRecordset` Objekte sind in den folgenden drei Formaten verfügbar:  
  
-   Recordsets vom Typ Tabelle stellen eine Basistabelle, die Sie verwenden können, zu untersuchen, hinzufügen, ändern oder Löschen von Datensätzen aus einer einzelnen Datenbanktabelle dar.  
  
-   Recordsets vom Typ Dynaset sind das Ergebnis einer Abfrage, die aktualisierbare Datensätze haben kann. Diese Recordsets sind eine Gruppe von Datensätzen, die Sie zum Überprüfen, hinzufügen, ändern oder Löschen von Datensätzen in einer zugrunde liegenden Datenbanktabellen verwenden können. Recordsets vom Typ Dynaset kann Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten.  
  
-   Recordsets vom Typ Snapshot sind eine statische Kopie einer Gruppe von Datensätzen, die Sie zum Suchen von Daten oder Generieren von Berichten verwenden können. Diese Datensätze können Felder aus einer oder mehreren Tabellen in einer Datenbank enthalten, aber nicht aktualisiert werden.  
  
 Jedes Formular des Recordsets stellt einen Satz von Datensätzen, die zum Zeitpunkt, wenn das Recordset geöffnet wird. Wenn Sie auf einen Datensatz in einem Recordset vom Typ Tabelle oder ein Recordset vom Typ Dynaset Blättern, spiegelt wider Änderungen an den Datensatz nach dem Öffnen des Recordsets, anderen Benutzern oder anderen Recordsets in Ihrer Anwendung. (Ein Recordset Snapshot-Typ kann nicht aktualisiert werden.) Sie können `CDaoRecordset` direkt oder leiten Sie eine anwendungsspezifische Recordset-Klasse von `CDaoRecordset`. Anschließend können Sie:  
  
-   Führen Sie einen Bildlauf durch die Datensätze.  
  
-   Legen Sie einen Index und schnell suchen Sie nach Einträgen, die mit [Seek](#seek) (nur Recordsets vom Typ Tabelle).  
  
-   Suchen nach Datensätzen, die auf Basis eines Wertevergleichs der Zeichenfolge: "<",></",>\<=", "=", "> =", oder ">" (vom Typ Dynaset und Snapshot-Typ).  
  
-   Aktualisieren Sie die Datensätze zu, und geben Sie Sperrmodus (mit Ausnahme von Recordsets vom Typ Snapshot).  
  
-   Filtern Sie das Recordset, um die Datensätze zu beschränken, auf die Datenquelle aus den verfügbaren auswählt.  
  
-   Sortieren Sie das Recordset.  
  
-   Parametrisieren Sie das Recordset angepasst werden, dessen Auswahl mit Informationen, die erst zur Laufzeit bekannt ist.  
  
 Klasse `CDaoRecordset` stellt eine Schnittstelle ähnlich der Klasse `CRecordset`. Der Hauptunterschied besteht darin, diese Klasse `CDaoRecordset` greift auf Daten über eine (Datenzugriffsobjekt) basierend auf OLE. Klasse `CRecordset` greift auf das DBMS über Open Database Connectivity (ODBC) und einen ODBC-Treiber für dieses DBMS verwaltet.  
  
> [!NOTE]
>  Die DAO-Datenbankklassen unterscheiden sich von den MFC-Datenbankklassen basierend auf Open Database Connectivity (ODBC). Alle DAO-Datenbank-Klassennamen haben das Präfix "CDao". Sie können immer noch Zugriff auf ODBC-Datenquellen mit DAO-Klassen. die DAO-Klassen bieten im Allgemeinen überlegene Funktionen, da sie für das Microsoft Jet-Datenbankmodul spezifisch sind.  
  
 Sie können entweder `CDaoRecordset` direkt oder leiten Sie eine Klasse von `CDaoRecordset`. Um eine Recordset-Klasse in beiden Fällen zu verwenden, öffnen Sie eine Datenbank, und erstellen Sie ein Recordset-Objekt, und übergeben Sie dem Konstruktor einen Zeiger auf die `CDaoDatabase` Objekt. Sie können auch erstellen eine `CDaoRecordset` Objekts, sodass MFC Erstellen eines temporären `CDaoDatabase` -Objekt für Sie. Rufen Sie dann des Recordsets [öffnen](#open) Member-Funktion, die angibt, ob das Objekt ein Recordset vom Typ Tabelle, ein Recordset vom Typ Dynaset oder ein Recordset Snapshot-Typ ist. Aufrufen von **öffnen** wählt Daten aus der Datenbank und ruft den ersten Datensatz.  
  
 Verwenden Sie Member und Datenmember des Objekts, um einen Bildlauf durch die Datensätze und auf sie angewendet werden. Die verfügbaren Vorgänge ist davon abhängig, ob das Objekt ein Recordset vom Typ Tabelle, ein Recordset vom Typ Dynaset oder ein Recordset Momentaufnahme vom Typ ist, und ob es aktualisierbar oder schreibgeschützt ist, dies hängt von der Funktion der Datenbank oder Datenquelle Open Database Connectivity (ODBC). Datensätze zu aktualisieren, die möglicherweise wurde geändert oder hinzugefügt werden, da die **öffnen** aufrufen, rufen Sie die [Requery](#requery) Member-Funktion. Rufen Sie die **schließen** Member-Funktion und zerstören Sie das Objekt aus, wenn Sie damit fertig sind.  
  
 `CDaoRecordset`DAO-Datensatzfeldaustausch (DFX) zur Unterstützung von lesen und Aktualisieren von Datensatzfelder typsicheren C++ Mitglieder verwendet Ihre `CDaoRecordset` oder `CDaoRecordset`-abgeleiteten Klasse. Dynamisches Binden von Spalten in einer Datenbank können Sie auch implementieren, ohne die DFX-Mechanismus mit [GetFieldValue](#getfieldvalue) und [SetFieldValue](#setfieldvalue).  
  
 Weitere Informationen finden Sie im Thema "Recordset-Objekt" in der DAO-Hilfe.  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdao.h  
  
##  <a name="addnew"></a>AddNew  
 Rufen Sie diese Memberfunktion, um einen neuen Datensatz zu einem Recordset vom Typ Tabelle oder Dynaset hinzufügen.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Felder des Datensatzes sind anfangs Null. (In der datenbankterminologie von-Null-man "kein Wert" und ist nicht identisch mit **NULL** in C++.) Um den Vorgang abzuschließen, müssen Sie aufrufen, die [Update](#update) Member-Funktion. **Update** speichert die Änderung an der Datenquelle.  
  
> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten, und führen Sie einen zu einem anderen Datensatz ohne Aufruf Bildlauf **Update**, Ihre Änderungen werden ohne Warnung.  
  
 Wenn Sie einen Datensatz zu einem Recordset vom Typ Dynaset durch Aufrufen von hinzufügen [AddNew](#addnew), der Datensatz ist im Recordset angezeigt und enthalten in der zugrunde liegenden Tabelle, in denen sichtbar auf eine neue `CDaoRecordset` Objekte.  
  
 Die Position des neuen Datensatzes hängt vom Typ der Datensatzgruppe ab:  
  
-   In einem Dynaset-Typ ist Recordset, an der neue Datensatz eingefügt wird nicht garantiert. Dieses Verhalten ist mit Microsoft Jet 3.0 aus Gründen der Leistung und Parallelität. Ist das Ziel dem neu hinzugefügten Datensatz zum aktuellen Datensatz machen, rufen Sie das Lesezeichen des letzten Datensatzes geändert, und zu diesem Lesezeichen verschieben:  
  
 [!code-cpp[NVC_MFCDatabase&#1;](../../mfc/codesnippet/cpp/cdaorecordset-class_1.cpp)]  
  
-   In einem Recordset vom Typ Tabelle, für die ein Index angegeben wurde, werden Datensätze entsprechend ihrer Position in der Sortierreihenfolge zurückgegeben. Wenn kein Index angegeben wurde, werden neue Datensätze am Ende des Recordset-Objekts zurückgegeben.  
  
 Der Datensatz, die vor der `AddNew` bleibt der aktuelle Datensatz. Wenn Sie den neuen Datensatz aktualisieren möchten, und das Recordset Lesezeichen Aufruf unterstützt [SetBookmark](#setbookmark) auf das Lesezeichen, die durch die Einstellung der LastModified-Eigenschaft des zugrunde liegenden DAO-Recordset-Objekts identifiziert. Dies ist nützlich zum Ermitteln des Wert für den Leistungsindikator (automatisch inkrementierten) Felder in einem Datensatz hinzugefügt. Weitere Informationen finden Sie unter [GetLastModifiedBookmark](#getlastmodifiedbookmark).  
  
 Wenn die Datenbank Transaktionen unterstützt, können Sie machen die `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Beachten Sie, die aufgerufen werden soll [CDaoWorkspace::BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans) vor dem Aufruf von `AddNew`.  
  
 Es ist unzulässig, rufen Sie `AddNew` für ein Recordset, dessen [öffnen](#open) Memberfunktion nicht aufgerufen wurde. Ein `CDaoException` wird ausgelöst, wenn Sie aufrufen, `AddNew` für ein Recordset, das angefügt werden kann. Sie können bestimmen, ob das Recordset aktualisierbar, durch Aufrufen von ist [CanAppend](#canappend).  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie auf den Datensatz in der Datenquelle von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus geschrieben werden. Ändern den Wert eines Felds in der Regel das Feld modifizierte automatisch festgelegt, daher nur in seltenen Fällen Sie aufrufen müssen, [SetFieldDirty](#setfielddirty) selbst, aber Sie können manchmal sicherstellen möchten, dass Spalten explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert im Felddatenmember ist. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDO-NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss explizit das Feld modifizierte festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
> [!NOTE]
>  Wenn Einträge doppelt gepuffert sind (d. h. automatische Überprüfung Felder aktiviert), Aufrufen `CancelUpdate` wird die Membervariablen auf die Werte, die sie bisher wiederherstellen `AddNew` oder **bearbeiten** aufgerufen wurde.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate Method", "LastModified-Eigenschaft" und "EditMode-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="canappend"></a>CDaoRecordset::CanAppend  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das zuvor geöffnete Recordset Sie neue Datensätze durch Aufrufen von hinzufügen können der [AddNew](#addnew) Member-Funktion.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Hinzufügen von neuen Datensätzen; andernfalls 0. `CanAppend`Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Thema "Append-Methode" in der DAO-Hilfe.  
  
##  <a name="canbookmark"></a>CDaoRecordset::CanBookmark  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das zuvor geöffnete Recordset Datensätze mithilfe von Lesezeichen einzeln kennzeichnen Sie können.  
  
```  
BOOL CanBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Recordset Lesezeichen, andernfalls 0 unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie vollständig auf Tabellen des Microsoft Jet-Datenbankmoduls basiert Recordsets verwenden, können Lesezeichen außer in Recordsets vom Typ Snapshot, die als Bildlauf vorwärts-Recordsets verwendet werden. Anderer Produkte (externe ODBC-Datenquellen) unterstützen möglicherweise keine Lesezeichen.  
  
 Informationen finden Sie unter dem Thema "Lesezeichenfähig-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="cancelupdate"></a>CDaoRecordset::CancelUpdate  
 Die `CancelUpdate` Memberfunktion bricht alle ausstehenden Updates aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang.  
  
```  
virtual void CancelUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
 Angenommen, eine Anwendung ruft die **bearbeiten** oder `AddNew` Memberfunktion und nicht aufgerufen [Update](#update), `CancelUpdate` bricht alle Änderungen, die nach **bearbeiten** oder `AddNew` aufgerufen wurde.  
  
> [!NOTE]
>  Wenn Einträge doppelt gepuffert sind (d. h. automatische Überprüfung Felder aktiviert), Aufrufen `CancelUpdate` wird die Membervariablen auf die Werte, die sie bisher wiederherstellen `AddNew` oder **bearbeiten** aufgerufen wurde.  
  
 Liegt keine **bearbeiten** oder `AddNew` Vorgang steht, `CancelUpdate` MFC eine Ausnahme ausgelöst wird. Rufen Sie die [GetEditMode](#geteditmode) Member-Funktion, um zu bestimmen, ob es ein ausstehender Vorgang, der abgebrochen werden kann.  
  
 Verwandte Informationen finden Sie im Thema "CancelUpdate Method" in der DAO-Hilfe.  
  
##  <a name="canrestart"></a>CDaoRecordset::CanRestart  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset ermöglicht das Neustarten der Abfrage (Wenn Sie die Datensätze zu aktualisieren) durch Aufrufen der **Requery** Member-Funktion.  
  
```  
BOOL CanRestart();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL **Requery** aufgerufen werden, um die Recordset Abfrage erneut aus, andernfalls 0 ausführen.  
  
### <a name="remarks"></a>Hinweise  
 Recordsets vom Typ Tabelle unterstützen keine **Requery**.  
  
 Wenn **Requery** wird nicht unterstützt, rufen Sie [schließen](#close) dann [öffnen](#open) zum Aktualisieren der Daten. Rufen Sie **Requery** aktualisieren ein Recordset-Objekt zugrunde liegenden Parameterabfrage nach die Werten der Parameter geändert wurden.  
  
 Verwandte Informationen finden Sie im Thema "Startfähige Property" in der DAO-Hilfe.  
  
##  <a name="canscroll"></a>CDaoRecordset::CanScroll  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset Bildlauf ermöglicht.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze, andernfalls 0 durchführen können.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie aufrufen [öffnen](#open) mit **DbForwardOnly**, das Recordset kann nur vorwärts.  
  
 Weitere Informationen finden Sie im Thema "Positionieren des aktuellen Zeiger mit DAO" in der DAO-Hilfe.  
  
##  <a name="cantransact"></a>CDaoRecordset::CanTransact  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset Transaktionen ermöglicht.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die zugrunde liegende Datenquelle Transaktionen, ansonsten 0 unterstützt.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Transaktionen Property" in der DAO-Hilfe.  
  
##  <a name="canupdate"></a>CDaoRecordset::CanUpdate  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset aktualisiert werden kann.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das Recordset aktualisiert werden kann (hinzufügen, aktualisieren und Löschen von Datensätzen), andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Recordset kann schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist oder wenn Sie angegeben **DbReadOnly** für `nOptions` beim Aufruf [öffnen](#open) für das Recordset.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "Delete-Methode", "Update-Methode" und "Updatable-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="cdaorecordset"></a>CDaoRecordset::CDaoRecordset  
 Erstellt ein `CDaoRecordset`-Objekt.  
  
```  
CDaoRecordset(CDaoDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Enthält einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) oder der Wert **NULL**. Wenn dies nicht **NULL** und `CDaoDatabase` des Objekts **öffnen** Memberfunktion nicht aufgerufen wurde, um es an die Datenquelle eine Verbindung herstellen, wird das Recordset öffnen Sie während der eigenen [öffnen](#open) aufrufen. Wenn Sie übergeben **NULL**, `CDaoDatabase` Objekt erstellt und verbunden, die Sie mit den Datenquelleninformationen, die Sie angegeben, wenn Sie vom Recordset-Klasse abgeleitet ist `CDaoRecordset`.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder `CDaoRecordset` direkt oder ableiten eine Klasse von anwendungsspezifischen von `CDaoRecordset`. Klassen-Assistenten können Sie die Recordset-Klassen abgeleitet werden.  
  
> [!NOTE]
>  Beim Ableiten einer `CDaoRecordset` Klasse, die abgeleitete Klasse muss einen eigenen Konstruktor bereitstellen. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CDaoRecordset::CDaoRecordset`, die entsprechenden Parameter entlang an sie übergibt.  
  
 Übergeben Sie **NULL** an der Recordset-Konstruktor haben ein `CDaoDatabase` Objekt erstellt und automatisch für Sie verbunden. Dies ist eine hilfreiche Abkürzung, die nicht erforderlich ist, erstellen und verbinden Sie ein `CDaoDatabase` Objekt vor dem Erstellen des Recordsets. Wenn die `CDaoDatabase` Objekt ist nicht geöffnet ist, eine [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) Objekt auch erstellt werden, die den Standardarbeitsbereich verwendet. Weitere Informationen finden Sie unter [CDaoDatabase::CDaoDatabase](../../mfc/reference/cdaodatabase-class.md#cdaodatabase).  
  
##  <a name="close"></a>CDaoRecordset::Close  
 Schließen einer `CDaoRecordset` Objekt aus der Auflistung der geöffneten Recordsets in der verbundenen Datenbank entfernt wird.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Da **schließen** wird nicht zerstört die `CDaoRecordset` -Objekts können Sie das Objekt durch Aufrufen von wiederverwenden **öffnen** auf die gleiche Datenquelle oder eine andere Datenquelle.  
  
 Alle ausstehenden [AddNew](#addnew) oder [bearbeiten](#edit) -Anweisungen abgebrochen und alle ausstehenden Transaktionen ein Rollback. Wenn Sie ausstehende hinzufügen oder bearbeiten beibehalten möchten, rufen Sie [Update](#update) vor dem Aufruf von **schließen** für jede Recordset.  
  
 Rufen Sie **öffnen** erneut nach dem Aufruf von **schließen**. Dadurch können Sie das Recordset-Objekt wiederverwenden. Eine bessere Alternative ist, rufen Sie [Requery](#requery), sofern dies möglich.  
  
 Verwandte Informationen finden Sie im Thema "Close-Methode" in der DAO-Hilfe.  
  
##  <a name="delete"></a>CDaoRecordset::Delete  
 Rufen Sie diese Memberfunktion zum Löschen des aktuellen Datensatzes in einem geöffneten Dynaset oder vom Typ Tabelle Recordset-Objekt.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einer erfolgreichen löschen, werden das Recordset-Felddatenmember auf einen Nullwert festgelegt, und müssen Sie explizit eine Datensatzgruppe Navigation Memberfunktionen aufrufen ( [verschieben](#move), [Seek](#seek), [SetBookmark](#setbookmark)usw.) um den gelöschten Datensatz zu verschieben. Beim Löschen von Datensätzen aus einem Recordset es muss ein aktueller Datensatz im Recordset vor dem Aufruf von **löschen**, andernfalls MFC löst eine Ausnahme aus.  
  
 **Löschen Sie** entfernt den aktuellen Datensatz und macht es nicht zugegriffen werden kann. Obwohl Sie nicht bearbeiten oder den gelöschten Datensatz verwenden, bleiben sie aktuelle. Sobald Sie zu einem anderen Datensatz wechseln, können nicht jedoch Sie den gelöschten Datensatz wieder aktualisieren.  
  
> [!CAUTION]
>  Das Recordset muss aktualisierbar sein und es muss ein gültiger Datensatz im Recordset aktuelle beim Aufruf von **löschen**. Beispielsweise, wenn Sie einen Datensatz löschen, jedoch kein Bildlauf zu einem neuen Datensatz vor dem Aufruf von **löschen** erneut **löschen** löst ein [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Sie können einen Datensatz wiederherstellen, wenn Sie Transaktionen verwenden, und Sie rufen die [CDaoWorkspace::Rollback](../../mfc/reference/cdaoworkspace-class.md#rollback) Member-Funktion. Wenn die Basistabelle die primäre Tabelle ist in Cascade Beziehung löschen, Löschen des aktuellen Datensatzes kann einen oder mehrere Datensätze in einer Fremdtabelle auch löschen. Weitere Informationen finden Sie unter der Definition "Cascade löschen" in der DAO-Hilfe.  
  
 Im Gegensatz zu `AddNew` und **bearbeiten**, einen Aufruf von **löschen** folgt nicht durch einen Aufruf von **Update**.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "Delete-Methode", "Update-Methode" und "Updatable-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="dofieldexchange"></a>CDaoRecordset:: DoFieldExchange  
 Das Framework ruft diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern des Recordset-Objekts und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch.  
  
```  
virtual void DoFieldExchange(CDaoFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Enthält einen Zeiger auf ein `CDaoFieldExchange` Objekt. Das Framework wird dieses Objekt bereits eingerichtet haben, einen Kontext für den Betrieb von Exchange Feld angeben.  
  
### <a name="remarks"></a>Hinweise  
 Es bindet zudem Parameterdatenmember, falls vorhanden, die Parameterplatzhaltern in der SQL-Anweisung-Zeichenfolge für die Auswahl des Recordsets. Der Austausch von Daten, Namen von DAO-Datensatzfeldaustausch (DFX), funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes in der Datenquelle und aus dem Datensatz in der Datenquelle in das Recordset-Objekt. Wenn Sie Spalten dynamisch binden, müssen Sie nicht implementieren `DoFieldExchange`.  
  
 Die einzige Aktion, die normalerweise durchzuführenden implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse ist, erstellen Sie die Klasse mit dem Klassen-Assistenten, und geben Sie die Namen und Datentypen der Felddatenmember des. Sie können auch Code hinzufügen, auf was ClassWizard an Parameterdatenmember schreibt. Wenn alle Felder sind dynamisch gebunden werden, wird diese Funktion inaktiv sein, es sei denn, Sie Parameterdatenmember angeben.  
  
 Wenn Sie Klassen-Assistent abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` , die etwa wie folgt:  
  
 [!code-cpp[NVC_MFCDatabase&#2;](../../mfc/codesnippet/cpp/cdaorecordset-class_2.cpp)]  
  
##  <a name="edit"></a>CDaoRecordset::Edit  
 Rufen Sie diese Memberfunktion damit Änderungen am aktuellen Datensatz.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie Aufrufen der **bearbeiten** Memberfunktion, Änderungen an Feldern des aktuellen Datensatzes in den Kopierpuffer kopiert werden. Nachdem Sie die gewünschten Änderungen auf den Datensatz haben, rufen Sie **Update** zum Speichern der Änderungen. **Bearbeiten Sie** speichert die Werte der Felddatenmember des Recordsets. Wenn Sie aufrufen **bearbeiten**, ändern, rufen Sie dann **bearbeiten** erneut, die Werte des Datensatzes wiederhergestellt werden vor dem ersten Originalwerts **bearbeiten** aufrufen.  
  
> [!CAUTION]
>  Wenn Sie einen Datensatz bearbeiten, und dann Vorgänge ausführen, die zu einem anderen Datensatz erst nach Aufrufen von verschiebt **Update**, Ihre Änderungen werden ohne Warnung. Wenn Sie das Recordset oder die übergeordnete Datenbank schließen, wird außerdem der bearbeitete Datensatz ohne Warnung verworfen.  
  
 In einigen Fällen möchten möglicherweise eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Rufen Sie hierzu `SetFieldNull` mit einem Parameter des **TRUE** , markieren Sie das Feld Null; Dadurch wird auch die Spalte aktualisiert werden. Wenn Sie möchten, dass ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert hat, rufen Sie `SetFieldDirty` mit einem Parameter des **TRUE**. Dies funktioniert auch, wenn das Feld den Wert Null haben.  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie auf den Datensatz in der Datenquelle von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus geschrieben werden. Ändern den Wert eines Felds in der Regel das Feld modifizierte automatisch festgelegt, daher nur in seltenen Fällen Sie aufrufen müssen, [SetFieldDirty](#setfielddirty) selbst, aber Sie können manchmal sicherstellen möchten, dass Spalten explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert im Felddatenmember ist. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDO-NULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss explizit das Feld modifizierte festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
 Wenn das Recordset-Objekt in einer Umgebung mit mehreren Benutzern pessimistisch gesperrt ist, bleibt der Datensatz ab dem Zeitpunkt gesperrt **bearbeiten** wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz gesperrt und mit der Sperre verglichen wird, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen **bearbeiten**, **Update** fehl und MFC eine Ausnahme auslöst. Sie können ändern, das Sperrverhalten mit `SetLockingMode`.  
  
> [!NOTE]
>  Eingeschränktes Sperren wird immer auf der externen Datenbank-Formaten, z. B. ODBC und installierbare ISAM verwendet.  
  
 Der aktuelle Datensatz bleibt nach dem Aufruf von aktuellen **bearbeiten**. Aufrufen **bearbeiten**, muss ein aktueller Datensatz vorhanden sein. Wenn kein aktueller Datensatz vorhanden ist, oder wenn das Recordset nicht auf einer geöffneten Tabelle oder vom Typ Dynaset-Recordset-Objekt verweist, tritt eine Ausnahme auf. Aufrufen von **bearbeiten** bewirkt, dass ein `CDaoException` unter den folgenden Umständen ausgelöst:  
  
-   Es gibt keinen aktuellen Datensatz.  
  
-   Datenbank oder ein Recordset ist schreibgeschützt.  
  
-   Es sind keine Felder im Datensatz aktualisierbar.  
  
-   Die Datenbank oder das Recordset wurde für die ausschließliche Verwendung von einem anderen Benutzer geöffnet.  
  
-   Ein anderer Benutzer hat die Seite mit Ihrem Datensatz gesperrt.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **bearbeiten** Teil einer Transaktion aufrufen. Beachten Sie, die aufgerufen werden soll `CDaoWorkspace::BeginTrans` vor dem Aufruf von **bearbeiten** und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf `CDaoWorkspace::CommitTrans` ist kein Ersatz für den Aufruf von **Update** zum Abschließen der **bearbeiten** Vorgang. Weitere Informationen über Transaktionen finden Sie unter Klasse `CDaoWorkspace`.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "Methode bearbeiten", "Delete-Methode", "Update-Methode" und "Updatable-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="fillcache"></a>FillCache  
 Rufen Sie diese Memberfunktion, um eine angegebene Anzahl von Datensätzen aus dem Recordset zwischenzuspeichern.  
  
```  
void FillCache(
    long* pSize = NULL,  
    COleVariant* pBookmark = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pSize`  
 Gibt die Anzahl der Zeilen im Cache zu füllen. Wenn Sie diesen Parameter weglassen, wird der Wert durch die Einstellung der CacheSize-Eigenschaft des zugrunde liegenden DAO-Objekts bestimmt.  
  
 `pBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) angeben eines Lesezeichens. Auffüllen des Caches wird ab dem Datensatz, der durch dieses Lesezeichen angegeben. Wenn Sie diesen Parameter weglassen, wird der Cache ab dem Datensatz, der durch die CacheStart-Eigenschaft des zugrunde liegenden DAO-Objekts angegebenen gefüllt.  
  
### <a name="remarks"></a>Hinweise  
 Das Zwischenspeichern verbessert die Leistung einer Anwendung, die abgerufen oder an, die Daten von einem Remoteserver abruft. Ein Cache ist Platz im lokalen Speicher, der das zuletzt auf der Annahme, dass die Daten wahrscheinlich noch einmal angefordert werden während der Ausführung der Anwendung vom Server abgerufenen Daten enthält. Wenn Daten angefordert werden, überprüft das Microsoft Jet-Datenbankmodul den Cache für die Daten zunächst statt holen aus dem Server mehr Zeit in Anspruch. Zwischenspeichern von Daten auf nicht-ODBC-Datenquellen mit hat keine Auswirkung, wie die Daten nicht im Cache gespeichert ist.  
  
 Statt warten, bis des Caches mit Datensätzen gefüllt werden, wie sie abgerufen werden, können Sie explizit den Cache zu einem beliebigen Zeitpunkt ausfüllen, durch Aufrufen der `FillCache` Member-Funktion. Dies ist eine schnellere Methode zum Auffüllen des Cache, da `FillCache` ruft mehrere Datensätze gleichzeitig statt einzeln ab. Z. B. beim jeweils eine Seite mit Datensätzen angezeigt wird, kann Ihnen Ihre Anwendungsaufruf `FillCache` zum Abrufen der nächsten Seite mit Datensätzen.  
  
 Jeder ODBC-Datenbank erfolgt mit Recordset-Objekte haben einen lokalen Cache. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt aus der remote-Datenquelle, und rufen Sie dann die `SetCacheSize` und `SetCacheStart` Memberfunktionen des Recordset-Objekts. Wenn `lSize` und *lBookmark* erstellen Sie einen Bereich, der teilweise oder vollständig außerhalb des angegebenen Bereichs `SetCacheSize` und `SetCacheStart`, der Teil des Recordset-Objekts außerhalb dieses Bereichs wird ignoriert und nicht in den Cache geladen. Wenn `FillCache` fordert mehr Datensätze als bleiben in der Remotedatenquelle, nur die verbleibenden Datensätze abgerufen werden und keine Ausnahme ausgelöst.  
  
 Aus dem Cache abgerufenen Datensätze nicht gleichzeitig die Daten von anderen Benutzern vorgenommenen Änderungen wieder.  
  
 `FillCache`Ruft nur Datensätze, die noch nicht zwischengespeichert. Um eine Aktualisierung aller zwischengespeicherten Daten zu erzwingen, rufen die `SetCacheSize` Memberfunktion mit einer `lSize` Parameter gleich 0 ist, rufen `SetCacheSize` erneut mit der `lSize` Parameter gleich der Größe des Caches Sie ursprünglich angefordert hat, und rufen Sie dann `FillCache`.  
  
 Verwandte Informationen finden Sie im Thema "Zwischenspeichergröße" DAO-Hilfe.  
  
##  <a name="find"></a>CDaoRecordset::Find  
 Rufen Sie diese Memberfunktion zum Suchen einer bestimmten Zeichenfolge in einem Recordset vom Typ Dynaset oder Snapshot mit einem Vergleichsoperator.  
  
```  
virtual BOOL Find(
    long lFindType,  
    LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 *lFindType*  
 Ein Wert, der den gewünschten Suchvorgang angibt. Mögliche Werte sind:  
  
- **AFX_DAO_NEXT** die nächste Position einer übereinstimmenden Zeichenfolge suchen.  
  
- **AFX_DAO_PREV** am vorherigen Speicherort einer übereinstimmenden Zeichenfolge suchen.  
  
- **AFX_DAO_FIRST** finden Sie den ersten Speicherort einer übereinstimmenden Zeichenfolge.  
  
- **AFX_DAO_LAST** den letzten Speicherort einer übereinstimmenden Zeichenfolge suchen.  
  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (wie die **,** -Klausel in einer SQL-Anweisung ohne das Wort **,**) verwendet, um den Datensatz zu suchen. Zum Beispiel:  
  
 [!code-cpp[NVC_MFCDatabase&3;](../../mfc/codesnippet/cpp/cdaorecordset-class_3.cpp)]  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie zuerst nächsten, vorherigen oder letzten Instanz der Zeichenfolge. **Suchen Sie** ist eine virtuelle Funktion, damit Sie außer Kraft setzen und eine eigene Implementierung hinzufügen können. Die `FindFirst`, `FindLast`, `FindNext`, und `FindPrev` Memberfunktionen Aufrufen der **suchen** Member-Funktion, damit Sie verwenden können **suchen** zum Steuern des Verhaltens von alle Suchvorgänge.  
  
 Um einen Datensatz in einem Recordset vom Typ Tabelle zu suchen, rufen Sie die [Seek](#seek) Member-Funktion.  
  
> [!TIP]
>  Je kleiner die Datensatzgruppe Ihnen die effektiver **suchen** werden. Im Allgemeinen und insbesondere mit ODBC-Daten ist es besser, eine neue Abfrage erstellen, die nur die Datensätze abruft, die Sie möchten.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in der DAO-Hilfe.  
  
##  <a name="findfirst"></a>CDaoRecordset::FindFirst  
 Rufen Sie diese Memberfunktion zum ersten Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.  
  
```  
BOOL FindFirst(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (wie die **,** -Klausel in einer SQL-Anweisung ohne das Wort **,**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindFirst` Memberfunktion beginnt die Suche am Anfang des Recordset und sucht bis zum Ende des Recordset-Objekts.  
  
 Wenn alle enthalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer der Move-Vorgänge mithilfe von Datensatz zu Datensatz verschoben werden soll. Um einen Datensatz in einem Recordset vom Typ Tabelle zu suchen, rufen Sie die `Seek` -Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, den Zeiger auf den aktuellen Datensatz ist unbestimmt, und `FindFirst` gibt NULL zurück. Wenn das Recordset mehr als einen Datensatz enthält, die die Kriterien erfüllen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, müssen Sie zum Speichern der Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, werden die Änderungen ohne Warnung.  
  
 Die **suchen** Memberfunktionen zu suchen, an der Stelle und in der Richtung, in der folgenden Tabelle angegeben:  
  
|Suchvorgänge|Beginnen|Suchrichtung|  
|---------------------|-----------|----------------------|  
|`FindFirst`|Anfang des recordset|Ende des Recordsets|  
|`FindLast`|Ende des Recordsets|Anfang des recordset|  
|`FindNext`|Aktueller Datensatz|Ende des Recordsets|  
|**FindPrevious**|Aktueller Datensatz|Anfang des recordset|  
  
> [!NOTE]
>  Beim Aufruf von `FindLast`, das Microsoft Jet-Datenbankmodul füllt das Recordset vollständig vor Beginn der Suche, wenn dies nicht bereits ausgeführt wurde. Bei der ersten Suche dauert länger als die nachfolgenden suchen.  
  
 Mithilfe einer der Vorgänge suchen ist nicht identisch mit dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch des ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt einen Wert ungleich NULL, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger zurück auf einen gültigen Datensatz positionieren.  
  
-   Einen Suchvorgang kann nicht mit einem vorwärts-Bildlauf Snapshot-Recordset verwendet werden.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann ein übereinstimmender Datensatz nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken sowie große Dynasets werden Sie möglicherweise feststellen, mit der Suchvorgänge langsam ist, insbesondere bei der Arbeit mit großen Datensatzgruppen. Sie können die Leistung verbessern, mithilfe von SQL-Abfragen mit angepasst **ORDERBY** oder **, in dem** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte indizierte Datensätze abrufen.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in der DAO-Hilfe.  
  
##  <a name="findlast"></a>CDaoRecordset::FindLast  
 Rufen Sie diese Memberfunktion zum letzten Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.  
  
```  
BOOL FindLast(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (wie die **,** -Klausel in einer SQL-Anweisung ohne das Wort **,**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindLast` Memberfunktion beginnt die Suche am Ende des Recordsets und sucht rückwärts bis zum Anfang des Recordset-Objekts.  
  
 Wenn alle enthalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer der Move-Vorgänge mithilfe von Datensatz zu Datensatz verschoben werden soll. Um einen Datensatz in einem Recordset vom Typ Tabelle zu suchen, rufen Sie die `Seek` -Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, den Zeiger auf den aktuellen Datensatz ist unbestimmt, und `FindLast` gibt NULL zurück. Wenn das Recordset mehr als einen Datensatz enthält, die den Kriterien entsprechen, `FindFirst` sucht das erste Vorkommen `FindNext` sucht die nächste Instanz nach dem ersten Vorkommens und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, müssen Sie Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, werden die Änderungen ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen ist nicht identisch mit dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch des ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt einen Wert ungleich NULL, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger zurück auf einen gültigen Datensatz positionieren.  
  
-   Einen Suchvorgang kann nicht mit einem vorwärts-Bildlauf Snapshot-Recordset verwendet werden.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann ein übereinstimmender Datensatz nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken sowie große Dynasets werden Sie möglicherweise feststellen, mit der Suchvorgänge langsam ist, insbesondere bei der Arbeit mit großen Datensatzgruppen. Sie können die Leistung verbessern, mithilfe von SQL-Abfragen mit angepasst **ORDERBY** oder **, in dem** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte indizierte Datensätze abrufen.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in der DAO-Hilfe.  
  
##  <a name="findnext"></a>CDaoRecordset::FindNext  
 Rufen Sie diese Memberfunktion zum nächsten Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.  
  
```  
BOOL FindNext(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (wie die **,** -Klausel in einer SQL-Anweisung ohne das Wort **,**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindNext` Memberfunktion beginnt die Suche am aktuellen Datensatz und sucht bis zum Ende des Recordset-Objekts.  
  
 Wenn alle enthalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer der Move-Vorgänge mithilfe von Datensatz zu Datensatz verschoben werden soll. Um einen Datensatz in einem Recordset vom Typ Tabelle zu suchen, rufen Sie die `Seek` -Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, den Zeiger auf den aktuellen Datensatz ist unbestimmt, und `FindNext` gibt NULL zurück. Wenn das Recordset mehr als einen Datensatz enthält, die die Kriterien erfüllen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, müssen Sie Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, werden die Änderungen ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen ist nicht identisch mit dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch des ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt einen Wert ungleich NULL, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger zurück auf einen gültigen Datensatz positionieren.  
  
-   Einen Suchvorgang kann nicht mit einem vorwärts-Bildlauf Snapshot-Recordset verwendet werden.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann ein übereinstimmender Datensatz nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken sowie große Dynasets werden Sie möglicherweise feststellen, mit der Suchvorgänge langsam ist, insbesondere bei der Arbeit mit großen Datensatzgruppen. Sie können die Leistung verbessern, mithilfe von SQL-Abfragen mit angepasst **ORDERBY** oder **, in dem** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte indizierte Datensätze abrufen.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in der DAO-Hilfe.  
  
##  <a name="findprev"></a>CDaoRecordset::FindPrev  
 Rufen Sie diese Memberfunktion zum vorherigen Datensatz zu suchen, der mit einer angegebene Bedingung übereinstimmt.  
  
```  
BOOL FindPrev(LPCTSTR lpszFilter);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszFilter`  
 Ein Zeichenfolgenausdruck (wie die **,** -Klausel in einer SQL-Anweisung ohne das Wort **,**) verwendet, um den Datensatz zu suchen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die `FindPrev` Memberfunktion beginnt die Suche am aktuellen Datensatz und sucht rückwärts bis zum Anfang des Recordset-Objekts.  
  
 Wenn alle enthalten die Datensätze in die Suche (nicht nur diejenigen, die eine bestimmte Bedingung erfüllen) einer der Move-Vorgänge mithilfe von Datensatz zu Datensatz verschoben werden soll. Um einen Datensatz in einem Recordset vom Typ Tabelle zu suchen, rufen Sie die `Seek` -Memberfunktion.  
  
 Ein Datensatz den Kriterien nicht gefunden wird, den Zeiger auf den aktuellen Datensatz ist unbestimmt, und `FindPrev` gibt NULL zurück. Wenn das Recordset mehr als einen Datensatz enthält, die die Kriterien erfüllen, `FindFirst` sucht das erste Vorkommen, `FindNext` sucht das nächste Vorkommen und So weiter.  
  
> [!CAUTION]
>  Wenn Sie den aktuellen Datensatz bearbeiten, müssen Sie Sie speichern die Änderungen durch Aufrufen der **Update** Memberfunktion, bevor Sie zu einem anderen Datensatz wechseln. Wenn Sie zu einem anderen Datensatz verschieben, ohne zu aktualisieren, werden die Änderungen ohne Warnung.  
  
 Mithilfe einer der Vorgänge suchen ist nicht identisch mit dem Aufruf von **MoveFirst** oder `MoveNext`, die einfach macht jedoch des ersten oder nächsten Datensatzes aktuelle ohne Angabe einer Bedingung. Sie können einen Suchvorgang mit einem Verschiebevorgang folgen.  
  
 Bedenken Sie Folgendes, wenn die Operationen mit:  
  
-   Wenn **suchen** gibt einen Wert ungleich NULL, der aktuelle Datensatz ist nicht definiert. In diesem Fall müssen Sie den aktuellen Datensatzzeiger zurück auf einen gültigen Datensatz positionieren.  
  
-   Einen Suchvorgang kann nicht mit einem vorwärts-Bildlauf Snapshot-Recordset verwendet werden.  
  
-   Sie sollten das US-Datumsformat (Monat-Tag-Jahr) verwenden bei der Suche nach Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls kann ein übereinstimmender Datensatz nicht gefunden werden.  
  
-   Bei der Arbeit mit ODBC-Datenbanken sowie große Dynasets werden Sie möglicherweise feststellen, mit der Suchvorgänge langsam ist, insbesondere bei der Arbeit mit großen Datensatzgruppen. Sie können die Leistung verbessern, mithilfe von SQL-Abfragen mit angepasst **ORDERBY** oder **, in dem** -Klauseln, Parameterabfragen, oder **CDaoQuerydef** Objekte, die bestimmte indizierte Datensätze abrufen.  
  
 Weitere Informationen finden Sie im Thema "FindFirst, FindLast, FindNext, FindPrevious Methoden" in der DAO-Hilfe.  
  
##  <a name="getabsoluteposition"></a>CDaoRecordset:: GetAbsolutePosition  
 Gibt die Nummer des aktuellen Datensatzes des Recordset-Objekts zurück.  
  
```  
long GetAbsolutePosition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine ganze Zahl von 0 auf die Anzahl der Datensätze im Recordset. Entspricht der Position des aktuellen Datensatzes im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Der Wert der AbsolutePosition-Eigenschaft für das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz im Recordset. Sie können bestimmen, dass die Anzahl der gefüllten Datensätze im Recordset durch Aufrufen von [GetRecordCount](#getrecordcount). Aufrufen von `GetRecordCount` kann einige Zeit dauern, da alle Datensätze, um zu bestimmen, die Anzahl die zugegriffen werden muss.  
  
 Wenn es kein aktueller Datensatz ist, als es sind keine Datensätze im Recordset, – 1 zurückgegeben. Wenn der aktuelle Datensatz gelöscht wird, den Wert der AbsolutePosition-Eigenschaft ist nicht definiert und MFC eine Ausnahme auslöst, wenn darauf verwiesen wird. Für Recordsets vom Typ Dynaset werden neue Datensätze am Ende der Sequenz hinzugefügt.  
  
> [!NOTE]
>  Diese Eigenschaft sollte nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, um eine bestimmte Position und Sie sind die einzige Möglichkeit, den aktuellen Datensatz für alle Typen von Recordset-Objekte zu positionieren. Insbesondere ändert die Position eines bestimmten Datensatzes beim vorhergehenden Datensätze gelöscht werden. Es gibt auch keine Gewähr, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze in einem Recordset nicht garantiert ist, es sei denn, sie mit einer SQL-Anweisung mit erstellt wird ein **ORDERBY** Klausel.  
  
> [!NOTE]
>  Diese Memberfunktion ist nur für Dynaset und Snapshot-Typ gültig.  
  
 Verwandte Informationen finden Sie im Thema "AbsolutePosition-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getbookmark"></a>CDaoRecordset:: GetBookmark  
 Rufen Sie diese Memberfunktion zum Abrufen des lesezeichenwerts in einem bestimmten Datensatz.  
  
```  
COleVariant GetBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der das Lesezeichen für den aktuellen Datensatz darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, wenn es unterstützt. Rufen Sie `CanBookmark` zu bestimmen, ob ein Recordset Lesezeichen unterstützt.  
  
 Sie können das Lesezeichen für den aktuellen Datensatz durch Zuweisen des Werts des Lesezeichens, das Speichern einer `COleVariant` Objekt. Rufen Sie zum schnell zu diesem Datensatz zu einem beliebigen Zeitpunkt nach dem Wechsel zu einem anderen Datensatz zurückgeben `SetBookmark` mit einem Parameter entsprechend dem Wert der `COleVariant` Objekt.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Verwandte Informationen finden Sie im Thema "Lesezeichen Property" in der DAO-Hilfe.  
  
##  <a name="getcachesize"></a>CDaoRecordset::GetCacheSize  
 Rufen Sie diese Memberfunktion, um die Anzahl der zwischengespeicherten Datensätze zu erhalten.  
  
```  
long GetCacheSize();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, die Anzahl der Datensätze in einem Recordset vom Typ Dynaset mit Daten aus einer ODBC-Datenquelle lokal zwischengespeichert werden.  
  
### <a name="remarks"></a>Hinweise  
 Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Recordset-Objekte vom Typ Dynaset abruft. Ein Cache ist ein Bereich im lokalen Speicher, der enthält die Daten, die zuletzt vom Server abgerufen, die die Daten erneut angefordert werden, während die Anwendung ausgeführt wird. Wenn Daten angefordert werden, überprüft das Microsoft Jet-Datenbankmodul den Cache für die angeforderten Daten zunächst statt Abruf aus dem Server mehr Zeit in Anspruch. Daten, die nicht von einer ODBC-Datenquelle stammen, werden nicht im Cache gespeichert.  
  
 Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle, kann einen lokalen Cache haben.  
  
 Verwandte Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getcachestart"></a>CDaoRecordset::GetCacheStart  
 Rufen Sie diese Memberfunktion zum Abrufen des lesezeichenwerts des ersten Datensatzes im Recordset zwischengespeichert werden.  
  
```  
COleVariant GetCacheStart();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COleVariant` , der das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden angibt.  
  
### <a name="remarks"></a>Hinweise  
 Das Microsoft Jet-Datenbankmodul fordert Datensätze innerhalb des Bereichs der Cache aus dem Cache, und fordert Datensätze außerhalb des Bereichs der Cache auf dem Server.  
  
> [!NOTE]
>  Aus dem Cache abgerufenen Datensätze nicht gleichzeitig die Daten von anderen Benutzern vorgenommenen Änderungen wieder.  
  
 Verwandte Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getcurrentindex"></a>CDaoRecordset::GetCurrentIndex  
 Rufen Sie diese Memberfunktion zum Bestimmen des Indexes aktuell in Verwendung in einer indizierten Tabellentyp `CDaoRecordset` Objekt.  
  
```  
CString GetCurrentIndex();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` mit dem Namen des Indexes mit einem Recordset vom Typ Tabelle verwendet. Gibt eine leere Zeichenfolge zurück, wenn kein Index festgelegt wurde.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Index ist die Grundlage zum Sortieren von Datensätzen in einem Recordset vom Typ Tabelle und wird von der [Seek](#seek) Member-Funktion, um Datensätze zu suchen.  
  
 Ein `CDaoRecordset` Objekt kann mehr als einen Index aufweisen, jedoch können jeweils nur einen Index verwenden (obwohl eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt möglicherweise mehrere Indizes definiert).  
  
 Weitere Informationen finden Sie im Thema "Index-Objekt" und in der Definition "aktuellen Index" in der DAO-Hilfe.  
  
##  <a name="getdatecreated"></a>CDaoRecordset::GetDateCreated  
 Rufen Sie diese Memberfunktion, um das Datum und die Uhrzeit der Erstellung eine Basistabelle abzurufen.  
  
```  
COleDateTime GetDateCreated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der Erstellung die Basistabelle enthält.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen für Datum und Uhrzeit werden vom Computer abgeleitet, auf denen die Basistabelle erstellt wurde.  
  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getdatelastupdated"></a>CDaoRecordset::GetDateLastUpdated  
 Rufen Sie diese Memberfunktion zum Abrufen von Datum und Uhrzeit der letzten Aktualisierung des Schemas.  
  
```  
COleDateTime GetDateLastUpdated();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) Objekt, das das Datum und die Uhrzeit der letzten die Basistabellenstruktur (Schema Aktualisierung) enthält.  
  
### <a name="remarks"></a>Hinweise  
 Einstellungen für Datum und Uhrzeit der letzten die Basistabellenstruktur (Schema Aktualisierung) auf dem Computer stammen.  
  
 Verwandte Informationen finden Sie im Thema "DateCreated LastUpdated-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="getdefaultdbname"></a>CDaoRecordset::GetDefaultDBName  
 Rufen Sie diese Memberfunktion auf den Namen der Datenbank für dieses Recordset ermitteln.  
  
```  
virtual CString GetDefaultDBName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , enthält der Pfad und Name der Datenbank, von denen dieses Recordset abgeleitet ist.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Recordset erstellt wird, ohne einen Zeiger auf eine [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md), und dieser Pfad vom Recordset verwendet wird, um die Standarddatenbank zu öffnen. Standardmäßig gibt diese Funktion eine leere Zeichenfolge zurück. Wenn abgeleitete Klassen-Assistent ein neues Recordset aus `CDaoRecordset`, diese Funktion wird für Sie erstellt.  
  
 Das folgende Beispiel veranschaulicht die Verwendung eines umgekehrten Schrägstriche (\\\\) in der Zeichenfolge ist erforderlich, damit die Zeichenfolge richtig interpretiert werden.  
  
 [!code-cpp[NVC_MFCDatabase&4;](../../mfc/codesnippet/cpp/cdaorecordset-class_4.cpp)]  
  
##  <a name="getdefaultsql"></a>CDaoRecordset::GetDefaultSQL  
 Das Framework ruft diese Member-Funktion, um die Standard-SQL-Anweisung zu erhalten, auf der das Recordset basiert.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , enthält die Standard-SQL-Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist möglicherweise ein Tabellenname oder ein SQL **wählen** Anweisung.  
  
 Sie definieren die Standard-SQL-Anweisung indirekt durch deklarieren die Recordset-Klasse mit dem Klassen-Assistent und der Klassen-Assistent führt diese Aufgabe für Sie.  
  
 Wenn Sie eine null-SQL-Zeichenfolge zu übergeben [öffnen](#open), und klicken Sie dann diese Funktion aufgerufen wird, um zu bestimmen, den Tabellennamen oder SQL für das Recordset.  
  
##  <a name="geteditmode"></a>CDaoRecordset::GetEditMode  
 Rufen Sie diese Memberfunktion zum Bestimmen des Status der Bearbeitung einer der folgenden Werte:  
  
```  
short GetEditMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt einen Wert, der den Bearbeitungsstatus für den aktuellen Datensatz angibt.  
  
### <a name="remarks"></a>Hinweise  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|**dbEditNone**|Kein Bearbeitungsvorgang wird ausgeführt.|  
|**dbEditInProgress**|**Bearbeiten Sie** aufgerufen wurde.|  
|**dbEditAdd**|`AddNew`wurde aufgerufen.|  
  
 Informationen finden Sie unter dem Thema "EditMode-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getfieldcount"></a>CDaoRecordset::GetFieldCount  
 Rufen Sie diese Memberfunktion zum Abrufen der Anzahl von Feldern (Spalten), die im Recordset definiert.  
  
```  
short GetFieldCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Count-Eigenschaft" in der DAO-Hilfe.  
  
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
 Der nullbasierte Index des vordefinierten Felds in der Fields-Auflistung des Recordsets für die Suche nach Index.  
  
 `fieldinfo`  
 Ein Verweis auf eine [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen das Recordset abrufen. Die verfügbaren Optionen werden hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen. Rufen Sie für eine optimale Leistung nur die Ebene der Informationen, die Sie benötigen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Typ, Größe und der Attribute  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: Ordnungszahl Position ist erforderlich, ermöglichen Null Länge Reihenfolge sortieren Foreign Namen Quellfeld Quelltabelle  
  
- `AFX_DAO_ALL_INFO`Informationen über primäre und sekundäre plus: Default Value Validierungsregel Validation Text  
  
 `lpszName`  
 Der Name des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld über einen Index zu suchen. Die andere Version können Sie ein Feld nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
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
 Ein Verweis auf ein `COleVariant` -Objekt, das den Wert eines Felds gespeichert werden sollen.  
  
 `nIndex`  
 Ein nullbasierter Index des Felds in der Fields-Auflistung des Recordsets für die Suche nach Index.  
  
### <a name="return-value"></a>Rückgabewert  
 Die beiden Versionen des `GetFieldValue` , die einen Wert zurückgeben Zurückgeben einer [COleVariant](../../mfc/reference/colevariant-class.md) -Objekt, das den Wert eines Felds enthält.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Feld nach Namen oder nach der Ordnungsposition nachschlagen.  
  
> [!NOTE]
>  Es ist effizienter, rufen eine der Versionen von dieser Memberfunktion, ein `COleVariant` Objektverweis als Parameter Aufrufen eine Version, die zurückgegeben ein `COleVariant` Objekt. Die letzten Versionen dieser Funktion werden für die Abwärtskompatibilität beibehalten.  
  
 Verwendung `GetFieldValue` und [SetFieldValue](#setfieldvalue) Sie Felder zur Laufzeit und nicht statisch Binden von Spalten mit dynamisch binden der [DoFieldExchange](#dofieldexchange) Mechanismus.  
  
 `GetFieldValue`und die `DoFieldExchange` Mechanismus kann kombiniert werden, um die Leistung zu verbessern. Verwenden Sie z. B. `GetFieldValue` auf einen Wert aus, die Sie nur bei Bedarf abzurufen, und weisen Sie diesen Aufruf an eine Schaltfläche "Weitere Informationen" in der Benutzeroberfläche.  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getindexcount"></a>CDaoRecordset::GetIndexCount  
 Rufen Sie diese Memberfunktion zum Ermitteln der Anzahl der Indizes, die für das Recordset vom Typ Tabelle verfügbar.  
  
```  
short GetIndexCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Indizes in das Recordset vom Typ Tabelle.  
  
### <a name="remarks"></a>Hinweise  
 `GetIndexCount`eignet sich für alle Indizes in das Recordset durchlaufen. Verwenden Sie zu diesem Zweck `GetIndexCount` in Verbindung mit [GetIndexInfo](#getindexinfo). Wenn Sie diese Memberfunktion auf Dynaset oder Snapshot-Typ aufrufen, löst MFC eine Ausnahme aus.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getindexinfo"></a>CDaoRecordset::GetIndexInfo  
 Rufen Sie diese Memberfunktion auf verschiedene Arten von Informationen zu einem Index definiert in der Basistabelle, die zugrunde liegenden Recordset zu erhalten.  
  
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
 Der nullbasierte Index in der Tabelle Indizes Auflistung, für die Suche nach der numerischen Position.  
  
 `indexinfo`  
 Ein Verweis auf eine [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur.  
  
 `dwInfoOptions`  
 Optionen, die angeben, welche Informationen über den Index abgerufen. Die verfügbaren Optionen werden hier aufgeführt, zusammen mit der sie die Funktion zurückgeben verursachen. Rufen Sie für eine optimale Leistung nur die Ebene der Informationen, die Sie benötigen:  
  
- `AFX_DAO_PRIMARY_INFO`(Standard) Name, Feldinformationen, Felder  
  
- `AFX_DAO_SECONDARY_INFO`Primäre Informationen plus: primäre, eindeutiger, gruppierter, IgnoreNulls, erforderlich, Fremdschlüssel  
  
- `AFX_DAO_ALL_INFO`Informationen über primäre und sekundäre plus: Distinct Count  
  
 `lpszName`  
 Ein Zeiger auf den Namen des Index-Objekts, für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie nach einem Index anhand seiner Position in der Auflistung suchen. Die andere Version können Sie einen Index nach Namen suchen.  
  
 Eine Beschreibung der zurückgegebenen Informationen finden Sie in der [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) Struktur. Diese Struktur hat Member, die in der Beschreibung der obigen Angaben entsprechen `dwInfoOptions`. Wenn Sie Daten auf einer Ebene anfordern, erhalten Sie Informationen für alle vorherigen Ebenen sowie.  
  
 Verwandte Informationen finden Sie unter dem Thema "Attribute-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getlastmodifiedbookmark"></a>CDaoRecordset::GetLastModifiedBookmark  
 Rufen Sie diese Memberfunktion, um das Lesezeichen des Datensatzes die zuletzt hinzugefügte oder aktualisierte abzurufen.  
  
```  
COleVariant GetLastModifiedBookmark();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `COleVariant` hinzugefügten oder geänderten Datensatz mit einem Lesezeichen, das das zuletzt angibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen, wenn es unterstützt. Rufen Sie [GetBookmark](#getbookmark) bestimmt, ob das Recordset Lesezeichen unterstützt. Wenn das Recordset keine Lesezeichen unterstützt eine `CDaoException` ausgelöst.  
  
 Wenn Sie einen Datensatz hinzufügen, erscheint am Ende des Recordset-Objekts, und ist nicht zum aktuellen Datensatz. Um den neuen Datensatz aktualisieren, rufen Sie `GetLastModifiedBookmark` und rufen dann `SetBookmark` auf den neu hinzugefügten Datensatz zurückgegeben.  
  
 Verwandte Informationen finden Sie unter dem Thema "LastModified-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getlockingmode"></a>CDaoRecordset::GetLockingMode  
 Rufen Sie diese Memberfunktion, um die Sperrung an für das Recordset zu bestimmen.  
  
```  
BOOL GetLockingMode();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, ist die Art der Sperrung pessimistische, andernfalls 0 für die vollständige Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Wenn pessimistische Sperren ist die Datenseite mit den von Ihnen bearbeiteten Datensatz ist gesperrt, sobald Sie rufen die [bearbeiten](#edit) Member-Funktion. Die Seite ist nicht gesperrt, beim Aufrufen der [Update](#update) oder [schließen](#close) Memberfunktion oder die Vorgänge verschieben oder suchen.  
  
 Wenn optimistischen Sperren aktiviert ist, wird die Datenseite mit dem Datensatz gesperrt, nur verwendet werden, während der Aktualisierung des Datensatzes mit der **Update** Member-Funktion.  
  
 Bei der Arbeit mit ODBC-Datenquellen wird das Sperrverhalten immer optimistische.  
  
 Weitere Informationen finden Sie unter den Themen "Sperren Property" und "Sperren Verhalten in Multiuser Applications" in der DAO-Hilfe.  
  
##  <a name="getname"></a>CDaoRecordset::GetName  
 Rufen Sie diese Memberfunktion zum Abrufen des Namens des Recordset-Objekts.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` mit dem Namen des Recordset-Objekts.  
  
### <a name="remarks"></a>Hinweise  
 Der Name des Recordset-Objekts muss mit einem Buchstaben beginnen und darf maximal 40 Zeichen enthalten. Es kann Zahlen enthalten und Unterstrich-Zeichen jedoch keine Interpunktionszeichen oder Leerzeichen enthalten.  
  
 Verwandte Informationen finden Sie im Thema "Name-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getparamvalue"></a>CDaoRecordset::GetParamValue  
 Rufen Sie diese Memberfunktion rufen Sie den aktuellen Wert des angegebenen Parameters in der zugrunde liegenden DAOParameter-Objekt gespeichert.  
  
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
  
 Verwandte Informationen finden Sie im Thema "Parameter-Objekt" in der DAO-Hilfe.  
  
##  <a name="getpercentposition"></a>CDaoRecordset:: GetPercentPosition  
 Beim Arbeiten mit einem Dynaset oder vom Typ Snapshot-Recordset, wenn Sie aufrufen `GetPercentPosition` vor das Recordset vollständig aufgefüllt, ist der Umfang der Bewegung relativ zur Anzahl der Datensätze zugegriffen wird, wie durch Aufrufen von [GetRecordCount](#getrecordcount).  
  
```  
float GetPercentPosition();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Zahl zwischen 0 und 100, die die ungefähre Position des aktuellen Datensatzes im Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset angibt.  
  
### <a name="remarks"></a>Hinweise  
 Sie können mit dem letzten Datensatz verschieben durch Aufrufen von [MoveLast](#movelast) , vollständige die Auffüllung des Recordsets, aber dies dauert sehr viel Zeit.  
  
 Rufen Sie `GetPercentPosition` auf alle drei Typen von Recordset-Objekte, einschließlich der Tabellen ohne Indizes. Sie können nicht aufgerufen `GetPercentPosition` Bildlauf vorwärts-Snapshots oder ein Recordset in einer Pass-Through-Abfrage für eine externe Datenbank geöffnet. Es ist kein aktueller Datensatz oder aktuelle He-Datensatz wurde gelöscht, eine `CDaoException` ausgelöst.  
  
 Verwandte Informationen finden Sie unter dem Thema "PercentPosition-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getrecordcount"></a>CDaoRecordset::GetRecordCount  
 Rufen Sie diese Memberfunktion, um herauszufinden, wie viele Datensätze in einem Recordset zugegriffen wurde.  
  
```  
long GetRecordCount();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Gibt die Anzahl der Datensätze in einem Recordset-Objekt zugegriffen.  
  
### <a name="remarks"></a>Hinweise  
 `GetRecordCount`bedeutet nicht, wie viele Datensätze in einem Dynaset oder Snapshot-Typ enthalten sind, bis alle Datensätze zugegriffen wurde. Dieser Member-Funktionsaufruf dauert sehr viel Zeit in Anspruch.  
  
 Nachdem der letzte Datensatz zugegriffen wurde, gibt der Rückgabewert die Gesamtzahl der nicht gelöschten Datensätze im Recordset. Um den letzten Datensatz zugegriffen werden zu erzwingen, rufen Sie die `MoveLast` oder `FindLast` -Memberfunktion des Recordsets. Gibt die Anzahl SQL können auch um die ungefähre Anzahl der Datensätze zu ermitteln, die Ihre Abfrage zurückgeben wird.  
  
 Wie Ihre Anwendung Datensätze in einem Recordset vom Typ Dynaset, den Rückgabewert der löscht `GetRecordCount` verringert. Von anderen Benutzern gelöschten Datensätze werden jedoch nicht wiedergegeben, indem `GetRecordCount` bis zu einem gelöschten Datensatz zum aktuelle Datensatz positioniert ist. Wenn Sie eine Transaktion, die die Anzahl der Datensätze wirkt sich auf Ausführen und anschließend ein der Transaktion Rollback `GetRecordCount` spiegeln nicht die tatsächliche Anzahl verbleibender Datensätze.  
  
 Der Wert des `GetRecordCount` aus einem Recordset vom Typ Snapshot wird durch Änderungen an den zugrunde liegenden Tabellen nicht beeinflusst.  
  
 Der Wert des `GetRecordCount` aus einem Tabellentyp Recordset gibt die ungefähre Anzahl der Datensätze in der Tabelle und unmittelbar beeinflusst, wie die Datensätze hinzugefügt und gelöscht werden.  
  
 Ein Recordset mit keine Datensätze gibt den Wert 0 zurück. Beim Arbeiten mit angefügten Tabellen oder ODBC-Datenbanken, `GetRecordCount` immer – 1 zurückgegeben. Aufrufen der **Requery** Memberfunktion für ein Recordset setzt den Wert der `GetRecordCount` nur als wäre die Abfrage erneut ausgeführt.  
  
 Verwandte Informationen finden Sie im Thema "RecordCount Property" in der DAO-Hilfe.  
  
##  <a name="getsql"></a>CDaoRecordset::GetSQL  
 Rufen Sie diese Memberfunktion, um die SQL-Anweisung zu erhalten, die verwendet wurde, um die Datensätze des Recordsets auswählen, wenn sie geöffnet wurde.  
  
```  
CString GetSQL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , der die SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist in der Regel wird eine SQL **wählen** Anweisung.  
  
 Die zurückgegebene Zeichenfolge `GetSQL` unterscheidet sich in der Regel eine beliebige Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die `lpszSQL` Parameter, um die [öffnen](#open) Member-Funktion. Dies ist, da das Recordset basierte auf den an Sie übergeben eine vollständige SQL­Anweisung erstellt **öffnen**, was Sie mit dem Klassen-Assistenten angegeben und was Sie in angegeben haben möglicherweise die [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) Datenmember.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf von **öffnen**.  
  
 Weitere Informationen finden Sie unter dem Thema "SQL-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="gettype"></a>CDaoRecordset::GetType  
 Rufen Sie diese Memberfunktion nach dem Öffnen des Recordsets, um den Typ des Recordset-Objekts zu ermitteln.  
  
```  
short GetType();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der folgenden Werte, die den Typ eines Recordset-Objekts angibt:  
  
- **Übergeben** Tabelle  
  
- **DbOpenDynaset** vom Typ Dynaset  
  
- **DbOpenSnapshot** Recordsets vom Typ Snapshot  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "Typeigenschaft" DAO-Hilfe.  
  
##  <a name="getvalidationrule"></a>CDaoRecordset::GetValidationRule  
 Rufen Sie diese Memberfunktion zum Bestimmen der Regel verwendet, um Daten zu überprüfen.  
  
```  
CString GetValidationRule();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt mit einem Wert, der die Daten in einem Datensatz überprüft, wie es geändert oder einer Tabelle hinzugefügt.  
  
### <a name="remarks"></a>Hinweise  
 Diese Regel ist textbasiert und angewendet wird jedes Mal, wenn die zugrunde liegende Tabelle geändert wird. Wenn die Daten nicht zulässig ist, löst MFC eine Ausnahme aus. Die zurückgegebene Fehlermeldung ist der Text der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt, wenn angegeben, oder der Text des Ausdrucks von der ValidationRule-Eigenschaft des zugrunde liegenden Field-Objekts angegeben. Rufen Sie [GetValidationText](#getvalidationtext) um den Text der Fehlermeldung abzurufen.  
  
 Z. B. ein Feld in einem Datensatz, der den Tag des Monats erfordert möglicherweise eine Validierungsregel wie z. B. "Tag zwischen 1 und 31."  
  
 Weitere Informationen finden Sie unter dem Thema "ValidationRule-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="getvalidationtext"></a>CDaoRecordset::GetValidationText  
 Rufen Sie diese Memberfunktion zum Abrufen des Texts der ValidationText-Eigenschaft des zugrunde liegenden Field-Objekt.  
  
```  
CString GetValidationText();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` Objekt mit dem Text der Nachricht, die angezeigt wird, wenn der Wert eines Felds die Validierungsregel des zugrunde liegenden Field-Objekts nicht erfüllt.  
  
### <a name="remarks"></a>Hinweise  
 Verwandte Informationen finden Sie im Thema "ValidationText-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="isbof"></a>CDaoRecordset::IsBOF  
 Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf von Datensatz zu Datensatz zur Feststellung, ob Sie vor dem ersten Datensatz des Recordsets überschritten haben.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält, oder wenn Sie vor dem ersten Datensatz rückwärts gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können auch aufrufen, `IsBOF` zusammen mit `IsEOF` bestimmen, ob das Recordset Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von **öffnen**, wenn das Recordset keine Datensätze enthält `IsBOF` gibt einen Wert ungleich NULL zurück. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz zum aktuellen Datensatz und `IsBOF` gibt 0 zurück.  
  
 Wenn der erste Datensatz zum aktuellen Datensatz ist, und Sie rufen `MovePrev`, `IsBOF` anschließend einen Wert ungleich NULL zurück. Wenn `IsBOF` gibt einen Wert ungleich NULL, und Sie rufen `MovePrev`, wird eine Ausnahme ausgelöst. Wenn `IsBOF` gibt einen Wert ungleich NULL, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert eine Ausnahme ausgelöst wird.  
  
 Auswirkung auf bestimmte Methoden `IsBOF` und `IsEOF` Einstellungen:  
  
-   Aufrufen von **öffnen** intern wird der erste Datensatz im Recordset den aktuellen Datensatz durch Aufrufen von **MoveFirst**. Daher entspricht der Aufruf **öffnen** auf einen leeren Satz von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe folgende Tabelle für das Verhalten einer fehlgeschlagenen **MoveFirst** oder `MoveLast` aufrufen.)  
  
-   Alle Move-Vorgänge, die einen Datensatz finden dazu führen, dass beide `IsBOF` und `IsEOF` 0 zurück.  
  
-   Ein `AddNew` Aufruf, gefolgt von einer **Update** -Aufruf, der einen neuen Eintrag erfolgreich eingefügt wird `IsBOF` zurückzugebenden 0, jedoch nur, wenn `IsEOF` bereits einen Wert ungleich NULL ist. Der Status des `IsEOF` immer unverändert. Gemäß der Definition durch das Microsoft Jet-Datenbankmodul ist der aktuelle Datensatzzeiger, der eine leere Datensatzgruppe am Ende einer Datei, damit alle neuer Datensatz nach dem aktuellen Datensatz eingefügt wird.  
  
-   Alle **löschen** aufrufen, auch wenn den letzte Datensatz aus einem Recordset entfernt ändert nicht den Wert der `IsBOF` oder `IsEOF`.  
  
 Die folgende Tabelle zeigt die Move-Vorgänge zulässig sind, mit verschiedenen Kombinationen der `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> Verschieben< 0></ 0>|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`ungleich null =<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|  
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|  
|Beide 0|Allowed|Allowed|Allowed|Allowed|  
  
 Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang erfolgreich einen Datensatz findet. Es bedeutet nur, dass ein Versuch, den angegebenen Vorgang durchzuführen zulässig ist und keine Ausnahme erzeugt. Der Wert der `IsBOF` und `IsEOF` Memberfunktionen können aufgrund der versuchten verschieben ändern.  
  
 Die Auswirkung der Move-Vorgänge, die keinen Datensatz auf den Wert der finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle gezeigt wird.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ungleich|Ungleich|  
|**Verschieben Sie** 0|Keine Änderung|Keine Änderung|  
|`MovePrev`, **Move**< 0></ 0>|Ungleich|Keine Änderung|  
|`MoveNext`, **Move** > 0|Keine Änderung|Ungleich|  
  
 Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="isdeleted"></a>CDaoRecordset::IsDeleted  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der aktuelle Datensatz gelöscht wurde.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen zu einem Datensatz Bildlauf und `IsDeleted` gibt **TRUE** (ungleich null), Sie müssen Blättern Sie zu einem anderen Datensatz Weitere Recordset-Operationen durchführen zu können.  
  
> [!NOTE]
>  Sie müssen nicht den Status "gelöscht" für die Datensätze in einem Recordset vom Typ Tabelle oder Snapshot zu überprüfen. Da Datensätze aus einer Momentaufnahme gelöscht werden können, besteht keine Notwendigkeit zum Aufrufen `IsDeleted`. Recordsets vom Typ Tabelle werden gelöschte Datensätze tatsächlich aus dem Recordset entfernt. Sobald ein Datensatz, Sie einem anderen Benutzer oder einer anderen Datensatzgruppe gelöscht wurde können nicht Sie zu diesem Datensatz zurück blättern. Daher besteht keine Notwendigkeit zum Aufrufen `IsDeleted`.  
  
 Wenn Sie einen Datensatz aus einem Dynaset löschen, wird aus dem Recordset entfernt, und Sie können nicht mit dem Datensatz zurück blättern. Wenn ein Datensatz in einem Dynaset wird jedoch gelöscht, von einem anderen Benutzer oder in einem anderen Recordset basierend auf der gleichen Tabelle `IsDeleted` zurück **TRUE** Wenn Sie später einen Bildlauf zu diesem Datensatz.  
  
 Weitere Informationen finden Sie unter den Themen "Delete-Methode", "LastModified-Eigenschaft" und "EditMode-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="iseof"></a>CDaoRecordset::IsEOF  
 Rufen Sie diese Memberfunktion, wie Sie einen Bildlauf von Datensatz zu Datensatz zur Feststellung, ob Sie den letzten Datensatz des Recordsets überschritten haben.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält, oder wenn Sie hinter dem letzten Datensatz gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Sie können auch aufrufen `IsEOF` bestimmen, ob das Recordset Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von **öffnen**, wenn das Recordset keine Datensätze enthält `IsEOF` gibt einen Wert ungleich NULL zurück. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz zum aktuellen Datensatz und `IsEOF` gibt 0 zurück.  
  
 Wenn der letzte Datensatz zum aktuellen Datensatz, beim Aufruf von ist `MoveNext`, `IsEOF` anschließend einen Wert ungleich NULL zurück. Wenn `IsEOF` gibt einen Wert ungleich NULL, und Sie rufen `MoveNext`, wird eine Ausnahme ausgelöst. Wenn `IsEOF` gibt einen Wert ungleich NULL, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert eine Ausnahme ausgelöst wird.  
  
 Auswirkung auf bestimmte Methoden `IsBOF` und `IsEOF` Einstellungen:  
  
-   Aufrufen von **öffnen** intern wird der erste Datensatz im Recordset den aktuellen Datensatz durch Aufrufen von **MoveFirst**. Daher entspricht der Aufruf **öffnen** auf einen leeren Satz von Datensätzen Ursachen `IsBOF` und `IsEOF` ungleich NULL zurückgegeben. (Siehe folgende Tabelle für das Verhalten einer fehlgeschlagenen **MoveFirst** aufrufen.)  
  
-   Alle Move-Vorgänge, die einen Datensatz finden dazu führen, dass beide `IsBOF` und `IsEOF` 0 zurück.  
  
-   Ein `AddNew` Aufruf, gefolgt von einer **Update** -Aufruf, der einen neuen Eintrag erfolgreich eingefügt wird `IsBOF` zurückzugebenden 0, jedoch nur, wenn `IsEOF` bereits einen Wert ungleich NULL ist. Der Status des `IsEOF` immer unverändert. Gemäß der Definition durch das Microsoft Jet-Datenbankmodul ist der aktuelle Datensatzzeiger, der eine leere Datensatzgruppe am Ende einer Datei, damit alle neuer Datensatz nach dem aktuellen Datensatz eingefügt wird.  
  
-   Alle **löschen** aufrufen, auch wenn den letzte Datensatz aus einem Recordset entfernt ändert nicht den Wert der `IsBOF` oder `IsEOF`.  
  
 Die folgende Tabelle zeigt die Move-Vorgänge zulässig sind, mit verschiedenen Kombinationen der `IsBOF` /  `IsEOF`.  
  
||MoveFirst, MoveLast|MovePrev,<br /><br /> Verschieben< 0></ 0>|Verschieben von 0|MoveNext,<br /><br /> Verschieben Sie > 0|  
|------|-------------------------|-----------------------------|------------|-----------------------------|  
|`IsBOF`ungleich null =<br /><br /> `IsEOF`=0|Allowed|Ausnahme|Ausnahme|Allowed|  
|`IsBOF`=0,<br /><br /> `IsEOF`ungleich null =|Allowed|Allowed|Ausnahme|Ausnahme|  
|Beide ungleich null|Ausnahme|Ausnahme|Ausnahme|Ausnahme|  
|Beide 0|Allowed|Allowed|Allowed|Allowed|  
  
 Ermöglicht einen Verschiebevorgang bedeutet nicht, dass der Vorgang erfolgreich einen Datensatz findet. Es bedeutet nur, dass ein Versuch, den angegebenen Vorgang durchzuführen zulässig ist und keine Ausnahme erzeugt. Der Wert der `IsBOF` und `IsEOF` Memberfunktionen können aufgrund der versuchten verschieben ändern.  
  
 Die Auswirkung der Move-Vorgänge, die keinen Datensatz auf den Wert der finden `IsBOF` und `IsEOF` Einstellungen in der folgenden Tabelle gezeigt wird.  
  
||IsBOF|IsEOF|  
|------|-----------|-----------|  
|**MoveFirst**,`MoveLast`|Ungleich|Ungleich|  
|**Verschieben Sie** 0|Keine Änderung|Keine Änderung|  
|`MovePrev`, **Move**< 0></ 0>|Ungleich|Keine Änderung|  
|`MoveNext`, **Move** > 0|Keine Änderung|Ungleich|  
  
 Weitere Informationen finden Sie im Thema "BOF, EOF-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="isfielddirty"></a>CDaoRecordset::IsFieldDirty  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember ein Dynaset als "geändert" gekennzeichnet ist (geändert).  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Feld Datenelement als fehlerhaft gekennzeichnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten in alle Felddatenmember transferiert auf den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der **Update** -Memberfunktion des `CDaoRecordset` (nach einem Aufruf von **bearbeiten** oder `AddNew`). Mit diesem Wissen Sie können weitere Schritte vornehmen, z. B. Aufheben der Kennzeichnung der Felddatenmember, um die Spalte zu markieren, damit sie nicht an die Datenquelle geschrieben wird.  
  
 `IsFieldDirty`wird über implementiert `DoFieldExchange`.  
  
##  <a name="isfieldnull"></a>CDaoRecordset::IsFieldNull  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember eines Recordset-Objekts als Null gekennzeichnet ist.  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Feld Datenelement als Null gekennzeichnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 (In der datenbankterminologie von-Null-man "kein Wert" und ist nicht identisch mit **NULL** in C++.) Wenn Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte des aktuellen Datensatzes interpretiert kein Wert vorhanden ist.  
  
> [!NOTE]
>  In bestimmten Situationen mit `IsFieldNull` kann ineffizient sein, wie im folgenden Codebeispiel wird veranschaulicht:  
  
 [!code-cpp[NVC_MFCDatabase&5;](../../mfc/codesnippet/cpp/cdaorecordset-class_5.cpp)]  
  
> [!NOTE]
>  Wenn Sie dynamische Bindung aufzuzeichnen, verwenden, ohne eine Ableitung von `CDaoRecordset`, verwenden Sie **VT_NULL** wie im Beispiel gezeigt.  
  
##  <a name="isfieldnullable"></a>CDaoRecordset::IsFieldNullable  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das angegebene Feld Datenelement "zulässig" ist (können auf einen Null-Wert festgelegt werden C++ **NULL** ist nicht Null, womit, in der datenbankterminologie identisch "having kein Wert").  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL ist, der angegebenen Felddatenmember Null festgelegt werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, ein Feld auf Null, die beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und **aktualisieren** löst eine Ausnahme aus. Die Ausnahme tritt auf, wenn Sie aufrufen **Update**, nicht beim Aufruf von `SetFieldNull`.  
  
##  <a name="isopen"></a>CDaoRecordset::IsOpen  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das Recordset geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich Null des Recordset-Objekts **öffnen** oder **Requery** Memberfunktion zuvor aufgerufen wurde und das Recordset nicht geschlossen wurde, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
  
##  <a name="m_bcheckcachefordirtyfields"></a>CDaoRecordset:: M_bcheckcachefordirtyfields  
 Enthält ein Flag, das angibt, ob zwischengespeicherte Felder automatisch als markiert sind modifiziert (geändert) und Null.  
  
### <a name="remarks"></a>Hinweise  
 Das Flag wird standardmäßig auf **TRUE**. Die Einstellung in diesem Datenelement steuert den gesamten Doppelpufferung Mechanismus. Wenn Sie das Flag auf **TRUE**, Sie können das Zwischenspeichern auf Grundlage von Feld DFX-Mechanismus deaktivieren. Wenn Sie das Flag auf **FALSE**, müssen Sie aufrufen, `SetFieldDirty` und `SetFieldNull` selbst.  
  
 Legen Sie dieses Datenelement vor dem Aufruf von **öffnen**. Dieser Mechanismus ist in erster Linie für die erleichterte Bedienung. Leistung ist möglicherweise langsamer aufgrund der Doppelpufferung Felder geändert werden.  
  
##  <a name="m_nfields"></a>CDaoRecordset::m_nFields  
 Enthält die Anzahl der Felddatenmember der Recordset-Klasse und die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor für die Recordset-Klasse initialisieren muss `m_nFields` mit der korrekten Anzahl von statisch gebundenen Feldern. Klassen-Assistent schreibt diese Initialisierung für Sie, wenn Sie es verwenden, um die Recordset-Klasse deklarieren. Sie können Sie auch manuell schreiben.  
  
 Das Framework verwendet diese Nummer zum Verwalten der Interaktion zwischen den Felddatenmembern und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle.  
  
> [!NOTE]
>  Diese Zahl muss der Anzahl der Ausgabespalten, die in registriert entsprechen `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter **CDaoFieldExchange::outputColumn**.  
  
 Sie können Spalten dynamisch mit binden `CDaoRecordset::GetFieldValue` und `CDaoRecordset::SetFieldValue`. Wenn Sie dies tun, müssen Sie nicht erhöht die Anzahl die in `m_nFields` entsprechend die Anzahl der DFX-Funktion aufruft, der `DoFieldExchange` Member-Funktion.  
  
##  <a name="m_nparams"></a>CDaoRecordset::m_nParams  
 Enthält die Anzahl der Parameterdatenmember in der Recordset-Klasse – die Anzahl der Parameter zu übergeben, mit die Abfrage des Recordsets.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Recordset-Klasse Parameterdatenmember verfügt, muss der Konstruktor für die Klasse initialisieren `m_nParams` mit der korrekten Anzahl. Der Wert des `m_nParams` hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen – was Sie manuell durchführen müssen – Sie müssen eine Initialisierung auch manuell hinzufügen, im Konstruktor Klasse die Anzahl von Parametern an (die muss mindestens so groß wie die Anzahl der '' Platzhalter in Ihre **M_strFilter** oder `m_strSort` Zeichenfolge).  
  
 Das Framework verwendet diese Zahl, wenn sie die Abfrage des Recordsets parametrisiert.  
  
> [!NOTE]
>  Diese Zahl muss der Anzahl der "Params" in registriert entsprechen `DoFieldExchange` nach einem Aufruf von `SetFieldType` mit dem Parameter **CFieldExchange::param**.  
  
 Verwandte Informationen finden Sie im Thema "Parameter-Objekt" in der DAO-Hilfe.  
  
##  <a name="m_pdaorecordset"></a>CDaoRecordset::m_pDAORecordset  
 Enthält einen Zeiger auf die OLE-Schnittstelle für den DAO-Recordset-Objekt zugrunde liegenden der `CDaoRecordset` Objekt.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie diesen Zeiger, wenn Sie auf die DAO-Schnittstelle direkt zugreifen müssen.  
  
 Weitere Informationen finden Sie im Thema "Recordset-Objekt" in der DAO-Hilfe.  
  
##  <a name="m_pdatabase"></a>CDaoRecordset::m_pDatabase  
 Enthält einen Zeiger auf die `CDaoDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable wird auf zwei Arten festgelegt werden. In der Regel, übergeben Sie einen Zeiger auf ein bereits geöffnetes `CDaoDatabase` -Objekts bei der Konstruktion des Recordsetobjekts. Wenn Sie übergeben **NULL** stattdessen **CDaoRecordset** erstellt ein `CDaoDatabase` -Objekt für Sie und öffnet sie. In beiden Fällen `CDaoRecordset` den Zeiger in dieser Variablen gespeichert.  
  
 Normalerweise wird nicht direkt müssen mit den gespeicherten Zeiger **M_pDatabase**. Wenn Sie Ihre eigenen Erweiterungen schreiben `CDaoRecordset`, jedoch möglicherweise den Zeiger zu verwenden. Beispielsweise benötigen Sie möglicherweise den Mauszeiger Wenn Sie lösen eigene `CDaoException`(s).  
  
 Verwandte Informationen finden Sie im Thema "Datenbankobjekt" DAO-Hilfe.  
  
##  <a name="m_strfilter"></a>CDaoRecordset::m_strFilter  
 Enthält eine Zeichenfolge, die zum Erstellen der **,** -Klausel einer SQL­Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Sie schließt nicht das reservierte Wort **, in denen** das Recordset filtern. Die Verwendung dieses Datenelements gilt nicht für Recordsets vom Typ Tabelle zur Verfügung. Die Verwendung von **M_strFilter** hat keine Auswirkung, wenn Sie öffnen ein Recordset mit einer `CDaoQueryDef` Zeiger.  
  
 Verwenden Sie das US-Datumsformat (Monat-Tag-Jahr) beim Filtern von Feldern mit Datumsangaben, selbst wenn Sie nicht die US-Version des Microsoft Jet-Datenbankmoduls; verwenden Andernfalls können die Daten nicht gefiltert werden, wie erwartet.  
  
 Verwandte Informationen finden Sie im Thema "Filter-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="m_strsort"></a>CDaoRecordset::m_strSort  
 Enthält eine Zeichenfolge mit der **ORDERBY** -Klausel einer SQL­Anweisung ohne die reservierten Wörter **ORDERBY**.  
  
### <a name="remarks"></a>Hinweise  
 Sie können Recordset-Objekte vom Typ Dynaset und Snapshot sortieren.  
  
 Recordset-Objekte vom Typ Tabelle können nicht sortiert werden. Um die Sortierreihenfolge eines Recordsets vom Typ Tabelle zu ermitteln, rufen [SetCurrentIndex](#setcurrentindex).  
  
 Die Verwendung von `m_strSort` hat keine Auswirkung, wenn Sie öffnen ein Recordset mit einer `CDaoQueryDef` Zeiger.  
  
 Verwandte Informationen finden Sie im Thema "Sort-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="move"></a>CDaoRecordset::Move  
 Rufen Sie diese Memberfunktion zum Positionieren Sie des Recordsets `lRows` Datensätze aus dem aktuellen Datensatz.  
  
```  
virtual void Move(long lRows);
```  
  
### <a name="parameters"></a>Parameter  
 `lRows`  
 Die Anzahl von Datensätzen vorwärts oder rückwärts verschoben. Positive Werte vorwärts, am Ende des Recordset-Objekts. Negative Werte rückwärts, an den Anfang.  
  
### <a name="remarks"></a>Hinweise  
 Sie können vorwärts oder rückwärts verschieben. `Move( 1 )`entspricht dem `MoveNext`, und `Move( -1 )` entspricht `MovePrev`.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. In der Regel rufen Sie beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmen, ob das Recordset Datensätze verfügt. Nach dem Aufruf von **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie nach dem Anfang oder Ende des Recordsets gescrollt haben ( `IsBOF` oder `IsEOF` gibt einen Wert ungleich null), einen Aufruf von **verschieben** löst eine `CDaoException`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Beim Aufruf von **verschieben** auf einen vorwärtsgerichteten Bildlauf Snapshot der `lRows` -Parameter muss eine positive ganze Zahl sein, und Lesezeichen sind nicht zulässig, sodass Sie nur vorwärts bewegen können.  
  
 Damit wird der ersten, letzten, nächsten oder vorherigen Zeichnen in einem Recordset den aktuellen Datensatz, Aufruf der **MoveFirst**, `MoveLast`, `MoveNext`, oder `MovePrev` Member-Funktion.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious-Methoden" in der DAO-Hilfe.  
  
##  <a name="movefirst"></a>CDaoRecordset::MoveFirst  
 Rufen Sie diese Memberfunktion zum ersten Datensatz im Recordset (sofern vorhanden) stellen den aktuellen Datensatz.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen keinen Aufrufen **MoveFirst** sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt ist der erste Datensatz (sofern vorhanden) automatisch zum aktuellen Datensatz.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. In der Regel rufen Sie beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmen, ob das Recordset Datensätze verfügt. Nach dem Aufruf von **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben werden, ohne eine Bedingung anzuwenden. Verwenden Sie die Operationen zum Suchen von Datensätzen in einem Dynaset oder vom Typ Snapshot-Recordset-Objekts, die eine bestimmte Bedingung erfüllen. Rufen Sie zum Suchen eines Datensatzes in einem Recordset-Objekt vom Typ Tabelle `Seek`.  
  
 Wenn das Recordset zu einem Recordset vom Typ Tabelle bezieht, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie den aktuellen Index nicht festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Wenn Sie aufrufen `MoveLast` auf einem Recordset-Objekt, das auf einer SQL-Abfrage oder Querydef basiert, wird die Abfrage bis zum Abschluss erzwungen, und das Recordset-Objekt wird vollständig aufgefüllt.  
  
 Kann nicht aufgerufen werden die **MoveFirst** oder `MovePrev` Memberfunktion mit einem Bildlauf vorwärts-Snapshot.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious-Methoden" in der DAO-Hilfe.  
  
##  <a name="movelast"></a>CDaoRecordset::MoveLast  
 Rufen Sie diese Memberfunktion zum letzten Datensatz (sofern vorhanden) stellen im Recordset der aktuelle Datensatz.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. In der Regel rufen Sie beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmen, ob das Recordset Datensätze verfügt. Nach dem Aufruf von **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben werden, ohne eine Bedingung anzuwenden. Verwenden Sie die Operationen zum Suchen von Datensätzen in einem Dynaset oder vom Typ Snapshot-Recordset-Objekts, die eine bestimmte Bedingung erfüllen. Rufen Sie zum Suchen eines Datensatzes in einem Recordset-Objekt vom Typ Tabelle `Seek`.  
  
 Wenn das Recordset zu einem Recordset vom Typ Tabelle bezieht, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie den aktuellen Index nicht festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Wenn Sie aufrufen `MoveLast` auf einem Recordset-Objekt, das auf einer SQL-Abfrage oder Querydef basiert, wird die Abfrage bis zum Abschluss erzwungen, und das Recordset-Objekt wird vollständig aufgefüllt.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious-Methoden" in der DAO-Hilfe.  
  
##  <a name="movenext"></a>CDaoRecordset::MoveNext  
 Rufen Sie diese Memberfunktion zum nächsten Datensatz im Recordset der aktuelle Datensatz zu erstellen.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, Sie rufen `IsBOF` , bevor Sie versuchen, auf den vorherigen Datensatz wechseln. Ein Aufruf von `MovePrev` löst ein `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. In der Regel rufen Sie beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmen, ob das Recordset Datensätze verfügt. Nach dem Aufruf von **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben werden, ohne eine Bedingung anzuwenden. Verwenden Sie die Operationen zum Suchen von Datensätzen in einem Dynaset oder vom Typ Snapshot-Recordset-Objekts, die eine bestimmte Bedingung erfüllen. Rufen Sie zum Suchen eines Datensatzes in einem Recordset-Objekt vom Typ Tabelle `Seek`.  
  
 Wenn das Recordset zu einem Recordset vom Typ Tabelle bezieht, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie den aktuellen Index nicht festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious-Methoden" in der DAO-Hilfe.  
  
##  <a name="moveprev"></a>CDaoRecordset::MovePrev  
 Rufen Sie diese Memberfunktion zum vorherigen Datensatz im Recordset der aktuelle Datensatz zu erstellen.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Es wird empfohlen, Sie rufen `IsBOF` , bevor Sie versuchen, auf den vorherigen Datensatz wechseln. Ein Aufruf von `MovePrev` löst ein `CDaoException` Wenn `IsBOF` gibt einen Wert ungleich NULL, der angibt, dass Sie bereits vor dem ersten Datensatz gescrollt haben oder keine Datensätze vom Recordset ausgewählt wurden.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. In der Regel rufen Sie beide `IsBOF` und `IsEOF` vor einem Verschiebevorgang bestimmen, ob das Recordset Datensätze verfügt. Nach dem Aufruf von **öffnen** oder **Requery**, rufen Sie entweder `IsBOF` oder `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Verwenden der **verschieben** Funktionen von Datensatz zu Datensatz verschoben werden, ohne eine Bedingung anzuwenden. Verwenden Sie die Operationen zum Suchen von Datensätzen in einem Dynaset oder vom Typ Snapshot-Recordset-Objekts, die eine bestimmte Bedingung erfüllen. Rufen Sie zum Suchen eines Datensatzes in einem Recordset-Objekt vom Typ Tabelle `Seek`.  
  
 Wenn das Recordset zu einem Recordset vom Typ Tabelle bezieht, folgt die Bewegung der Index der aktuellen Tabelle. Sie können den aktuellen Index festlegen, mit der Index-Eigenschaft des zugrunde liegenden DAO-Objekts. Wenn Sie den aktuellen Index nicht festlegen, ist die Reihenfolge der zurückgegebenen Datensätze nicht definiert.  
  
 Kann nicht aufgerufen werden die **MoveFirst** oder `MovePrev` Memberfunktion mit einem Bildlauf vorwärts-Snapshot.  
  
 Aufrufen, um die Position des aktuellen Zeichnen in einem Recordset-Objekt eine bestimmte Anzahl von Datensätzen vorwärts oder rückwärts zu verschieben, **verschieben**.  
  
 Weitere Informationen finden Sie unter den Themen "Move-Methode" und "MoveFirst, MoveLast, MoveNext MovePrevious-Methoden" in der DAO-Hilfe.  
  
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
  
- **DbOpenDynaset** einem Dynaset-Recordset mit bidirektionalem Bildlauf. Dies ist die Standardeinstellung.  
  
- **Übergeben** ein Tabellentyp Recordset mit bidirektionalem Bildlauf.  
  
- **DbOpenSnapshot** einem Snapshot-Recordset mit bidirektionalem Bildlauf.  
  
 `lpszSQL`  
 Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:  
  
-   Ein **NULL** Zeiger.  
  
-   Der Name der Tabledefs und/oder Querydefs (durch Trennzeichen getrennt).  
  
-   SQL **auswählen** Anweisung (optional mit einem SQL- **,** oder **ORDERBY** Klausel).  
  
-   Eine Pass-Through-Abfrage.  
  
 `nOptions`  
 Mindestens eine der unten aufgeführten Optionen. Der Standardwert ist 0. Folgende Werte sind möglich:  
  
- **DbAppendOnly** können Sie nur neue Datensätze (nur vom Typ Dynaset-Recordset) anfügen. Diese Option also buchstäblich Datensätze nur angefügt werden können. Die MFC-ODBC-Datenbankklassen haben eine nur Anhängen-Option, mit der Datensätze abgerufen und angefügt werden.  
  
- **DbForwardOnly** das Recordset ist ein Bildlauf vorwärts-Snapshot.  
  
- **DbSeeChanges** eine Ausnahme generiert, wenn ein anderer Benutzer Daten ändert, die Sie bearbeiten.  
  
- **DbDenyWrite** andere Benutzer nicht ändern oder Hinzufügen von Datensätzen.  
  
- **DbDenyRead** andere Benutzer können keine Datensätze (nur Recordset vom Typ Tabelle) anzeigen.  
  
- **DbReadOnly** können Sie nur Datensätze anzeigen, die andere Benutzer geändert werden können.  
  
- **DbInconsistent** inkonsistente Aktualisierungen sind zulässig (nur vom Typ Dynaset-Recordset).  
  
- **DbConsistent** nur einheitliche Updates (nur vom Typ Dynaset-Recordset) sind zulässig.  
  
> [!NOTE]
>  Die Konstanten **DbConsistent** und **DbInconsistent** gegenseitig aus. Verwenden Sie eine oder die andere aber nicht beide in einer bestimmten Instanz des **öffnen**.  
  
 *pTableDef*  
 Ein Zeiger auf eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt. Diese Version ist nur für Recordsets vom Typ Tabelle gültig. Bei Verwendung dieser Option die `CDaoDatabase` Zeiger erstellt die `CDaoRecordset` nicht verwendet wird, sondern unter Verwendung der Datenbank in der Tabledef befindet.  
  
 *pQueryDef*  
 Ein Zeiger auf eine [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) Objekt. Diese Version ist nur für Dynaset und Snapshot-Typ gültig. Bei Verwendung dieser Option die `CDaoDatabase` Zeiger erstellt die `CDaoRecordset` nicht verwendet wird, sondern unter Verwendung der Datenbank in der Querydef befindet.  
  
### <a name="remarks"></a>Hinweise  
 Vor dem Aufruf von **öffnen**, müssen Sie das Recordset-Objekt erstellen. Dafür stehen verschiedene Möglichkeiten zur Verfügung:  
  
-   Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das bereits geöffnet ist.  
  
-   Wenn Sie das Recordset-Objekt erstellen, übergeben Sie einen Zeiger auf eine `CDaoDatabase` -Objekt, das nicht geöffnet ist. Öffnen des Recordsets einen `CDaoDatabase` -Objekt, jedoch wird nicht geschlossen werden das Recordset-Objekt geschlossen wird.  
  
-   Übergeben Sie das Recordset-Objekt erstellen, eine **NULL** Zeiger. Die Recordset-Objekt Aufrufe `GetDefaultDBName` zum Abrufen des Namens des Microsoft Access. MDB-Datei zu öffnen. Öffnet das Recordset ein `CDaoDatabase` Objekt und hält sie zu öffnen, solange das Recordset geöffnet ist. Beim Aufruf von **schließen** für das Recordset die `CDaoDatabase` Objekt ebenfalls geschlossen.  
  
    > [!NOTE]
    >  Beim Öffnen des Recordsets die `CDaoDatabase` -Objekt, die Datenquelle nicht exklusiven Zugriff geöffnet wird.  
  
 Für die Version des **öffnen** , verwendet der `lpszSQL` -Parameter, sobald das Recordset geöffnet ist, können Sie Datensätze in eine von mehreren Methoden abrufen. Die erste Möglichkeit besteht, dass DFX-Funktionen in Ihrer `DoFieldExchange`. Die zweite Option ist die Verwendung von dynamischen Bindung durch Aufrufen der `GetFieldValue` Member-Funktion. Diese Optionen können einzeln oder in Kombination implementiert werden. Wenn sie kombiniert werden, müssen die SQL-Anweisung selbst beim Aufruf übergeben **öffnen**.  
  
 Bei Verwendung die zweite Version **öffnen** , übergeben Sie eine `CDaoTableDef` -Objekt, die daraus resultierenden Spalten stehen über binden `DoFieldExchange` und der DFX-Mechanismus und/oder Bindung dynamisch über `GetFieldValue`.  
  
> [!NOTE]
>  Können Sie nur aufrufen **öffnen** mit einem `CDaoTableDef` -Objekt für Recordsets vom Typ Tabelle.  
  
 Wenn Sie die dritte Version von verwenden **öffnen** , übergeben Sie eine `CDaoQueryDef` -Objekt, dass die Abfrage ausgeführt, und die daraus resultierenden Spalten stehen über binden `DoFieldExchange` und der DFX-Mechanismus und/oder Bindung dynamisch über `GetFieldValue`.  
  
> [!NOTE]
>  Können Sie nur aufrufen **öffnen** mit einem `CDaoQueryDef` Objekt vom Typ Dynaset und Snapshot-Typ.  
  
 Für die erste Version des **öffnen** , verwendet der `lpszSQL` -Parameter, die Datensätze sind ausgewählten basierend auf Kriterien in der folgenden Tabelle dargestellt.  
  
|Der Wert des Parameters `lpszSQL`.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|  
|--------------------------------------|----------------------------------------|-------------|  
|**NULL**|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||  
|Eine durch Trennzeichen getrennte Liste von ein oder mehrere Tabledefs und/oder Querydef-Namen.|Alle Spalten dargestellt, der `DoFieldExchange`.|`"Customer"`|  
|**Wählen Sie** Spaltenliste **von** Tabellenliste|Die angegebenen Spalten von der angegebenen Tabledef(s) und/oder Querydef(s).|`"SELECT CustId, CustName`<br /><br /> `FROM Customer"`|  
  
 Die übliche Vorgehensweise ist die Übergabe **NULL** auf **öffnen**; in diesem Fall **öffnen** Aufrufe `GetDefaultSQL`, eine überschreibbare Member-Funktion, die Klassen-Assistent beim Erstellen generiert einer `CDaoRecordset`-abgeleiteten Klasse. Dieser Wert stellt die Tabledef(s) und/oder Querydef-Namen, die Sie im Klassen-Assistenten angegeben. Sie können stattdessen andere Informationen im `lpszSQL`-Parameter angeben.  
  
 Jede Übergabe **öffnen** erstellt eine endgültige SQL-Anweisung für die Abfrage (Zeichenfolge möglicherweise die SQL **, in dem** und **ORDERBY** Klauseln angefügt, um die `lpszSQL` Sie übergebene Zeichenfolge) und führt dann die Abfrage. Sie können die erstellte Zeichenfolge überprüfen, durch Aufrufen von `GetSQL` nach dem Aufruf von **öffnen**.  
  
 Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 Wenn Sie Optionen für das Recordset, wie z. B. einen Filter oder eine Sortierung festlegen möchten `m_strSort` oder **M_strFilter** nach der Konstruktion des Recordset-Objekts, aber vor dem Aufruf von **öffnen**. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie **Requery**.  
  
 Wenn Sie aufrufen **öffnen** auf einem Dynaset oder vom Typ Snapshot-Recordset, oder wenn die Datenquelle bezieht sich auf eine SQL-Anweisung oder einer Tabledef, die eine angefügte Tabelle darstellt, können keine **übergeben** für das Typargument; anderenfalls MFC löst eine Ausnahme aus. Bestimmt, ob ein Tabledef-Objekt eine angefügte Tabelle darstellt, erstellen eine [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) Objekt, und rufen die [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) Member-Funktion.  
  
 Verwenden der **DbSeeChanges** kennzeichnen, wenn Sie Änderungen, die von einem anderen Benutzer oder ein anderes Programm auf Ihrem Computer, wenn Sie bearbeiten oder löschen den gleichen Datensatz abfangen möchten. Wenn zwei Benutzer starten, bearbeiten den gleichen Datensatz, der erste Benutzer aufrufen, z. B. die **Update** Memberfunktion erfolgreich ausgeführt wird. Wenn **Update** heißt der zweite Benutzer eine `CDaoException` ausgelöst. Auf ähnliche Weise, wenn der zweite Benutzer versucht, rufen Sie **löschen** So löschen Sie den Datensatz, und es bereits geändert wurde der erste Benutzer, eine `CDaoException` auftritt.  
  
 In der Regel, wenn der Benutzer dadurch erhält `CDaoException` während der Aktualisierung der Code den Inhalt der Felder aktualisieren und die geänderten Werte abrufen. Tritt die Ausnahme gerade gelöscht, konnte der Code Daten des neuen Datensatzes anzeigen, für den Benutzer und eine Meldung, dass die Daten zuletzt geändert hat. An diesem Punkt kann Ihr Code eine Bestätigung anfordern, dass der Benutzer immer noch den Datensatz löschen möchte.  
  
> [!TIP]
>  Verwenden Sie die Bildlauf vorwärts-Option ( **DbForwardOnly**) zur Verbesserung der Leistung, wenn Ihre Anwendung auf einem einzelnen Durchlauf durch ein Recordset durchführt, die von einer ODBC-Datenquelle geöffnet.  
  
 Verwandte Informationen finden Sie im Thema "OpenRecordset-Methode" in der DAO-Hilfe.  
  
##  <a name="requery"></a>CDaoRecordset::Requery  
 Rufen Sie diese Memberfunktion zum neu erstellen (aktualisieren) einem Recordset.  
  
```  
virtual void Requery();
```  
  
### <a name="remarks"></a>Hinweise  
 Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 In der Reihenfolge für das Recordset widerspiegeln, das Hinzufügen und löschen, die Sie oder andere Benutzer mit der Datenquelle herstellen, müssen Sie das Recordset erstellen, durch Aufruf **Requery**. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer die vorhandenen Datensätze (jedoch nicht Additions) Stellen angezeigt. Das Recordset eine Momentaufnahme ist, rufen Sie **Requery** entsprechend der Bearbeitung durch andere Benutzer als auch hinzufügen und löschen.  
  
 Rufen Sie für ein Dynaset oder eine Momentaufnahme, **Requery** Sie das Recordset mit Parameterwerten neu erstellen möchten. Legen Sie die neue filtern oder sortieren, indem Sie [M_strFilter](#m_strfilter) und [M_strSort](#m_strsort) vor dem Aufruf von **Requery**. Neue Parameter festlegen, indem Zuweisen neuer Werte zu Parameterdatenmember vor dem Aufruf von **Requery**.  
  
 Wenn das Recordset neu erstellen fehlschlägt, wird das Recordset geschlossen. Vor dem Aufruf von **Requery**, können Sie bestimmen, ob das Recordset durch Aufrufen von erneut abgefragt werden kann die [CanRestart](#canrestart) Member-Funktion. `CanRestart`garantiert nicht, dass **Requery** wird erfolgreich ausgeführt.  
  
> [!CAUTION]
>  Rufen Sie **Requery** , wenn Sie aufgerufen haben **öffnen**.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Kann nicht aufgerufen werden **Requery** auf einem Dynaset oder Recordsets vom Typ Snapshot, wenn beim Aufrufen von `CanRestart` gibt 0 zurück, und Sie können es in einem Recordset vom Typ Tabelle.  
  
 Wenn beide `IsBOF` und `IsEOF` ungleich NULL zurückgeben, nach dem Aufruf von **Requery**, die Abfrage wurde Datensätze und das Recordset enthalten keine Daten zurückgegeben.  
  
 Weitere Informationen finden Sie im Thema "Requery-Methode" in der DAO-Hilfe.  
  
##  <a name="seek"></a>CDaoRecordset::Seek  
 Rufen Sie diese Memberfunktion um den Datensatz in einem Recordset-Objekt vom Typ indizierte Tabelle zu suchen, die die angegebenen Kriterien für den aktuellen index und erstellen, die zum aktuellen Datensatz entspricht.  
  
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
 Einer der folgenden Zeichenfolgenausdrücke: "<",></",>\<=", "=", "> =", oder ">".  
  
 `pKey1`  
 Ein Zeiger auf eine [COleVariant](../../mfc/reference/colevariant-class.md) , dessen Wert entspricht dem ersten Feld im Index. Erforderlich.  
  
 *pKey2*  
 Ein Zeiger auf ein `COleVariant` , dessen Wert entspricht das zweite Feld im Index, sofern vorhanden. Standardmäßig **NULL**.  
  
 *pKey3*  
 Ein Zeiger auf ein `COleVariant` , dessen Wert entspricht das dritte Feld im Index, sofern vorhanden. Standardmäßig **NULL**.  
  
 *pKeyArray*  
 Ein Zeiger auf ein Array von Variant. Die Größe des Arrays entspricht der Anzahl der Felder im Index.  
  
 *nKeys*  
 Eine ganze Zahl, die Größe des Arrays, der die Anzahl der Felder im Index entspricht.  
  
> [!NOTE]
>  Geben Sie Platzhalter in den Schlüsseln. Bewirkt, dass Platzhalter `Seek` keine übereinstimmenden Datensätze zurückgeben.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn übereinstimmende Datensätze gefunden werden, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die zweite (Array) Version `Seek` Indizes von vier Feldern oder mehr verarbeiten.  
  
 `Seek`ermöglicht leistungsfähige Index Recordsets vom Typ Tabelle suchen. Sie müssen den aktuellen Index festlegen, durch Aufrufen von `SetCurrentIndex` vor dem Aufruf von `Seek`. Wenn der Index ein nicht eindeutiges Schlüsselfeld oder Felder identifiziert `Seek` sucht den ersten Datensatz, der die Kriterien erfüllt. Wenn Sie einen Index nicht festlegen, wird eine Ausnahme ausgelöst.  
  
 Beachten Sie, dass, wenn Sie ein Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekte müssen explizit ANSI deklariert werden. Dies kann mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form des Konstruktors mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Beim Aufruf von `Seek`, übergeben Sie einen oder mehrere Werte und ein Vergleichsoperator ("<",></",>\<=", "=", "> =", oder ">"). `Seek`durchsucht die angegebenen Schlüsselfelder und sucht nach dem ersten Datensatz, der die angegebenen Kriterien erfüllt `lpszComparison` und `pKey1`. Wenn er gefunden wird, `Seek` gibt einen Wert ungleich NULL und aktuellen Datensatz gemacht. Wenn `Seek` findet eine Übereinstimmung, `Seek` gibt NULL zurück, und der aktuelle Datensatz nicht definiert ist. Wenn DAO direkt zu verwenden, müssen Sie explizit die NoMatch-Eigenschaft prüfen.  
  
 Wenn `lpszComparison` ist "=", "> =", oder ">", `Seek` beginnt am Anfang des Indexes. Wenn `lpszComparison` ist "<" or=""> </"> <=",> </=",> `Seek` startet am Ende des Indexes und sucht rückwärts, es sei denn, es doppelte Einträge am Ende sind. In diesem Fall `Seek` auf einen beliebigen Eintrag auf die doppelte Einträge am Ende des Index beginnt.  
  
 Gibt es keinen aktuellen Datensatz, bei Verwendung von `Seek`.  
  
 Verwenden Sie zum Suchen eines Datensatzes in einem Dynaset oder vom Typ Snapshot-Recordset, das eine bestimmte Bedingung erfüllt die Suchvorgänge. Verwenden Sie die Move-Vorgänge von Datensatz zu Datensatz verschoben, um alle Datensätze, nicht nur diejenigen, die eine bestimmte Bedingung erfüllen.  
  
 Kann nicht aufgerufen werden `Seek` auf einer angefügten Tabelle eines beliebigen eingeben, da der verbundene Tabellen als Dynaset oder Typ Snapshot geöffnet werden müssen. Jedoch wenn Sie aufrufen `CDaoDatabase::Open` um eine installierbare ISAM-Datenbank direkt zu öffnen, rufen Sie `Seek` auf Tabellen in dieser Datenbank zwar die Leistung möglicherweise beeinträchtigt.  
  
 Weitere Informationen finden Sie im Thema "Seek-Methode" in der DAO-Hilfe.  
  
##  <a name="setabsoluteposition"></a>CDaoRecordset::SetAbsolutePosition  
 Legt die relative Datensatznummer des aktuellen Datensatzes des Recordset-Objekts.  
  
```  
void SetAbsolutePosition(long lPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *lPosition*  
 Entspricht der Position des aktuellen Datensatzes im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen von `SetAbsolutePosition` ermöglicht es Ihnen, den aktuellen Datensatzzeiger zu einem bestimmten Datensatz basierend auf seiner Position in einem Dynaset oder vom Typ Snapshot-Recordset zu positionieren. Sie können die Nummer des aktuelle Datensatzes auch bestimmen, durch Aufrufen von [GetAbsolutePosition](#getabsoluteposition).  
  
> [!NOTE]
>  Diese Memberfunktion ist nur für Dynaset und Snapshot-Typ gültig.  
  
 Der Wert der AbsolutePosition-Eigenschaft für das zugrunde liegende DAO-Objekt ist nullbasiert. die Einstellung 0 bezieht sich auf den ersten Datensatz im Recordset. Einrichten eines Werts größer als die Anzahl der aufgefüllten Datensätze, löst MFC eine Ausnahme ausgelöst. Sie können bestimmen, dass die Anzahl der gefüllten Datensätze im Recordset durch Aufrufen der `GetRecordCount` Member-Funktion.  
  
 Wenn der aktuelle Datensatz gelöscht wird, den Wert der AbsolutePosition-Eigenschaft ist nicht definiert und MFC eine Ausnahme auslöst, wenn darauf verwiesen wird. Neue Datensätze werden am Ende der Sequenz hinzugefügt.  
  
> [!NOTE]
>  Diese Eigenschaft sollte nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, um eine bestimmte Position und Sie sind die einzige Möglichkeit, den aktuellen Datensatz für alle Typen von Recordset-Objekte zu positionieren, die Lesezeichen unterstützen. Insbesondere ändert die Position eines bestimmten Datensatzes beim vorhergehenden Datensätze gelöscht werden. Es gibt auch keine Gewähr, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze in einem Recordset nicht garantiert ist, es sei denn, sie mit einer SQL-Anweisung mit erstellt wird ein **ORDERBY** Klausel.  
  
 Verwandte Informationen finden Sie im Thema "AbsolutePosition-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setbookmark"></a>CDaoRecordset:: SetBookmark  
 Rufen Sie diese Memberfunktion des Recordsets auf den Datensatz mit dem angegebenen Lesezeichen positionieren.  
  
```  
void SetBookmark(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) Objekt mit dem Lesezeichenwert "für einen bestimmten Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Wenn ein Recordset-Objekt erstellt oder geöffnet wird, hat jeder Datensatz bereits ein eindeutiges Lesezeichen. Sie können das Lesezeichen für den aktuellen Datensatz abrufen, durch Aufrufen von `GetBookmark` und speichern den Wert ein `COleVariant` Objekt. Sie können später zu diesem Datensatz zurückkehren, indem `SetBookmark` mit den gespeicherten Lesezeichenwert.  
  
> [!NOTE]
>  Aufrufen von [Requery](#requery) DAO Lesezeichen ändert.  
  
 Beachten Sie, dass, wenn Sie ein Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form des Konstruktors mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie unter den Themen "Lesezeichen-Eigenschaft" und Lesezeichenfähig Eigenschaft"DAO-Hilfe.  
  
##  <a name="setcachesize"></a>CDaoRecordset:: SetCacheSize  
 Rufen Sie diese Memberfunktion zum Festlegen der Anzahl von Datensätzen, die zwischengespeichert werden.  
  
```  
void SetCacheSize(long lSize);
```  
  
### <a name="parameters"></a>Parameter  
 `lSize`  
 Gibt die Anzahl der Datensätze. Ein häufig angegebener Wert ist 100. Die Einstellung 0 deaktiviert das Zwischenspeichern. Die Einstellung muss zwischen 5 und 1200 Datensätze sein. Der Cache kann eine beträchtliche Menge an Arbeitsspeicher verwenden.  
  
### <a name="remarks"></a>Hinweise  
 Ein Cache ist ein Bereich im lokalen Speicher, der enthält die Daten, die zuletzt vom Server abgerufen, die die Daten erneut angefordert werden, während die Anwendung ausgeführt wird. Zwischenspeichern von Daten verbessert die Leistung einer Anwendung, die Daten von einem Remoteserver über Recordset-Objekte vom Typ Dynaset abruft. Wenn Daten angefordert werden, überprüft das Microsoft Jet-Datenbankmodul den Cache für die angeforderten Daten zunächst statt Abruf aus dem Server mehr Zeit in Anspruch. Daten, die nicht von einer ODBC-Datenquelle stammen, werden nicht im Cache gespeichert.  
  
 Eine ODBC-Datenquelle, z. B. einer angefügten Tabelle, kann einen lokalen Cache haben. Um den Cache zu erstellen, öffnen Sie ein Recordset-Objekt in der Remotedatenquelle Aufruf der `SetCacheSize` und `SetCacheStart` Memberfunktionen und rufen Sie dann die `FillCache` Memberfunktion oder Schritt durch die Datensätze mithilfe einer der Move-Vorgängen. Die `lSize` Parameter von der `SetCacheSize` Member-Funktion kann basieren auf der Anzahl der Datensätze, die Ihre Anwendung gleichzeitig arbeiten kann. Können z. B., wenn Sie eine Datensatzgruppe als Quelle der Daten verwenden, die auf dem Bildschirm angezeigt werden, Sie übergeben die `SetCacheSize``lSize` Parameter als 20 bis 20 Datensätze gleichzeitig angezeigt.  
  
 Verwandte Informationen finden Sie im Thema "CacheSize CacheStart-Eigenschaften" in der DAO-Hilfe.  
  
##  <a name="setcachestart"></a>CDaoRecordset:: SetCacheStart  
 Rufen Sie diese Memberfunktion zum Geben Sie des Lesezeichens des ersten Datensatzes im Recordset zwischengespeichert werden.  
  
```  
void SetCacheStart(COleVariant varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein [COleVariant](../../mfc/reference/colevariant-class.md) , der das Lesezeichen des ersten Datensatzes im Recordset zwischengespeichert werden angibt.  
  
### <a name="remarks"></a>Hinweise  
 Können Sie die Lesezeichenwert eines beliebigen Datensatzes für die `varBookmark` Parameter von der `SetCacheStart` Member-Funktion. Machen Sie den Datensatz, die Sie verwenden möchten, starten den Cache mit den aktuellen Datensatz, Einrichten eines Lesezeichens nach diesem Datensatz mit [SetBookmark](#setbookmark), und übergeben Sie die Lesezeichenwert als Parameter für die `SetCacheStart` -Memberfunktion.  
  
 Das Microsoft Jet-Datenbankmodul fordert Datensätze innerhalb des Bereichs der Cache aus dem Cache, und fordert Datensätze außerhalb des Bereichs der Cache auf dem Server.  
  
 Aus dem Cache abgerufenen Datensätze nicht gleichzeitig die Daten von anderen Benutzern vorgenommenen Änderungen wieder.  
  
 Übergeben, um eine Aktualisierung aller zwischengespeicherten Daten erzwingen, die `lSize` Parameter der `SetCacheSize` als 0 ist, rufen Sie `SetCacheSize` erneut mit der Größe des Caches Sie ursprünglich angefordert hat, und rufen Sie dann die `FillCache` -Memberfunktion.  
  
 Beachten Sie, dass, wenn Sie ein Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form des Konstruktors mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie im Thema CacheSize, CacheStart-Eigenschaften"in der DAO-Hilfe.  
  
##  <a name="setcurrentindex"></a>CDaoRecordset:: SetCurrentIndex  
 Rufen Sie diese Memberfunktion, um einen Index für ein Recordset vom Typ Tabelle festzulegen.  
  
```  
void SetCurrentIndex(LPCTSTR lpszIndex);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszIndex`  
 Ein Zeiger, mit dem Namen des Index festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 In Basistabellen werden nicht in einer bestimmten Reihenfolge gespeichert. Einen Index festlegen, ändert die Reihenfolge der Datensätze aus der Datenbank zurückgegeben, aber es hat keinen Einfluss auf die Reihenfolge, in der die Datensätze gespeichert sind. Der angegebene Index muss bereits definiert sein. Wenn Sie versuchen, einen Indexobjekt verwenden, das nicht vorhanden ist oder wenn der Index nicht festgelegt ist, beim Aufruf von [Seek](#seek), MFC löst eine Ausnahme aus.  
  
 Sie können einen neuen Index für die Tabelle erstellen, durch Aufrufen von [CDaoTableDef::CreateIndex](../../mfc/reference/cdaotabledef-class.md#createindex) und hängen Sie den neuen Index der Indexes-Auflistung des zugrunde liegenden Tabledef durch Aufrufen von [CDaoTableDef::](../../mfc/reference/cdaotabledef-class.md#append), und anschließend erneut öffnen des Recordsets.  
  
 Datensätze aus einem Recordset vom Typ Tabelle können nur durch die Indizes für die zugrunde liegenden Tabledef bestellt werden. Um Datensätze in einer anderen Reihenfolge sortieren, können Sie öffnen ein Dynaset oder vom Typ Snapshot-Recordset mit SQL **ORDERBY** -Klausel in gespeicherten [CDaoRecordset::m_strSort](#m_strsort).  
  
 Weitere Informationen finden Sie im Thema "Index-Objekt" und in der Definition "aktuellen Index" in der DAO-Hilfe.  
  
##  <a name="setfielddirty"></a>CDaoRecordset:: SetFieldDirty  
 Rufen Sie diese Memberfunktion zum Felddatenmember des Recordset-Objekts als geändert oder nicht als geändert gekennzeichnet.  
  
```  
void SetFieldDirty(
    void* pv,  
    BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des Felddatenmember im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember im Recordset gekennzeichnet sind. (C++ **NULL** ist nicht identisch mit Null in der Terminologie für Datenbanken, d. h. "keinen Wert aufweisen.")  
  
 `bDirty`  
 **True,** ist der Felddatenmember als "(geändert) geändert" gekennzeichnet werden. Andernfalls **FALSE** ist der Felddatenmember als "(unverändert) bereinigen" gekennzeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Markieren die Felder unverändert wird sichergestellt, dass das Feld nicht aktualisiert wird.  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie auf den Datensatz in der Datenquelle von den DAO-Datensatzfeldaustausch (DFX)-Mechanismus geschrieben werden. Ändern den Wert eines Felds in der Regel das Feld modifizierte automatisch festgelegt, daher nur in seltenen Fällen Sie aufrufen müssen, `SetFieldDirty` sich jedoch möglicherweise manchmal sicherstellen möchten, dass Spalten explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert im Felddatenmember ist. DFX-Mechanismus verwendet auch die Verwendung von **PSEUDONULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
 Wenn die doppelte Pufferung Mechanismus nicht verwendet wird, wird dann ändern den Wert des Felds nicht automatisch das Feld als fehlerhaft festgelegt. In diesem Fall werden muss das Feld als fehlerhaft explizit festgelegt. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
> [!NOTE]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mithilfe von **NULL** für das erste Argument der Funktion die Funktion für alle gelten **OutputColumn** Felder nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase&6;](../../mfc/codesnippet/cpp/cdaorecordset-class_6.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder werden nicht beeinflusst.  
  
 Auf einem **Param**, müssen Sie die tatsächliche Adresse der Person angeben **Param** , wie z. B. arbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase&#7;](../../mfc/codesnippet/cpp/cdaorecordset-class_7.cpp)]  
  
 Dies bedeutet, Sie können nicht festgelegt, werden alle **Param** Felder **NULL**, wie **OutputColumn** Felder.  
  
 `SetFieldDirty`wird über implementiert `DoFieldExchange`.  
  
##  <a name="setfieldnull"></a>CDaoRecordset::SetFieldNull  
 Rufen Sie diese Memberfunktion zum Kennzeichnen von Felddatenmember der Recordset als Null (insbesondere mit kein Wert) oder als nicht-Null.  
  
```  
void SetFieldNull(
    void* pv,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des Felddatenmember im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember im Recordset gekennzeichnet sind. (C++ **NULL** ist nicht identisch mit Null in der Terminologie für Datenbanken, d. h. "keinen Wert aufweisen.")  
  
 `bNull`  
 Wert ungleich NULL, wenn die Felddatenmember gekennzeichnet wird, dass kein Wert (Null) ist. Andernfalls 0, wenn die Felddatenmember als ungleich Null gekennzeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 `SetFieldNull`wird für Felder, die im gebundenen verwendet die `DoFieldExchange` Mechanismus.  
  
 Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) geändert" gekennzeichnet. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits Werte oder NULL. Wenn es angebracht, damit ein Feld Null ist, ist ein [CDaoException](../../mfc/reference/cdaoexception-class.md) ausgelöst.  
  
 Wenn Sie die doppelte Pufferung Mechanismus, z. B. verwenden, wenn Sie ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert, rufen Sie möchten `SetFieldNull` mit `bNull` festgelegt **TRUE** so kennzeichnen Sie es als Null. Wenn ein Feld war zuvor Null markiert, und jetzt Sie ihm einen Wert zuzuweisen möchten, legen Sie einfach den neuen Wert. Sie müssen nicht mit der Null-Flag entfernen `SetFieldNull`. Aufrufen, um zu bestimmen, ob das Feld Null sein darf, [IsFieldNullable](#isfieldnullable).  
  
 Wenn Sie die doppelte Pufferung Mechanismus nicht verwenden, wird dann ändern den Wert des Felds nicht automatisch das Feld als modifizierte und ungleich Null festgelegt. Sie müssen insbesondere die Felder geändert und ungleich Null festlegen. Das Flag in enthaltenen [M_bCheckCacheForDirtyFields](#m_bcheckcachefordirtyfields) steuert diese automatische Prüfung.  
  
 DFX-Mechanismus setzt die Verwendung von **PSEUDONULL**. Weitere Informationen finden Sie unter [CDaoFieldExchange::](../../mfc/reference/cdaofieldexchange-class.md#m_noperation).  
  
> [!NOTE]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mithilfe von **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder nicht **Param** Felder in `CDaoFieldExchange`. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase&#8;](../../mfc/codesnippet/cpp/cdaorecordset-class_8.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder werden nicht beeinflusst.  
  
##  <a name="setfieldvalue"></a>CDaoRecordset::SetFieldValue  
 Rufen Sie diese Memberfunktion um den Wert eines Felds durch die Position oder durch Ändern des Werts der Zeichenfolge festzulegen.  
  
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
 Ein Zeiger auf eine Zeichenfolge, die den Namen eines Felds enthält.  
  
 `varValue`  
 Ein Verweis auf eine [COleVariant](../../mfc/reference/colevariant-class.md) Objekt, das den Wert des Felds Inhalt enthält.  
  
 `nIndex`  
 Eine ganze Zahl, die die Ordnungsposition in das Recordset Fields-Auflistung (nullbasiert) des Felds darstellt.  
  
 `lpszValue`  
 Ein Zeiger auf eine Zeichenfolge mit dem Wert, der die Inhalte der Felder enthält.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `SetFieldValue` und [GetFieldValue](#getfieldvalue) Sie Felder zur Laufzeit und nicht statisch Binden von Spalten mit dynamisch binden der [DoFieldExchange](#dofieldexchange) Mechanismus.  
  
 Beachten Sie, dass wenn Sie ein Unicode-Recordset nicht erstellen, Sie entweder eine Form der `SetFieldValue` , die keinen enthalten eine `COleVariant` -Parameter, oder die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form des Konstruktors mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setfieldvaluenull"></a>CDaoRecordset::SetFieldValueNull  
 Rufen Sie diese Memberfunktion, um das Feld auf einen Null-Wert festgelegt.  
  
```  
void SetFieldValueNull(int nIndex);  
void SetFieldValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Felds im Recordset für die Suche über einen nullbasierten Index.  
  
 `lpszName`  
 Der Name des Felds im Recordset für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 C++ **NULL** ist nicht Null, womit, in der datenbankterminologie identisch "keinen Wert aufweisen."  
  
 Weitere Informationen finden Sie unter den Themen "Field-Objekt" und "Value-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="setlockingmode"></a>CDaoRecordset::SetLockingMode  
 Rufen Sie diese Memberfunktion zum Festlegen des Typs für das Recordset sperren.  
  
```  
void SetLockingMode(BOOL bPessimistic);
```  
  
### <a name="parameters"></a>Parameter  
 *bPessimistic*  
 Ein Flag, das die Art der Sperrung angibt.  
  
### <a name="remarks"></a>Hinweise  
 Wenn pessimistische Sperren ist die 2 KB-Seite mit dem von Ihnen bearbeiteten Datensatz ist gesperrt, sobald Sie rufen die **bearbeiten** Member-Funktion. Die Seite ist nicht gesperrt, beim Aufrufen der **Update** oder **schließen** Memberfunktion oder die Vorgänge verschieben oder suchen.  
  
 Wenn optimistischen Sperren aktiviert ist, wird die 2 KB-Seite, die mit dem Datensatz gesperrt, nur verwendet werden, während der Aktualisierung des Datensatzes mit der **Update** Member-Funktion.  
  
 Wenn eine Seite gesperrt ist, kann kein anderer Benutzer Datensätze auf derselben Seite bearbeiten. Wenn Sie aufrufen `SetLockingMode` und übergeben Sie einen Wert ungleich NULL und ein anderer Benutzer bereits die Seite gesperrt hat, wird eine Ausnahme wird ausgelöst, wenn Sie aufrufen **bearbeiten**. Andere Benutzer können Daten aus gesperrten Seiten lesen.  
  
 Wenn Sie aufrufen `SetLockingMode` aufrufen, mit dem Wert&0; (null) und höher **Update** während die Seite von einem anderen Benutzer gesperrt ist, wird eine Ausnahme ausgelöst wird. Um die Änderungen an der Datensatz von einem anderen Benutzer (und Ihre Änderungen verwerfen), rufen Sie die `SetBookmark` Memberfunktion mit dem Lesezeichenwert, der den aktuellen Datensatz.  
  
 Bei der Arbeit mit ODBC-Datenquellen wird das Sperrverhalten immer optimistische.  
  
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
 Die numerische Position des Parameters in der Querydef-Parameters-Auflistung.  
  
 `var`  
 Der festzulegende Wert; Siehe Hinweise.  
  
 `lpszName`  
 Der Name des Parameters, dessen Wert festgelegt werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Die Parameter muss als Teil der SQL-Zeichenfolge des Recordsets bereits eingerichtet haben. Sie können die Parameter nach Namen oder anhand der Indexposition in der Auflistung zugreifen.  
  
 Geben Sie den Wert festlegen als ein `COleVariant` Objekt. Weitere Informationen zum Festlegen der gewünschten Wert und geben Sie Ihre `COleVariant` Objekt, finden Sie unter Klasse [COleVariant](../../mfc/reference/colevariant-class.md). Beachten Sie, dass, wenn Sie ein Unicode-Recordset nicht erstellen, wird die `COleVariant` Objekt muss explizit ANSI deklariert werden. Dies kann mithilfe der [COleVariant::COleVariant](../../mfc/reference/colevariant-class.md#colevariant)**(** `lpszSrc` **,** `vtSrc` **)** Form des Konstruktors mit `vtSrc` festgelegt `VT_BSTRT` (ANSI) oder mithilfe der **COleVariant** Funktion [SetString](../../mfc/reference/colevariant-class.md#setstring)**(** `lpszSrc` **,** `vtSrc` **)** mit `vtSrc` festgelegt `VT_BSTRT`.  
  
##  <a name="setparamvaluenull"></a>CDaoRecordset::SetParamValueNull  
 Rufen Sie diese Memberfunktion zum der Parameter auf einen Null-Wert festgelegt.  
  
```  
void SetParamValueNull(int nIndex);  
void SetParamValueNull(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der Index des Felds im Recordset für die Suche über einen nullbasierten Index.  
  
 `lpszName`  
 Der Name des Felds im Recordset für die Suche nach Namen.  
  
### <a name="remarks"></a>Hinweise  
 C++ **NULL** ist nicht Null, womit, in der datenbankterminologie identisch "keinen Wert aufweisen."  
  
##  <a name="setpercentposition"></a>CDaoRecordset:: SetPercentPosition  
 Rufen Sie diese Memberfunktion, um einen Wert festzulegen, der die ungefähre Position des aktuellen Datensatzes im Recordset-Objekt, das basierend auf dem Prozentsatz der Datensätze im Recordset ändert.  
  
```  
void SetPercentPosition(float fPosition);
```  
  
### <a name="parameters"></a>Parameter  
 *fPosition*  
 Eine Zahl zwischen 0 und 100.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Arbeit mit einem Dynaset oder Snapshot vom Typ füllen Sie zuerst das Recordset durch Verschieben der letzten Datensatz vor dem Aufruf von `SetPercentPosition`. Wenn Sie aufrufen `SetPercentPosition` vor das Recordset vollständig aufgefüllt, ist der Umfang der Bewegung relativ zur Anzahl der Datensätze zugegriffen wird, wie durch den Wert der [GetRecordCount](#getrecordcount). Sie können mit dem letzten Datensatz verschieben durch Aufrufen von `MoveLast`.  
  
 Wenn Sie aufrufen `SetPercentPosition`, zum aktuellen Thread der Datensatz an der ungefähren Position, dieser Wert entspricht.  
  
> [!NOTE]
>  Aufrufen von `SetPercentPosition` zum Verschieben des aktuellen Datensatzes zu einem bestimmten Datensatz in einem Recordset wird nicht empfohlen. Rufen Sie die [SetBookmark](#setbookmark) Memberfunktion stattdessen.  
  
 Verwandte Informationen finden Sie unter dem Thema "PercentPosition-Eigenschaft" in der DAO-Hilfe.  
  
##  <a name="update"></a>CDaoRecordset::Update  
 Rufen Sie diese Memberfunktion nach einem Aufruf der `AddNew` oder **bearbeiten** Member-Funktion.  
  
```  
virtual void Update();
```  
  
### <a name="remarks"></a>Hinweise  
 Dieser Aufruf ist erforderlich, zum Abschließen der `AddNew` oder **bearbeiten** Vorgang.  
  
 Beide `AddNew` und **bearbeiten** vorbereiten Bearbeitungspuffer in der die hinzugefügten oder bearbeiteten Daten platziert werden zum Speichern in der Datenquelle. **Update** speichert die Daten. Nur die Felder markiert oder als geändert erkannt werden aktualisiert.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **Update** aufrufen (und dem zugehörigen `AddNew` oder **bearbeiten** aufrufen) Teil einer Transaktion.  
  
> [!CAUTION]
>  Wenn Sie aufrufen **Update** ohne Aufruf von `AddNew` oder **bearbeiten**, **Update** löst eine `CDaoException`. Wenn Sie aufrufen `AddNew` oder **bearbeiten**, müssen Sie aufrufen, **Update** vor dem Aufruf von [MoveNext](#movenext) oder schließen Sie das Recordset oder die datenquellenverbindung. Andernfalls sind die Änderungen ohne Benachrichtigung.  
  
 Wenn das Recordset-Objekt in einer Umgebung mit mehreren Benutzern pessimistisch gesperrt ist, bleibt der Datensatz ab dem Zeitpunkt gesperrt **bearbeiten** wird verwendet, bis die Aktualisierung abgeschlossen ist. Wenn das Recordset optimistisch gesperrt ist, wird der Datensatz gesperrt und mit der Sperre verglichen wird, kurz bevor sie in der Datenbank aktualisiert wird. Wenn der Datensatz geändert wurde, da Sie aufgerufen **bearbeiten**, **Update** fehl und MFC eine Ausnahme auslöst. Sie können ändern, das Sperrverhalten mit `SetLockingMode`.  
  
> [!NOTE]
>  Eingeschränktes Sperren wird immer auf der externen Datenbank-Formaten, z. B. ODBC und installierbare ISAM verwendet.  
  
 Weitere Informationen finden Sie unter den Themen "AddNew-Methode", "CancelUpdate Method", "Delete-Methode", "LastModified-Eigenschaft", "Update-Methode" und "EditMode-Eigenschaft" in der DAO-Hilfe.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef-Klasse](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace-Klasse](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase-Klasse](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef-Klasse](../../mfc/reference/cdaoquerydef-class.md)

