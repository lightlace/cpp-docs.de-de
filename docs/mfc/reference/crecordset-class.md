---
title: CRecordset-Klasse | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
dev_langs:
- C++
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 98177ada976196da7590464ab5c6412b2c7f28a3
ms.sourcegitcommit: be0e3457f2884551f18e183ef0ea65c3ded7f689
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2018
ms.locfileid: "37079941"
---
# <a name="crecordset-class"></a>CRecordset-Klasse
Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>Member  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|Erstellt ein `CRecordset`-Objekt. Die abgeleitete Klasse muss einen Konstruktor bereitstellen, der dieses Objekt aufruft.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|Für das Hinzufügen eines neuen Datensatzes vorbereitet. Rufen Sie `Update` das Hinzufügen abgeschlossen.|  
|[CRecordset::CanAppend](#canappend)|Gibt einen Wert ungleich NULL, wenn das Recordset über neue Einträge hinzugefügt werden können die `AddNew` Memberfunktion.|  
|[CRecordset:: CanBookmark](#canbookmark)|Gibt einen Wert ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|  
|[CRecordset::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess aus ein zweiter Thread ab.|  
|[CRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer `AddNew` oder `Edit` Vorgang.|  
|[CRecordset::CanRestart](#canrestart)|Gibt NULL zurück, wenn `Requery` aufgerufen werden, um das Recordset Abfrage erneut ausführen.|  
|[CRecordset::CanScroll](#canscroll)|Gibt einen Wert ungleich NULL, wenn Sie durch die Datensätze scrollen können zurück.|  
|[CRecordset::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CRecordset::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|Wird aufgerufen, zum Behandeln von Fehlern, die während des Abrufens der Datensatz generiert.|  
|[CRecordset::Close](#close)|Schließt das Recordset und den ODBC- **Befehls beschäftigt** zugeordnet.|  
|[CRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang einen Bildlauf durchführen.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Wird aufgerufen, zum Austauschen von Datenzeilen aus der Datenquelle in das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).|  
|[CRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).|  
|[CRecordset::Edit](#edit)|Für die Änderungen an den aktuellen Datensatz vorbereitet. Rufen Sie `Update` um die Bearbeitung abzuschließen.|  
|[CRecordset::FlushResultSet](#flushresultset)|Gibt, die ungleich NULL, wenn es ein anderes Resultset festgelegt abgerufen werden soll, wenn Sie eine vordefinierte Abfrage verwenden.|  
|[CRecordset::GetBookmark](#getbookmark)|Das Parameterobjekt des lesezeichenwerts eines Datensatzes zugewiesen.|  
|[GetDefaultConnect](#getdefaultconnect)|Wird aufgerufen, um die Standardverbindungszeichenfolge zu erhalten.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, um die Standard-SQL-Zeichenfolge auszuführende abzurufen.|  
|[CRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Gibt die Anzahl der Felder im Recordset-Objekt zurück.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurückgegeben in einem Recordset.|  
|[CRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze im Recordset.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|Gibt die Anzahl der Datensätze, die Sie während einer einzigen Abfrage abrufen möchten.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|Gibt die tatsächliche Anzahl von Zeilen, während ein Abrufvorgang abgerufen werden.|  
|[CRecordset::GetRowStatus](#getrowstatus)|Gibt den Status der Zeile nach einer Fetch zurück.|  
|[CRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset verwendet.|  
|[CRecordset::GetStatus](#getstatus)|Ruft den Status des Recordsets ab: der Index des aktuellen Datensatzes und gibt an, ob eine endgültige Anzahl der Datensätze abgerufen wurde.|  
|[CRecordset::GetTableName](#gettablename)|Ruft den Namen der Tabelle auf der sich die Datensatzgruppe basiert.|  
|[CRecordset::IsBOF](#isbof)|Gibt ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es ist kein aktueller Datensatz vorhanden.|  
|[CRecordset::IsDeleted](#isdeleted)|Gibt einen Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist.|  
|[CRecordset::IsEOF](#iseof)|Gibt einen Wert ungleich NULL, wenn das Recordset hinter dem letzten Datensatz positioniert wurde wurde zurück. Es ist kein aktueller Datensatz vorhanden.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CRecordset::IsFieldNull](#isfieldnull)|Gibt ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz null ist (kein Wert hat).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz festgelegt werden kann, auf null (kein Wert mit) zurück.|  
|[CRecordset::IsOpen](#isopen)|Gibt NULL zurück, wenn `Open` zuvor aufgerufen wurde.|  
|[CRecordset](#move)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|  
|[CRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz im ersten Datensatz des Recordsets. Test für `IsBOF` erste.|  
|[CRecordset::MoveLast](#movelast)|Den aktuellen Datensatz positioniert, auf den letzten Datensatz oder des letzten Rowsets. Test für `IsEOF` erste.|  
|[CRecordset::MoveNext](#movenext)|Die Position des aktuellen Datensatzes auf den nächsten Datensatz oder des nächsten Rowsets. Test für `IsEOF` erste.|  
|[CRecordset::MovePrev](#moveprev)|Die Position des aktuellen Datensatzes des vorherigen Datensatzes oder für das vorherige Rowset. Test für `IsBOF` erste.|  
|[CRecordset::OnSetOptions](#onsetoptions)|Wird zum Festlegen von Optionen, die (in der Auswahl verwendete) für die angegebene ODBC-Anweisung aufgerufen.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Zum Festlegen von Optionen (verwendet für Update) für die angegebene ODBC-Anweisung aufgerufen.|  
|[CRecordset:: Open](#open)|Öffnet das Recordset, indem die Tabelle abgerufen oder die vom Recordset darstellte Abfrage durchgeführt wird.|  
|[CRecordset::RefreshRowset](#refreshrowset)|Aktualisiert die Daten und Status, der die angegebene(n) Zeile(n).|  
|[CRecordset](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|  
|[CRecordset:: SetAbsolutePosition auf](#setabsoluteposition)|Positioniert das Recordset im Datensatz, der angegebene Datensatz entspricht.|  
|[CRecordset::SetBookmark](#setbookmark)|Positioniert das Recordset im Datensatz, der vom Lesezeichen angegeben.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz, als geändert.|  
|[CRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds in den aktuellen Datensatz auf null (kein Wert mit) fest.|  
|[CRecordset::SetLockingMode](#setlockingmode)|Legt das Sperrverhalten "optimistic" Sperren (Standard) oder "vollständige" Sperren. Bestimmt, wie Datensätze gesperrt werden, nach Updates.|  
|[CRecordset::SetParamNull](#setparamnull)|Legt die angegebenen Parameter auf null (kein Wert mit).|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Positioniert den Cursor in der angegebenen Zeile im Rowset.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|Gibt die Anzahl der Datensätze, die Sie während eines Abrufs abrufen möchten.|  
|[CRecordset:: Update](#update)|Schließt eine `AddNew` oder `Edit` Vorgangs durch die neuen oder bearbeiteten Daten speichern, für die Datenquelle.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[M_hstmt](#m_hstmt)|Den Handle der ODBC-Anweisung für das Recordset enthält. Geben Sie `HSTMT` ein.|  
|[CRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember des Recordsets. Geben Sie `UINT` ein.|  
|[CRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in Recordsets. Geben Sie `UINT` ein.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.|  
|[CRecordset:: M_strfilter](#m_strfilter)|Enthält eine `CString` , die angibt, Structured Query Language (SQL) `WHERE` Klausel. Als Filter verwendet, um nur die Datensätze auszuwählen, die bestimmte Kriterien erfüllen.|  
|[CRecordset::m_strSort](#m_strsort)|Enthält eine `CString` , die angibt, einer SQL `ORDER BY` Klausel. Zum Steuern, wie die Einträge sortiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Bekannt als "Recordsets" `CRecordset` Objekte dienen in der Regel in zwei Formen: Dynasets und Momentaufnahmen. Mit den des Datenupdates von anderen Benutzern bleibt ein Dynaset synchronisiert. Eine Momentaufnahme ist eine statische Ansicht der Daten. Jedes Formular stellt eine Gruppe von Datensätzen, die behoben werden, zu dem Zeitpunkt, die das Recordset geöffnet ist, aber wenn Sie einen Bildlauf zu einem Datensatz in einem Dynaset ausführen, gibt Sie von anderen Benutzern oder indem Sie weitere Recordsets in Ihrer Anwendung anschließend mit dem Datensatz vorgenommenen Änderungen wieder.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Zum Arbeiten mit beide Arten Recordset leiten Sie in der Regel eine anwendungsspezifische Recordsetklasse von `CRecordset`. Recordsets werden Datensätze aus einer Datenquelle auswählen und anschließend können Sie:  
  
-   Führen Sie einen Bildlauf durch die Datensätze.  
  
-   Zum Aktualisieren Sie der Datensätze, und geben Sie einen Sperrmodus.  
  
-   Filtern Sie das Recordset, um die Datensätze zu beschränken, damit aus den verfügbaren für die Datenquelle ausgewählt.  
  
-   Sortieren Sie das Recordset.  
  
-   Parametrisieren Sie das Recordset, um seine Auswahl mit Informationen, die erst zur Laufzeit bekannt anpassen.  
  
 Um Ihre Klasse verwenden, öffnen Sie eine Datenbank, und erstellen Sie ein Recordset-Objekts, übergeben dem Konstruktor einen Zeiger auf die `CDatabase` Objekt. Rufen Sie dann des Recordsets `Open` Memberfunktion ist, in dem Sie angeben können, ob das Objekt ein Dynaset oder eine Momentaufnahme ist. Aufrufen von `Open` wählt Daten aus der Datenquelle. Nach dem Öffnen des Recordset-Objekts verwenden Sie die Member-Funktionen und Datenmember, um durch die Datensätze scrollen und diese verarbeiten. Die verfügbaren Vorgänge hängen gibt an, ob das Objekt ein Dynaset oder eine Momentaufnahme ist es aktualisierbar oder schreibgeschützt ist (Dies hängt die Fähigkeit der Open Database Connectivity (ODBC)-Datenquelle), und gibt an, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben. Datensätze zu aktualisieren, die wurde geändert oder hinzugefügt werden, da die `Open` aufzurufen, rufen Sie des Objekts `Requery` Memberfunktion. Rufen Sie des Objekts `Close` Member-Funktion und zerstören Sie das Objekt aus, wenn Sie damit fertig sind.  
  
 In einer abgeleiteten `CRecordset` Klasse, Datensatzfeldaustausch (RFX) oder der Massen-Datensatzfeldaustausch (Bulk-RFX) wird zum Lesen und Aktualisieren von Datensatzfelder unterstützen.  
  
 Weitere Informationen zu Recordsets und Datensatz Datensatzfeldern, finden Sie in den Artikeln [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md), [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md). Schwerpunkt auf Dynasets und Momentaufnahmen, finden Sie in den Artikeln [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="addnew"></a>  CRecordset::AddNew  
 Für das Hinzufügen eines neuen Datensatzes zur Tabelle vorbereitet.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie die [Requery](#requery) Memberfunktion versucht, den neu hinzugefügten Eintrag finden Sie unter. Felder des Datensatzes sind anfänglich Null. (In der datenbankterminologie von-Null bedeutet "kein Wert having" und entspricht nicht dem als **NULL** in C++.) Um den Vorgang abzuschließen, rufen Sie die [Update](#update) Memberfunktion. `Update` Speichert die Änderungen an der Datenquelle an.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `AddNew`. Dadurch wird ein Assertionsfehler zurückgeben. Obwohl Klasse `CRecordset` bietet einen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `AddNew` wird einen neuen, leeren Datensatz, verwenden das Recordset-Felddatenmember vorbereitet. Nach dem Aufruf `AddNew`, legen Sie die Werte in das Recordset-Felddatenmember. (Sie müssen keine Aufrufen der [bearbeiten](#edit) Memberfunktion für diesen Zweck; verwenden Sie `Edit` nur für vorhandene Datensätze.) Wenn Sie später Aufrufen `Update`, geänderte Werte in den Felddatenmembern in der Datenquelle gespeichert sind.  
  
> [!CAUTION]
>  Wenn Sie einen Bildlauf zu einem neuen Datensatz durchführen, vor dem Aufruf `Update`, der neue Datensatz verloren gegangen ist und keine Warnung ausgegeben.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie in der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md). Beachten Sie, die Sie aufrufen sollte [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf `AddNew`.  
  
> [!NOTE]
>  Für Dynasets werden neue Datensätze als letzten Datensatz des Recordsets hinzugefügt. Hinzugefügte Datensätze werden Momentaufnahmen nicht hinzugefügt; Rufen Sie `Requery` das Recordset zu aktualisieren.  
  
 Es ist nicht zulässig, rufen Sie `AddNew` für ein Recordset, deren `Open` Memberfunktion nicht aufgerufen wurde. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen `AddNew` für ein Recordset, das zum angefügt werden kann. Sie können bestimmen, ob das Recordset aktualisierbar, durch den Aufruf ist [CanAppend](#canappend).  
  
 Weitere Informationen finden Sie unter den folgenden Artikeln: [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), und [Transaktion () ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="canappend"></a>  CRecordset::CanAppend  
 Bestimmt, ob das zuvor geöffnete Recordset Sie neue Datensätze hinzufügen können.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Hinzufügen von neuen Datensätzen; andernfalls 0. `CanAppend` Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet wurde.  
  
##  <a name="canbookmark"></a>  CRecordset:: CanBookmark  
 Bestimmt, ob das Recordset ermöglicht Sie Datensätze, die mithilfe von Lesezeichen zu kennzeichnen.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Recordset Lesezeichen unterstützt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist unabhängig von der **CRecordset:: useBookmarks** -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion. `CanBookmark` Gibt an, ob der angegebene ODBC-Treiber und die Cursor unterstützt Lesezeichen. **CRecordset:: useBookmarks** gibt an, ob Lesezeichen verfügbar sein soll, sofern diese unterstützt werden.  
  
> [!NOTE]
>  Lesezeichen werden nicht auf die Forward-only-Recordsets unterstützt.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cancel"></a>  CRecordset::Cancel  
 Fordert an, dass die Datenquelle eines asynchronen Vorgangs oder eines Prozesses aus ein zweiter Thread "Abbrechen".  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt aufrufen die ODBC-API-Funktion **SQLSetConnectOption**. Weitere Informationen finden Sie im Thema "Funktionen asynchron ausführen" in der *ODBC SDK Programmer's Guide*.  
  
##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate  
 Bricht alle ausstehenden Updates zurückzuführen sind, ein [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang vor dem [Update](#update) aufgerufen wird.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht in Recordsets, die gesammelte, da solche Recordsets aufrufen kann nicht anwendbar `Edit`, `AddNew`, oder `Update`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Wenn die automatische Überprüfung fehlerhafter Felder aktiviert ist, `CancelUpdate` wird die Membervariablen mit den Werten, die vor diesem Unternehmen arbeitete wiederherstellen `Edit` oder `AddNew` andernfalls aufgerufen wurde, alle wertänderungen bleiben. Automatische Überprüfung ist standardmäßig aktiviert, beim Öffnen des Recordsets. Um ihn zu deaktivieren, müssen Sie angeben der **:: Nodirtyfieldcheck** in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion.  
  
 Weitere Informationen zum Aktualisieren von Daten finden Sie im Artikel [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  
  
##  <a name="canrestart"></a>  CRecordset::CanRestart  
 Bestimmt, ob das Recordset ermöglicht das Neustarten der Abfrage (um ihre Datensätze aktualisieren) durch Aufrufen der `Requery` Memberfunktion.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn Requery zulässig ist; andernfalls 0.  
  
##  <a name="canscroll"></a>  CRecordset::CanScroll  
 Bestimmt, ob das Recordset ermöglicht das Durchführen eines Bildlaufs.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Durchführen eines Bildlaufs; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Durchführen eines Bildlaufs finden Sie im Artikel [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cantransact"></a>  CRecordset::CanTransact  
 Bestimmt, ob das Recordset Transaktionen ermöglicht.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset Transaktionen zulässt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>  CRecordset::CanUpdate  
 Bestimmt, ob das Recordset aktualisiert werden kann.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset aktualisiert werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Recordset möglicherweise schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist oder wenn Sie angegeben **CRecordset:: ReadOnly** in der *OpenEx* Parameter beim Öffnen des Recordsets.  
  
##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError  
 Wird aufgerufen, zum Behandeln von Fehlern, die während des Abrufens der Datensatz generiert.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>Parameter  
 *nRetCode*  
 Rückgabecode für eine ODBC-API-Funktion. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Dieser virtuelle Memberfunktion behandelt Fehler, die auftreten, wenn Datensätze abgerufen wurden, und eignet sich während des Abrufens von Zeilen. Sie sollten überschreiben möchten `CheckRowsetError` eigene Fehlerbehandlung implementieren.  
  
 `CheckRowsetError` wird aufgerufen, automatisch in ein Navigationsvorgang Cursor, wie z. B. `Open`, `Requery`, oder eine beliebige `Move` Vorgang. Es ist den Rückgabewert der ODBC-API-Funktion übergebene **SQLExtendedFetch**. Die folgende Tabelle enthält die möglichen Werte für die `nRetCode` Parameter.  
  
|nRetCode|Beschreibung|  
|--------------|-----------------|  
|**SQL_SUCCESS**|Die Funktion wurde erfolgreich abgeschlossen. Es sind keine zusätzlichen Informationen verfügbar.|  
|**SQL_SUCCESS_WITH_INFO**|Die Funktion wurde erfolgreich abgeschlossen, möglicherweise mit einem nicht schwerwiegenden Fehler. Weitere Informationen erhalten Sie durch Aufrufen von `SQLError`.|  
|**SQL_NO_DATA_FOUND**|Alle Zeilen aus dem Resultset wurden abgerufen.|  
|**SQL_ERROR**|Fehler bei der Funktion. Weitere Informationen erhalten Sie durch Aufrufen von `SQLError`.|  
|**SQL_INVALID_HANDLE**|Fehler bei der Funktion aufgrund einer ungültigen Umgebungshandle, Verbindungshandle oder Anweisungshandle. Hiermit wird einen Programmierfehler. Keine zusätzlichen Informationen steht über `SQLError`.|  
|**SQL_STILL_EXECUTING**|Eine Funktion, die asynchron gestartet wurde, wird weiterhin ausgeführt. Beachten Sie, dass standardmäßig nie diesen Wert übergeben wird `CheckRowsetError`; MFC weiterhin aufrufen `SQLExtendedFetch` bis nicht mehr zurückgegeben **SQL_STILL_EXECUTING**.|  
  
 Weitere Informationen zu `SQLError`, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="close"></a>  CRecordset::Close  
 Schließt das Recordset.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Die ODBC **Befehls beschäftigt** und den gesamten Arbeitsspeicher, die das Framework für das Recordset zugewiesenen aufgehoben werden. In der Regel nach dem Aufruf `Close`, wenn er mit belegt wurde, löschen Sie das C++-Recordset-Objekt **neue**.  
  
 Sie können Aufrufen `Open` erneut nach dem Aufruf `Close`. Dadurch können Sie das Recordset-Objekt wiederverwenden. Die Alternative ist das Aufrufen `Requery`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>  CRecordset::CRecordset  
 Erstellt ein `CRecordset`-Objekt.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 *pDatabase*  
 Enthält einen Zeiger auf eine `CDatabase` Objekt oder den Wert **NULL**. Wenn dies nicht der **NULL** und `CDatabase` des Objekts `Open` Memberfunktion nicht aufgerufen wurde, um der Datenquelle hergestellt werden, wird das Recordset versucht wird, öffnen Sie während der eigenen `Open` aufrufen. Wenn Sie übergeben **NULL**ein `CDatabase` Objekt wird erstellt und für die Datenquelleninformationen, die Sie angegeben, wenn Sie mit ClassWizard Recordset-Klasse abgeleitet verwenden Sie verbunden sind.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder `CRecordset` direkt oder ableiten eine Klasse anwendungsspezifische `CRecordset`. Klassen-Assistent können Sie die Recordset-Klassen abgeleitet werden.  
  
> [!NOTE]
>  Eine abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CRecordset::CRecordset`, die entsprechenden Parametern zusammen an sie übergibt.  
  
 Übergeben Sie **NULL** an Ihre recordsetkonstruktor haben eine `CDatabase` Objekt erstellt und automatisch für Sie verbunden. Dies ist eine nützliche kompakteigenschaft, die keine erforderlich zum Erstellen und Verbinden einer `CDatabase` Objekt vor dem Erstellen des Recordsets.  
  
### <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
##  <a name="delete"></a>  CRecordset::Delete  
 Löscht den aktuellen Datensatz.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einem erfolgreichen Löschvorgang das Recordset-Felddatenmember werden auf einen Null-Wert festgelegt, und Sie müssen explizit aufrufen eines der `Move` Funktionen, um aus dem gelöschten Datensatz zu verschieben. Nachdem Sie aus dem gelöschten Datensatz verschieben, ist es nicht möglich, darauf zurückgeben. Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Delete` Teil einer Transaktion aufrufen. Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `Delete`. Dadurch wird ein Assertionsfehler zurückgeben. Obwohl Klasse `CRecordset` bietet einen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!CAUTION]
>  Das Recordset aktualisierbar sein muss, und es muss ein gültiger Datensatz aktuell im Recordset beim Aufrufen `Delete`ist, andernfalls ein Fehler auftritt. Angenommen, wenn Sie einen Datensatz löschen, aber kein Bildlauf zu einem neuen Datensatz vor dem Aufruf `Delete` erneut `Delete` löst eine [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Im Gegensatz zu [AddNew](#addnew) und [bearbeiten](#edit), einen Aufruf von `Delete` ist nicht gefolgt von einem Aufruf von [Update](#update). Wenn ein `Delete` Aufruf ein Fehler auftritt, die Felddaten Elemente bleiben unverändert.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt ein Recordset im Rahmen einer Funktion erstellt. Im Beispiel wird vorausgesetzt, das Vorhandensein des `m_dbCust`, eine Membervariable des Typs `CDatabase` bereits mit der Datenquelle verbunden ist.  
  
 [!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange  
 Wird aufgerufen, zum Austauschen von Datenzeilen aus der Datenquelle in das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 *pFX*  
 Ein Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird bereits dieses Objekt eingerichtet haben, geben Sie einen Kontext für das Feld Austauschvorgang durch.  
  
### <a name="remarks"></a>Hinweise  
 Wenn gesammelte implementiert ist, ruft das Framework diese Memberfunktion zum Übertragen von Daten automatisch aus der Datenquelle für Ihr Recordsetobjekt. `DoBulkFieldExchange` Außerdem bindet Ihre Parameterdatenmember ggf. Parameterplatzhalter in der SQL-Anweisungszeichenfolge für die Auswahl des Recordsets.  
  
 Wenn Abrufens von Zeilen nicht implementiert wird, das Framework ruft [DoFieldExchange](#dofieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` -Option von der `dwOptions` Parameter in der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
> `DoBulkFieldExchange` ist nur verfügbar, wenn Sie von einer abgeleiteten Klasse mithilfe `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, rufen Sie die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.  
  
 Massen-Datensatzfeldaustausch (Bulk-RFX) ähnelt Datensatzfeldaustausch (RFX). Daten werden automatisch auf das Recordsetobjekt aus der Datenquelle übertragen. Allerdings können Sie nicht aufrufen `AddNew`, `Edit`, `Delete`, oder `Update` Änderungen zurück an die Datenquelle übertragen. Klasse `CRecordset` derzeit bietet einen Mechanismus zum Aktualisieren von Datenzeilen; Sie können allerdings Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**.  
  
 Beachten Sie, dass Massen-Datensatzfeldaustausch von ClassWizard nicht unterstützt wird; aus diesem Grund müssen Sie überschreiben `DoBulkFieldExchange` manuell durch Aufrufe der Bulk-RFX-Funktionen zu schreiben. Weitere Informationen zu diesen Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).  
  
 Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="dofieldexchange"></a>  CRecordset:: DoFieldExchange  
 Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 *pFX*  
 Ein Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird bereits dieses Objekt eingerichtet haben, geben Sie einen Kontext für das Feld Austauschvorgang durch.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Abrufens von Zeilen nicht implementiert ist, ruft das Framework diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern eines Recordset-Objekt und den entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch an. `DoFieldExchange` Außerdem bindet Ihre Parameterdatenmember ggf. Parameterplatzhalter in der SQL-Anweisungszeichenfolge für die Auswahl des Recordsets.  
  
 Gesammelte implementiert ist, wird das Framework ruft [DoBulkFieldExchange](#dobulkfieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` -Option von der *OpenEx* Parameter in der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
> `DoFieldExchange` ist nur verfügbar, wenn Sie von einer abgeleiteten Klasse mithilfe `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, rufen Sie die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.  
  
 Der Austausch von Felddaten, Datensatzfeldaustausch (RFX), aufgerufen funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes für die Datenquelle und aus dem Datensatz in der Datenquelle auf das Recordsetobjekt.  
  
 Die einzige Aktion, die Sie ergreifen müssen normalerweise implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse zum Erstellen einer Klasse mit dem Klassen-Assistenten, und geben Sie den Namen und Datentypen von den Felddatenmembern ist. Sie können auch Code hinzufügen, in was ClassWizard geschrieben, um Parameterdatenmember anzugeben oder für den Umgang mit Spalten, die Sie dynamisch binden. Weitere Informationen finden Sie im Artikel [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Wenn Sie mit ClassWizard abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` , die im folgende Beispiel ähnelt:  
  
 [!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 Weitere Informationen über RFX-Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).  
  
 Weitere Beispiele und Informationen zu `DoFieldExchange`, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Allgemeine Informationen über RFX finden Sie im Artikel [Datensatzfeldaustausch](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="edit"></a>  CRecordset::Edit  
 Ermöglicht Änderungen an den aktuellen Datensatz.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf `Edit`, Sie können die Felddatenmembern ändern, indem Sie deren Werte direkt zurücksetzen. Der Vorgang abgeschlossen ist, wenn anschließend Sie rufen die [Update](#update) Memberfunktion, um die Änderungen für die Datenquelle zu speichern.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `Edit`. Dadurch wird ein Assertionsfehler zurückgeben. Obwohl Klasse `CRecordset` bietet einen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `Edit` Speichert die Werte der Datenelemente für das Recordset. Beim Aufrufen `Edit`, nehmen Änderungen vor, und rufen dann `Edit` erneut, die Werte des Datensatzes werden wiederhergestellt, was sie vor dem ersten wären `Edit` aufrufen.  
  
 In einigen Fällen empfiehlt es sich um eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Zu diesem Zweck rufen [SetFieldNull](#setfieldnull) mit einem Parameter des **"true"** , markieren Sie das Feld Null; Dies bewirkt auch, dass die Spalte aktualisiert werden. Wenn Sie wünschen, dass ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert hat, rufen Sie [SetFieldDirty](#setfielddirty) mit einem Parameter des **"true"**. Dies funktioniert auch, wenn das Feld den Wert Null war.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Edit` Teil einer Transaktion aufrufen. Beachten Sie, die Sie aufrufen sollte [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf `Edit` und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) ist kein Ersatz für den Aufruf von `Update` zum Abschließen der `Edit` Vorgang. Weitere Informationen über Transaktionen finden Sie in der Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Abhängig von der aktuellen Sperrverhalten der aktualisierten Datensatz gelesen von gesperrt werden `Edit` bis zum Aufruf von `Update` oder beim Bildlauf mit einem anderen Datensatz oder er kann gesperrt werden, nur während der `Edit` aufrufen. Sie können ändern, dass der Sperrmodus mit [SetLockingMode](#setlockingmode).  
  
 Der vorherige Wert des aktuellen Datensatzes wird wiederhergestellt, wenn Sie einen Bildlauf zu einem neuen Datensatz vor dem Aufruf durchführen `Update`. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen `Edit` für ein Recordset, das nicht aktualisiert werden kann oder wenn kein aktueller Datensatz vorhanden ist.  
  
 Weitere Informationen finden Sie in den Artikeln [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md) und [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>  CRecordset::FlushResultSet  
 Ruft das nächste Resultset einer vordefinierten Abfrage (gespeicherten Prozedur) ab, wenn mehrere Resultsets vorhanden sind.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es sind mehrere Resultsets abgerufen werden sollen; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `FlushResultSet` nur wenn Sie mit dem Cursor auf das aktuelle Resultset vollständig abgeschlossen sind. Beachten Sie, dass, wenn Sie das nächste Resultset, der durch den Aufruf abrufen `FlushResultSet`, der Cursor gilt nicht für dieses Resultset; Sie sollten aufrufen, die [MoveNext](#movenext) Memberfunktion nach dem Aufruf `FlushResultSet`.  
  
 Wenn eine vordefinierte Abfrage ein Output-Parameter oder Eingabe-/Ausgabeparameter verwendet, müssen Sie aufrufen `FlushResultSet` bis zurückgegeben `FALSE` (der Wert 0), um diese Parameterwerte abzurufen.  
  
 `FlushResultSet` Ruft die ODBC-API-Funktion `SQLMoreResults`. Wenn `SQLMoreResults` gibt `SQL_ERROR` oder `SQL_INVALID_HANDLE`, klicken Sie dann `FlushResultSet` wird eine Ausnahme ausgelöst. Weitere Informationen zu `SQLMoreResults`, finden Sie im Windows SDK.  
  
 Die gespeicherte Prozedur muss Felder gebunden haben, wenn Sie aufrufen möchten `FlushResultSet`.  
  
### <a name="example"></a>Beispiel  
 Der folgende Code setzt voraus, dass `COutParamRecordset` ist eine `CRecordset`-abgeleitete Objekt basierend auf einer vordefinierten Abfrage mit einem Eingabeparameter und ein Output-Parameter, und dass mehrere Resultsets. Beachten Sie die Struktur der [DoFieldExchange](#dofieldexchange) außer Kraft setzen.  
  
 [!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>  CRecordset::GetBookmark  
 Ruft den Lesezeichenwert für den aktuellen Datensatz ab.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 *varBookmark*  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) Objekt, das das Lesezeichen im aktuellen Datensatz darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Um festzustellen, ob Lesezeichen, auf das Recordset unterstützt werden, rufen [CanBookmark](#canbookmark). Um Lesezeichen verfügbar zu machen, wenn sie unterstützt werden, müssen Sie festlegen der **CRecordset:: useBookmarks** -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
>  Wenn das Lesezeichen nicht unterstützte oder nicht verfügbar sind, beim Aufrufen `GetBookmark` führt dazu, eine Ausnahme ausgelöst. Lesezeichen werden nicht auf die Forward-only-Recordsets unterstützt.  
  
 `GetBookmark` weist den Wert des Lesezeichens für den aktuellen Datensatz auf eine `CDBVariant` Objekt. An diesen Datensatz zu einem beliebigen Zeitpunkt nach dem Verschieben zu einem anderen Datensatz rufen Sie zum Zurückgeben [SetBookmark](#setbookmark) mit dem entsprechenden `CDBVariant` Objekt.  
  
> [!NOTE]
>  Nach bestimmten Vorgängen Recordset Lesezeichen möglicherweise nicht mehr gültig. Angenommen, Sie rufen `GetBookmark` gefolgt von `Requery`, Sie können möglicherweise nicht zurück auf den Datensatz mit `SetBookmark`. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="getdefaultconnect"></a>  GetDefaultConnect  
 Wird aufgerufen, um die Standardverbindungszeichenfolge zu erhalten.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , enthält die Standard-Verbindungszeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Memberfunktion, um die Standardverbindungszeichenfolge für die Datenquelle zu erhalten, auf dem sich die Datensatzgruppe basiert. Klassen-Assistent implementiert diese Funktion für Sie identifiziert die gleiche Datenquelle, die Sie zum Abrufen von Informationen zu Tabellen und Spalten im Klassen-Assistenten verwenden. Wahrscheinlich werden finden Sie es praktisch sein, diese standardverbindung beim Entwickeln Ihrer Anwendung abhängig. Aber die standardverbindung kann nicht für Benutzer der Anwendung geeignet sein. Wenn dies der Fall ist, sollten Sie diese Funktion implementieren, Verwerfen ClassWizards-Version. Weitere Informationen zu Verbindungszeichenfolgen finden Sie im Artikel [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md).  
  
##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL  
 Wird aufgerufen, um die Standard-SQL-Zeichenfolge auszuführende abzurufen.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , die die Standard-SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Memberfunktion, um die Standard-SQL-Anweisung zu erhalten, auf der sich die Datensatzgruppe basiert. Dies ist möglicherweise ein Tabellenname oder ein SQL **wählen** Anweisung.  
  
 Sie definieren die Standard-SQL-Anweisung indirekt durch Deklarieren des Recordset-Klasse mit ClassWizard und ClassWizard diese Aufgabe für Sie ausführt.  
  
 Wenn Sie die Zeichenfolge der SQL-Anweisung für Ihre eigenen Zwecke benötigen, rufen Sie `GetSQL`, womit die SQL-Anweisung verwendet, um das Recordset Datensätze auszuwählen, wenn es geöffnet wurde. Sie können die Standard-SQL-Zeichenfolge in der Klasse: f Überschreibung von bearbeiten `GetDefaultSQL`. Beispielsweise können Sie angeben, einen Aufruf einer vordefinierten Abfrage mit einem **Aufrufen** Anweisung. (Beachten Sie, dass, auch wenn Sie jedoch bearbeiten `GetDefaultSQL`, müssen Sie auch ändern `m_nFields` mit der Anzahl der Spalten in der Datenquelle übereinstimmen.)  
  
 Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
> [!CAUTION]
>  Der Tabellenname ist leer, wenn das Framework einen Tabellennamen ein, wenn mehrere Tabellennamen angegeben wurden, oder wenn nicht identifizieren einer **Aufrufen** Anweisung konnte nicht interpretiert werden. Beachten Sie, dass bei Verwendung einer **Aufrufen** -Anweisung darf kein Leerzeichen zwischen der geschweiften Klammer eingefügt und die **Aufrufen** -Schlüsselwort, noch sollte Sie Leerzeichen vor der geschweiften Klammer oder vor dem Einfügen der  **Wählen Sie** -Schlüsselwort in einer **wählen** Anweisung.  
  
##  <a name="getfieldvalue"></a>  CRecordset:: GetFieldValue  
 Ruft die Felddaten im aktuellen Datensatz ab.  
  
```  
void GetFieldValue(
    LPCTSTR lpszName,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CStringA& strValue);

 
void GetFieldValue(
    short nIndex,  
    CStringW& strValue);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name eines Felds.  
  
 *VarValu*e  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) -Objekt, das der Wert des Felds gespeichert werden.  
  
 *nFieldType*  
 Der ODBC C-Datentyp des Felds. Mit dem Standardwert **DEFAULT_FIELD_TYPE**, erzwingt `GetFieldValue` zum Ermitteln des Datentyps "C" aus dem SQL-Datentyp, basierend auf der folgenden Tabelle. Andernfalls können Sie angeben, die Daten direkt eingeben, oder wählen Sie einen kompatiblen Datentyp; Sie können z. B. einen beliebigen Datentyp aufweisen, in speichern **SQL_C_CHAR**.  
  
|C-Datentyp|SQL-Datentyp|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 Weitere Informationen zu ODBC-Datentypen finden Sie unter den Themen "SQL-Datentypen" und "C-Datentypen" in Anhang D des Windows SDK.  
  
 *nIndex*  
 Der nullbasierte Index des Felds.  
  
 *StrValue*  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das der Wert des Felds zu speichern, wird in Text konvertiert, unabhängig von der Datentyp des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Feld nach Name oder Index nachzuschlagen. Sie können den Wert des Felds speichern, entweder in eine `CDBVariant` Objekt oder ein `CString` Objekt.  
  
 Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, wird der aktuelle Datensatz immer auf dem ersten Datensatz in einem Rowset positioniert. Mit `GetFieldValue` auf einen Datensatz in ein angegebenes Rowset, müssen Sie zuerst Aufrufen der [SetRowsetCursorPosition](#setrowsetcursorposition) Memberfunktion so verschieben Sie den Cursor auf die gewünschte Zeile innerhalb dieses Rowset besitzt. Rufen Sie anschließend `GetFieldValue` für diese Zeile. Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` -Option von der *OpenEx* Parameter in der [öffnen](#open) Memberfunktion.  
  
 Sie können `GetFieldValue` Felder zur Entwurfszeit statisch Bindung, statt zur Laufzeit dynamisch abgerufen. Angenommen, Sie direkt aus einem Recordset-Objekt deklariert haben `CRecordset`, verwenden Sie `GetFieldValue` zum Abrufen der Felddaten; die Datensatzfeldaustausch (RFX) oder den Massen-Datensatzfeldaustausch (Bulk-RFX) ist nicht implementiert.  
  
> [!NOTE]
>  Wenn Sie einem Recordset-Objekt deklarieren, ohne eine Ableitung von `CRecordset`, verfügen nicht über die ODBC-Cursorbibliothek geladen. Die Cursorbibliothek erfordert, dass das Recordset muss mindestens eine gebundene Spalte verfügen. Wenn Sie jedoch verwenden `CRecordset` direkt, keine der Spalten gebunden sind. Die Memberfunktionen [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) und [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) steuern, ob die Cursorbibliothek geladen werden.  
  
 `GetFieldValue` Ruft die ODBC-API-Funktion **SQLGetData**. Wenn der Treiber den Wert ausgibt **SQL_NO_TOTAL** für die tatsächliche Länge des Feldwerts, `GetFieldValue` löst eine Ausnahme aus. Weitere Informationen zu **SQLGetData**, finden Sie im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 Der folgende Beispielcode veranschaulicht Aufrufe `GetFieldValue` für direkt aus einem Recordset-Objekt deklariert `CRecordset`.  
  
 [!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  Im Gegensatz zu den DAO-Klasse `CDaoRecordset`, `CRecordset` verfügt nicht über eine `SetFieldValue` Memberfunktion. Wenn Sie ein Objekt direkt vom Erstellen `CRecordset`, er ist effektiv schreibgeschützt.  
  
 Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount  
 Ruft die Gesamtzahl der Felder im Recordset-Objekts ab.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen von Recordsets, finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo  
 Ruft Informationen zu den Feldern im Recordset ab.  
  
```  
void GetODBCFieldInfo(
    LPCTSTR lpszName,  
    CODBCFieldInfo& fieldinfo);

 
void GetODBCFieldInfo(
    short nIndex,  
    CODBCFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Parameter  
 *Wert*  
 Der Name eines Felds.  
  
 *FieldInfo*  
 Ein Verweis auf eine `CODBCFieldInfo` Struktur.  
  
 *nIndex*  
 Der nullbasierte Index des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld nach Namen suchen. Die andere Version können Sie ein Feld über einen Index zu suchen.  
  
 Eine Beschreibung zu den Informationen zurückgegeben werden, finden Sie unter der [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) Struktur.  
  
 Weitere Informationen zum Erstellen von Recordsets, finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount  
 Bestimmt die Größe des Recordsets.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Datensätze im Recordset; 0, wenn das Recordset keine Datensätze enthält; oder -1, wenn die Anzahl der Datensätze bestimmt werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Die Anzahl der Datensätze wird als eine "obere Grenze," der höchsten nummerierten Datensatz beibehalten noch sichtbar, wenn der Benutzer durch die Datensätze bewegt. Die Gesamtanzahl von Datensätzen wird nur bezeichnet werden, nachdem der Benutzer hinter dem letzten Datensatz gewechselt hat. Aus Gründen der Leistung die Anzahl die nicht aktualisiert, beim Aufrufen von `MoveLast`. Aufrufen, um die Datensätze selbst zu zählen, `MoveNext` solange wiederholt, bis `IsEOF` ungleich NULL zurückgegeben. Hinzufügen eines Datensatzes über `CRecordset:AddNew` und `Update` erhöht die Anzahl; das Löschen eines Datensatzes über `CRecordset::Delete` verringert die Anzahl.  
  
##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize  
 Ruft die aktuelle Einstellung für die Anzahl der Zeilen, die Sie während einer bestimmten Fetch abrufen möchten.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen, die während einer bestimmten Fetch abgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie gesammelte verwenden, ist die Standardgröße des Rowsets beim Öffnen des Recordsets 25; Andernfalls ist der Wert 1.  
  
 Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion. Rufen Sie zum Ändern der Einstellung für die Rowsetgröße [SetRowsetSize](#setrowsetsize).  
  
 Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched  
 Bestimmt, wie viele Datensätze tatsächlich nach einem Abrufvorgang abgerufen wurden.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen, die aus der Datenquelle einem Abrufvorgang abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist hilfreich, wenn Sie massenzeilenabruf implementiert haben. Die Rowsetgröße gibt normalerweise an, wie viele Zeilen aus einem Abrufvorgang abgerufen werden. Allerdings wirkt sich auf die Gesamtanzahl der Zeilen im Recordset auch, wie viele Zeilen in einem Rowset abgerufen werden sollen. Z. B. wenn Recordset 10 Datensätze mit 4-Einstellung Rowset Größe verfügt, klicken Sie dann Schleifendurchlauf durch das Recordset durch Aufrufen von `MoveNext` im endgültigen Rowset mit Datensätzen nur 2 führt.  
  
 Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion. Rufen Sie zum Angeben der Rowsetgröße [SetRowsetSize](#setrowsetsize).  
  
 Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus  
 Der Status für eine Zeile im aktuellen Rowset abgerufen.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *wRow*  
 Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Statuswert für die Zeile. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 `GetRowStatus` ein Wert, der angibt, entweder alle Änderung im Status der Zeile dass seit dem letzten abgerufen, von der Datenquelle, oder gibt keine Zeile entspricht *wRow* abgerufen wurde. In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:  
  
|Statuswert|Beschreibung|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|Die Zeile unverändert.|  
|`SQL_ROW_UPDATED`|Die Zeile wurde aktualisiert.|  
|`SQL_ROW_DELETED`|Die Zeile wurde gelöscht.|  
|`SQL_ROW_ADDED`|Die Zeile wurde hinzugefügt.|  
|`SQL_ROW_ERROR`|Die Zeile ist aufgrund eines Fehlers nicht abrufbar.|  
|`SQL_ROW_NOROW`|Es gibt keine Zeile, die entspricht *wRow*.|  
  
 Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLExtendedFetch** im Windows SDK.  
  
##  <a name="getstatus"></a>  CRecordset::GetStatus  
 Bestimmt den Index des aktuellen Datensatzes in das Recordset und gibt an, ob der letzte Datensatz verarbeitet wurde.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>Parameter  
 *rStatus*  
 Ein Verweis auf eine **CRecordsetStatus** Objekt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="remarks"></a>Hinweise  
 `CRecordset` versucht, verfolgen den Index jedoch unter bestimmten Umständen dies u. u. nicht möglich. Finden Sie unter [GetRecordCount](#getrecordcount) eine Erklärung.  
  
 Die **CRecordsetStatus** Struktur weist folgende Form:  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 Die zwei Member des **CRecordsetStatus** haben folgende Bedeutung:  
  
- **M_lCurrentRecord** enthält den nullbasierten Index des aktuellen Datensatzes im Recordset, sofern bekannt. Wenn der Index nicht bestimmt werden kann, enthält dieser Member **AFX_CURRENT_RECORD_UNDEFINED** (-2). Wenn `IsBOF` ist **"true"** (Recordset leer, oder versuchen, die vor dem ersten Datensatz einen Bildlauf), klicken Sie dann **M_lCurrentRecord** festgelegt ist, um **AFX_CURRENT_RECORD_BOF** (-1). Zweitens auf des ersten Datensatzes, klicken sie auf 0 festgelegt ist, zeichnen Sie 1, und so weiter festgelegt.  
  
- **M_bRecordCountFinal** Nonzero, wenn die Gesamtzahl der Datensätze im Recordset ermittelt wurde. Dies muss im Allgemeinen erreicht werden, wobei am Anfang des Recordsets und Aufrufen von `MoveNext` bis `IsEOF` ungleich NULL zurückgegeben. Wenn dieser Member 0 (null) ist, der Datensatz zählen zurückgegebene `GetRecordCount`, sofern nicht-1 ist, ist nur eine "obere Grenze" Anzahl der Datensätze.  
  
##  <a name="getsql"></a>  CRecordset::GetSQL  
 Rufen Sie diese Memberfunktion, um die SQL-Anweisung zu erhalten, die verwendet wurde, zum Auswählen von Datensätzen für das Recordset, wenn es geöffnet wurde.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** einen Verweis auf eine `CString` , die die SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist im Allgemeinen wird eine SQL **wählen** Anweisung. Die zurückgegebene Zeichenfolge `GetSQL` ist schreibgeschützt.  
  
 Die zurückgegebene Zeichenfolge `GetSQL` unterscheidet sich in der Regel eine beliebige Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die *LpszSQL* Parameter an die `Open` Memberfunktion. Dies ist, da das Recordset eine vollständige SQL­Anweisung anhand der erstellt an übergebene `Open`, angegebene Klassen-Assistent, was Sie angegeben haben möglicherweise die **M_strFilter** und `m_strSort` Datenmember und alle Parameter, mit denen, die Sie möglicherweise angegeben haben. Details wie das Recordset für diese SQL-Anweisung erstellt finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf [öffnen](#open).  
  
##  <a name="gettablename"></a>  CRecordset::GetTableName  
 Ruft den Namen der SQL-Tabelle, die auf der die Abfrage des Recordsets basiert.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** einen Verweis auf eine `CString` , die die Tabelle enthält name, wenn das Recordset ist, basierend auf einer Tabelle ist, andernfalls eine leere Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 `GetTableName` ist nur gültig, wenn das Recordset für eine Tabelle, die keine Verknüpfung von mehreren Tabellen oder eine vordefinierte Abfrage (gespeicherten Prozedur) basiert. Der Name ist schreibgeschützt.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf [öffnen](#open).  
  
##  <a name="isbof"></a>  CRecordset::IsBOF  
 Gibt ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es ist kein aktueller Datensatz vorhanden.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält oder wenn Sie kein Bildlauf rückwärts vor dem ersten Datensatz durchgeführt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf aus Datensatz zu Datensatz zur Feststellung, ob Sie vor dem ersten Datensatz des Recordsets überschritten haben. Sie können auch `IsBOF` zusammen mit `IsEOF` zu bestimmen, ob das Recordset alle Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf `Open`, wenn das Recordset keine Datensätze enthält `IsBOF` ungleich NULL zurückgegeben. Wenn Sie ein Recordset, die über mindestens ein Datensatz öffnen, der erste Datensatz zum aktuellen Datensatz ist und `IsBOF` gibt 0 zurück.  
  
 Wenn der erste Datensatz zum aktuellen Datensatz und Sie rufen `MovePrev`, `IsBOF` anschließend ungleich NULL zurück. Wenn `IsBOF` zurück, die ungleich NULL ist und Sie rufen `MovePrev`, ein Fehler auftritt. Wenn `IsBOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert führt zu einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `IsBOF` und `IsEOF` um die Grenzwerte eines Recordsets zu erkennen, wie der Code ein Bildlauf durch das Recordset in beide Richtungen durchgeführt.  
  
 [!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>  CRecordset::IsDeleted  
 Bestimmt, ob der aktuelle Datensatz gelöscht wurde.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset, auf einen gelöschten Datensatz positioniert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen zu einem Datensatz Bildlauf und `IsDeleted` gibt **"true"** (ungleich null), klicken Sie dann Sie müssen einen Bildlauf zu einem anderen Datensatz, bevor Sie andere Recordset-Vorgänge ausführen können.  
  
 Das Ergebnis des `IsDeleted` hängt von vielen Faktoren ab, z. B. Ihr Recordsettyp, ob das Recordset aktualisierbar ist, ist, ob Sie angegeben haben die **CRecordset:: Skipdeletedrecords** option, wenn Sie das Recordset geöffnet haben, ob Ihre Treiber Packs gelöschten Datensätzen, und ob mehrere Benutzer vorhanden sind.  
  
 Weitere Informationen zu **CRecordset:: Skipdeletedrecords** und Treiber packen, finden Sie unter der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie nicht `IsDeleted`. Rufen Sie stattdessen die [GetRowStatus](#getrowstatus) Memberfunktion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="iseof"></a>  CRecordset::IsEOF  
 Gibt einen Wert ungleich NULL, wenn das Recordset hinter dem letzten Datensatz positioniert wurde wurde zurück. Es ist kein aktueller Datensatz vorhanden.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält oder wenn Sie hinter dem letzten Datensatz gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, wie Sie einen Bildlauf aus Datensatz zu Datensatz zur Feststellung, ob Sie den letzten Datensatz des Recordsets überschritten haben. Sie können auch `IsEOF` zu bestimmen, ob das Recordset alle Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf `Open`, wenn das Recordset keine Datensätze enthält `IsEOF` ungleich NULL zurückgegeben. Wenn Sie ein Recordset, die über mindestens ein Datensatz öffnen, der erste Datensatz zum aktuellen Datensatz ist und `IsEOF` gibt 0 zurück.  
  
 Wenn der letzte Datensatz zum aktuellen Datensatz beim Aufrufen ist `MoveNext`, `IsEOF` anschließend ungleich NULL zurück. Wenn `IsEOF` zurück, die ungleich NULL ist und Sie rufen `MoveNext`, ein Fehler auftritt. Wenn `IsEOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert führt zu einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty  
 Bestimmt, ob das angegebene felddatenelement seit geändert wurde [bearbeiten](#edit) oder [AddNew](#addnew) aufgerufen wurde.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 *PV*  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das angegebene felddatenelement, seit dem Aufrufen geändert hat `AddNew` oder `Edit`, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten in alle Felddatenmember übertragen werden sollen den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der [Update](#update) Memberfunktion von `CRecordset` (nach einem Aufruf `Edit` oder `AddNew`).  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht anwendbar auf Recordsets, die gesammelte verwenden. Gesammelte, klicken Sie dann implementiert, `IsFieldDirty` gibt stets **"false"** und führt zu einem fehlgeschlagenen Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Aufrufen von `IsFieldDirty` wird zurückgesetzt, die Auswirkungen von vorangehenden Aufrufe [SetFieldDirty](#setfielddirty) seit der geänderten Status des Felds neu ausgewertet wird. In der `AddNew` Fall, wenn der aktuelle Wert des Felds aus dem Pseudo-null-Wert unterscheidet sich das Feldstatus festgelegt ist fehlerhaft. In der `Edit` Groß-/Kleinschreibung, wenn der Wert des Felds aus den zwischengespeicherten Wert unterscheidet, und klicken Sie dann die Feldstatus dirty festgelegt ist.  
  
 `IsFieldDirty` wird durch implementiert [DoFieldExchange](#dofieldexchange).  
  
 Weitere Informationen zu den Änderungsflag, finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull  
 Gibt ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz Null ist (kein Wert hat).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 *PV*  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene felddatenelement als Null gekennzeichnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Felddatenmember eines Recordsets als Null gekennzeichnet wurde. (In der datenbankterminologie von-Null bedeutet "kein Wert having" und entspricht nicht dem als **NULL** in C++.) Wenn ein Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte des aktuellen Datensatzes interpretiert kein Wert vorhanden ist.  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht anwendbar auf Recordsets, die gesammelte verwenden. Gesammelte, klicken Sie dann implementiert, `IsFieldNull` gibt stets **"false"** und führt zu einem fehlgeschlagenen Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `IsFieldNull` wird durch implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable  
 Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz auf Null festgelegt werden kann (mit keinen Wert) zurück.  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 *PV*  
 Ein Zeiger auf das felddatenelement, dessen Status Sie überprüfen möchten, oder **NULL** zu bestimmen, ob eines der Felder auf einen Null-Wert festgelegt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Feld-Datenelement "NULL-Werte zulassen" ist (können auf einen Null-Wert festgelegt werden C++ **NULL** entspricht nicht dem als Null, was die in der Terminologie von Datenbanken bedeutet "kein Wert having").  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `IsFieldNullable`. Rufen Sie stattdessen die [GetODBCFieldInfo](#getodbcfieldinfo) Member-Funktion, um zu bestimmen, ob ein Feld auf einen Null-Wert festgelegt werden kann. Beachten Sie, die Sie, immer aufrufen können `GetODBCFieldInfo`, unabhängig davon, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, ein solches Feld auf Null, die beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und [aktualisieren](#update) wird eine Ausnahme ausgelöst. Die Ausnahme tritt auf, wenn Sie aufrufen `Update`, nicht beim Aufrufen von [SetFieldNull](#setfieldnull).  
  
 Mit **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder, nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder sind nicht betroffen.  
  
 Auf **Param** Felder, geben Sie an die tatsächliche Adresse der Person **Param** auf, wie z. B. zusammenarbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, dass Sie nicht alle festlegen **Param** Felder **NULL**, wie Sie mit **OutputColumn** Felder.  
  
 `IsFieldNullable` wird durch implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isopen"></a>  CRecordset::IsOpen  
 Bestimmt, ob das Recordset bereits geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich Null des Recordset-Objekts [öffnen](#open) oder [Requery](#requery) Memberfunktion zuvor aufgerufen wurde und das Recordset nicht geschlossen wurde; andernfalls 0.  
  
##  <a name="m_hstmt"></a>  M_hstmt  
 Enthält ein Handle für die ODBC-Anweisung-Datenstruktur des Typs **Befehls beschäftigt**, das Recordset zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Jede Abfrage mit einer ODBC-Datenquelle zugeordnet ist ein **Befehls beschäftigt**.  
  
> [!CAUTION]
>  Verwenden Sie keine **M_hstmt** vor [öffnen](#open) aufgerufen wurde.  
  
 Normalerweise Sie müssen nicht den Zugriff auf die **Befehls beschäftigt** direkt, aber Sie können ihn benötigen, für die direkte Ausführung von SQL-Anweisungen. Die `ExecuteSQL` Memberfunktion der Klasse `CDatabase` enthält ein Beispiel der Verwendung von **M_hstmt**.  
  
##  <a name="m_nfields"></a>  CRecordset::m_nFields  
 Enthält die Anzahl der Felddatenmember der Recordset-Klasse. d. h. die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor für das Recordset-Klasse muss initialisiert werden `m_nFields` mit der korrekten Anzahl. Wenn Sie nicht gesammelte implementiert haben, schreibt ClassWizard diese Initialisierung für Sie aus, wenn Sie es verwenden, um die Recordset-Klasse deklarieren. Sie können Sie auch manuell erstellen.  
  
 Das Framework verwendet diese Zahl zum Verwalten der Interaktion zwischen den Felddatenmembern und den entsprechenden Spalten des aktuellen Datensatzes für die Datenquelle an.  
  
> [!CAUTION]
>  Diese Zahl muss entsprechen, die Spaltenanzahl "Ausgabe" in registriert `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit dem Parameter **CFieldExchange::outputColumn**.  
  
 Sie können Spalten dynamisch, wie im Artikel erläutert binden "Recordset: dynamisch binden von Datenspalten." Wenn Sie dies tun, müssen Sie die Anzahl die in der erhöhen `m_nFields` entsprechend der Anzahl der RFX- oder der Bulk-RFX-Funktion aufruft, Ihrem `DoFieldExchange` oder `DoBulkFieldExchange` Memberfunktion für die dynamisch gebundenen Spalten.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_nparams"></a>  CRecordset::m_nParams  
 Enthält die Anzahl der Parameterdatenmember in der Recordsetklasse. übergeben die Anzahl von Parametern, also durch das Recordset-Abfrage.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Recordset-Klasse Parameterdatenmember verfügt, muss der Konstruktor für die Klasse initialisieren `m_nParams` mit der korrekten Anzahl. Der Wert des `m_nParams` hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen (die Sie manuell ausführen müssen), müssen Sie eine Initialisierung auch manuell hinzufügen, im Klassenkonstruktor entsprechend die Anzahl von Parametern (die muss mindestens so groß wie die Anzahl der "Platzhalter in Ihre **M_strFilter**  oder `m_strSort` Zeichenfolge).  
  
 Das Framework verwendet diese Zahl an, wenn sie das Recordset-Abfrage parametrisiert.  
  
> [!CAUTION]
>  Diese Zahl muss entsprechen, die Anzahl der "Params" im registriert `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit einem Parameterwert von **CFieldExchange::inputParam**,  **CFieldExchange::param**, **CFieldExchange::outputParam**, oder **CFieldExchange::inoutParam**.  
  
### <a name="example"></a>Beispiel  
  Finden Sie in den Artikeln [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) und [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase  
 Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable wird auf zwei Arten festgelegt. In der Regel, übergeben Sie einen Zeiger an einem bereits verbundenen `CDatabase` Objekt, wenn Sie das Recordset-Objekt erstellen. Wenn Sie übergeben **NULL** stattdessen `CRecordset` erstellt eine `CDatabase` -Objekt für Sie und verbindet ihn. In beiden Fällen `CRecordset` den Zeiger in dieser Variable gespeichert.  
  
 Normalerweise Sie nicht direkt benötigen, verwenden Sie den Zeiger in gespeicherten **M_pDatabase**. Wenn Sie eine eigene Erweiterungen geschrieben werden sollen `CRecordset`, allerdings müssen Sie den Zeiger zu verwenden. Beispielsweise benötigen Sie möglicherweise den Zeiger Wenn Sie lösen eigene `CDBException`s. Oder Sie möglicherweise benötigt, wenn Sie eine Aktion mit dem gleichen müssen `CDatabase` Objekt, z. B. Transaktionen, Festlegen von Timeouts, ausgeführt oder zum Aufrufen der `ExecuteSQL` Memberfunktion der Klasse `CDatabase` SQL-Anweisungen direkt ausführen.  
  
##  <a name="m_strfilter"></a>  CRecordset:: M_strfilter  
 Nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf seiner `Open` Member funktionieren, verwenden Sie dieses Datenelement zum Speichern einer `CString` mit einer SQL **, in denen** Klausel.  
  
### <a name="remarks"></a>Hinweise  
 Das Recordset verwendet diese Zeichenfolge einzuschränken (oder Filtern) Datensätze ausgewählt wird, während die `Open` oder `Requery` aufrufen. Dies ist nützlich für die Auswahl einer Teilmenge von Datensätzen, z. B. "alle Vertriebsmitarbeiter in Kalifornien basierend" ("State = CA"). Die ODBC-SQL-Syntax für eine **, in dem** -Klausel  
  
 `WHERE search-condition`  
  
 Beachten Sie, die Sie nicht einschließen, die **, in dem** Schlüsselwort in der Zeichenfolge. Das Framework bereitgestellt.  
  
 Sie können auch der Filterzeichenfolge parametrisieren, indem platzieren '' Platzhalter, deklarieren einen Parameter-Datenmember in der Klasse für jeden Platzhalter und übergeben von Parametern an das Recordset zur Laufzeit. Dadurch können Sie den Filter zur Laufzeit zu erstellen. Weitere Informationen finden Sie im Artikel [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Weitere Informationen zu SQL **, in denen** -Klausel finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum auswählen und Filtern von Datensätzen finden Sie im Artikel [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>  CRecordset::m_strSort  
 Nach dem Erstellen des Recordsetobjekts, aber vor dem Aufrufen der `Open` Member funktionieren, verwenden Sie zum Speichern dieses Datenelement eine `CString` mit einer SQL **ORDER BY** Klausel.  
  
### <a name="remarks"></a>Hinweise  
 Das Recordset verwendet diese Zeichenfolge, um die Datensätze zu sortieren, er wählt den während, der `Open` oder `Requery` aufrufen. Sie können diese Funktion verwenden, um einem Recordset auf einer oder mehreren Spalten sortieren. Die ODBC-SQL-Syntax für eine **ORDER BY** -Klausel  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 dabei eine Sortierung eine ganze Zahl oder ein Spaltenname ist. Sie können auch die aufsteigende oder absteigende Reihenfolge (Standardmäßig ist die Reihenfolge aufsteigend) angeben, durch Anfügen von "ASC" oder "DESC" auf der Liste der Spalten in der Sortierzeichenfolge. Die ausgewählten Datensätze werden zunächst nach der ersten Spalte aufgeführt und dann durch den zweiten usw. sortiert. Beispielsweise können Sie ein Recordset "Customers" nach Nachnamen und Vornamen dann sortieren. Die Anzahl der Spalten, die Sie auflisten können, hängt von der Datenquelle ab. Weitere Informationen finden Sie im Windows-SDK.  
  
 Beachten Sie, die Sie nicht einschließen, die **ORDER BY** Schlüsselwort in der Zeichenfolge. Das Framework bereitgestellt.  
  
 Weitere Informationen zu SQL-Klauseln, finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum Sortieren von Datensätzen finden Sie im Artikel [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>  CRecordset  
 Verschiebt den Zeiger für den aktuellen Datensatz im Recordset, entweder vorwärts oder rückwärts ausgeführt.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>Parameter  
 *nRows*  
 Die Anzahl der Zeilen vorwärts oder rückwärts bewegen. Positive Werte vorwärts, am Ende des Recordsets. Negative Werte rückwärts, an den Anfang.  
  
 *wFetchType*  
 Bestimmt das Schemarowset, `Move` abgerufen wird. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert von 0 für übergeben *nRows*, `Move` aktualisiert den aktuellen Datensatz; `Move` aktuellen endet `AddNew` oder `Edit` Modus, und wird der aktuelle Datensatz Wert vor dem Wiederherstellen `AddNew` oder `Edit` aufgerufen wurde.  
  
> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können keine gelöschten Datensätze ausgelassen werden. Finden Sie unter [CRecordset::IsDeleted](#isdeleted) für Weitere Informationen. Beim Öffnen einer `CRecordset` mit der **SkipDeletedRecords** option festgelegt ist, `Move` bestätigt wird, wenn die *nRows* Parameter gleich 0 ist. Dieses Verhalten wird verhindert, dass die Aktualisierung von Zeilen, die von anderen Clientanwendungen, die mit den gleichen Daten gelöscht werden. Finden Sie unter der *DwOption* im Parameters [öffnen](#open) eine Beschreibung der **SkipDeletedRecords**.  
  
 `Move` Verschiebt das Recordset von Rowsets. Basierend auf den Werten für *nRows* und *wFetchType*, `Move` wird das entsprechende Rowset abgerufen und dann wird der erste Datensatz im dieses Rowset besitzt den aktuellen Datensatz. Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, ist die Größe des Rowsets immer 1. Beim Abrufen eines Rowsets `Move` ruft direkt die [CheckRowsetError](#checkrowseterror) Memberfunktion zum Behandeln von Fehlern, die sich aus der Abruf ergibt.  
  
 Abhängig von den Werten, die Sie übergeben, `Move` ist gleichbedeutend mit anderen `CRecordset` Memberfunktionen. Insbesondere wird der Wert der *wFetchType* kann darauf hindeuten, eine Memberfunktion, die eine intuitivere und häufig die bevorzugte Methode zum aktuellen Datensatz.  
  
 Die folgende Tabelle enthält die möglichen Werte für *wFetchType*, das Rowset, `Move` fetch wird basierend auf *wFetchType* und *nRows*, und alle entsprechenden Member, die Funktion entspricht *wFetchType*.  
  
|wFetchType|Abgerufenen rowset|Entsprechender Member-Funktion|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE` (Standardwert)|Das Rowset starten *nRows* Zeile(n) aus der ersten Zeile im aktuellen Rowset.||  
|`SQL_FETCH_NEXT`|Das nächste Rowset. *nRows* wird ignoriert.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|Das vorherige Rowset. *nRows* wird ignoriert.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|Das erste Rowset im Recordset. *nRows* wird ignoriert.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|Die letzte vollständige Rowset im Recordset. *nRows* wird ignoriert.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|Wenn *nRows* > 0, das Rowset ab *nRows* Zeilen vom Anfang des Recordsets. Wenn *nRows* < 0, das Rowset ab *nRows* Zeile(n) aus dem Ende des Recordsets. Wenn *nRows* = 0, wird eine Bedingung der Anfang der Datei (BOF) zurückgegeben.|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|Das Rowset, angefangen bei der Zeile, deren Lesezeichenwert entspricht *nRows*.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  Für die Forward-only-Recordsets `Move` ist nur gültig, wenn der Wert `SQL_FETCH_NEXT` für `wFetchType`.  
  
> [!CAUTION]
>  Aufrufen von `Move` löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Um festzustellen, ob das Recordset alle Datensätze hat, rufen [IsBOF](#isbof) und [IsEOF](#iseof).  
  
> [!NOTE]
>  Wenn Sie hinter dem Anfang oder Ende des Recordsets gescrollt haben ( `IsBOF` oder `IsEOF` ungleich NULL zurückgibt) wird beim Aufrufen einer `Move` Funktion löst möglicherweise eine `CDBException`. Z. B. wenn `IsEOF` ungleich NULL zurückgibt und `IsBOF` ist nicht der Fall, klicken Sie dann `MoveNext` wird eine Ausnahme ausgelöst, aber `MovePrev` geschieht dies nicht.  
  
> [!NOTE]
>  Beim Aufrufen `Move` während wird der aktuelle Datensatz aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLExtendedFetch** im Windows SDK.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>  CRecordset::MoveFirst  
 Macht dem ersten Datensatz in das erste Rowset zum aktuellen Datensatz.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Hinweise  
 Unabhängig davon, ob gesammelte implementiert wurde wird dies immer der erste Datensatz im Recordset sein.  
  
 Sie müssen keine Aufrufen `MoveFirst` sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt wird der erste Datensatz (sofern vorhanden) automatisch zum aktuellen Datensatz.  
  
> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.  
  
> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können keine gelöschten Datensätze ausgelassen werden. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion für Details.  
  
> [!CAUTION]
>  Aufrufen einer der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Um festzustellen, ob das Recordset alle Datensätze hat, rufen `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="movelast"></a>  CRecordset::MoveLast  
 Macht dem ersten Datensatz in die letzte vollständige Rowset zum aktuellen Datensatz.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MoveLast` einfach wechselt zum letzten Datensatz des Recordsets.  
  
> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.  
  
> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können keine gelöschten Datensätze ausgelassen werden. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion für Details.  
  
> [!CAUTION]
>  Aufrufen einer der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Um festzustellen, ob das Recordset alle Datensätze hat, rufen `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="movenext"></a>  CRecordset::MoveNext  
 Wird der erste Datensatz im Rowset weiter zum aktuellen Datensatz.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MoveNext` einfach auf den nächsten Datensatz wechselt.  
  
> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können keine gelöschten Datensätze ausgelassen werden. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion für Details.  
  
> [!CAUTION]
>  Aufrufen einer der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Um festzustellen, ob das Recordset alle Datensätze hat, rufen `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Es wird empfohlen, die Sie aufrufen `IsEOF` vor dem Aufruf `MoveNext`. Wenn Sie nach dem Ende des Recordsets gescrollt haben z. B. `IsEOF` zurück ungleich NULL ist; ein nachfolgender Aufruf von `MoveNext` eine Auslösung ausgeben würde.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="moveprev"></a>  CRecordset::MovePrev  
 Wird der erste Datensatz im Rowset vorherigen zum aktuellen Datensatz.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MovePrev` einfach auf den vorherigen Datensatz wechselt.  
  
> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.  
  
> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können keine gelöschten Datensätze ausgelassen werden. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion für Details.  
  
> [!CAUTION]
>  Aufrufen einer der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze enthält. Um festzustellen, ob das Recordset alle Datensätze hat, rufen `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Es wird empfohlen, die Sie aufrufen `IsBOF` vor dem Aufruf `MovePrev`. Wenn Sie den Anfang des Recordsets gescrollt haben z. B. `IsBOF` zurück ungleich NULL ist; ein nachfolgender Aufruf von `MovePrev` eine Auslösung ausgeben würde.  
  
> [!NOTE]
>  Wenn Sie jede der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions  
 Wird zum Festlegen von Optionen, die (in der Auswahl verwendete) für die angegebene ODBC-Anweisung aufgerufen.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 *Befehls beschäftigt*  
 Die **Befehls beschäftigt** der ODBC-Anweisung, deren Optionen festgelegt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `OnSetOptions` zum Festlegen von Optionen, die (in der Auswahl verwendete) für die angegebene ODBC-Anweisung. Das Framework ruft diese Memberfunktion zum anfänglichen Optionen für das Recordset festlegen. `OnSetOptions` die Datenquelle-Unterstützung für scrollfähige Cursor und Cursorparallelität bestimmt und das Recordset-Optionen entsprechend festgelegt. (Während `OnSetOptions` dient zum Auswahlvorgänge, `OnSetUpdateOptions` für Update-Vorgänge verwendet wird.)  
  
 Überschreiben Sie `OnSetOptions` Optionen speziell für den Treiber oder die Datenquelle festgelegt. Beispielsweise, wenn die Datenquelle unterstützt, die für den exklusiven Zugriff zu öffnen, Sie können außer Kraft gesetzt `OnSetOptions` diese Funktion nutzen.  
  
 Weitere Informationen zu Cursorn finden Sie im Artikel [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions  
 Zum Festlegen von Optionen (verwendet für Update) für die angegebene ODBC-Anweisung aufgerufen.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 *Befehls beschäftigt*  
 Die **Befehls beschäftigt** der ODBC-Anweisung, deren Optionen festgelegt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `OnSetUpdateOptions` zum Festlegen von Optionen, die (verwendet für Update) für die angegebene ODBC-Anweisung. Das Framework ruft diese Memberfunktion auf, nach dem Erstellen einer Befehls beschäftigt zum Aktualisieren von Datensätzen in einem Recordset. (Während `OnSetOptions` dient zum Auswahlvorgänge, `OnSetUpdateOptions` für Update-Vorgänge verwendet wird.) `OnSetUpdateOptions` bestimmt die Datenquelle-Unterstützung für scrollfähige Cursor und Cursorparallelität und das Recordset-Optionen entsprechend festgelegt.  
  
 Überschreiben Sie `OnSetUpdateOptions` Optionen einer ODBC-Anweisung festgelegt werden, bevor diese Anweisung verwendet wird, auf eine Datenbank zuzugreifen.  
  
 Weitere Informationen zu Cursorn finden Sie im Artikel [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="open"></a>  CRecordset:: Open  
 Öffnet das Recordset, indem die Tabelle abgerufen oder die vom Recordset darstellte Abfrage durchgeführt wird.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>Parameter  
 *nOpenType*  
 Akzeptieren Sie den Standardwert **AFX_DB_USE_DEFAULT_TYPE**, oder verwenden Sie einen der folgenden Werte aus der **Enum OpenType**:  
  
- **CRecordset:: Dynaset** ein Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets bestimmt. Die von anderen Benutzern an den Datenwerten vorgenommenen Änderungen sind nach einem Abrufvorgang allerdings sichtbar. Dynasets sind auch als keysetgesteuerte Recordsets bekannt.  
  
- **CRecordset:: Snapshot** ein statisches Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets und die Datenwerte beim Abrufen der Datensätze bestimmt. Die von anderen Benutzern vorgenommenen Änderungen sind nicht sichtbar, bis das Recordset geschlossen und erneut geöffnet wird.  
  
- **CRecordset:: Dynamic** ein Recordset mit bidirektionalem Bildlauf. Die von anderen Benutzern an der Mitgliedschaft, der Reihenfolge und den Datenwerten vorgenommen Änderungen sind nach einem Abrufvorgang sichtbar. Beachten Sie, dass dieser Recordsettyp von vielen ODBC-Treibern nicht unterstützt wird.  
  
- **CRecordset:: forwardOnly** ein schreibgeschütztes Recordset mit Bildlauf ausschließlich vorwärts ausgeführt.  
  
     Für `CRecordset`, der Standardwert ist **CRecordset:: Snapshot**. Mithilfe des Standardwertmechanismus kann bei Visual C++-Assistenten mit ODBC-`CRecordset` sowie DAO- `CDaoRecordset`, die über unterschiedliche Standardwerte verfügen, interagiert werden.  
  
 Weitere Informationen über diese Recordsettypen finden Sie im Artikel [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Verwandte Informationen finden Sie im Artikel "Verwenden von Blocks und bildlauffähigen Cursorn" im Windows SDK.  
  
> [!CAUTION]
>  Wenn der angeforderte Typ nicht unterstützt wird, löst das Framework eine Ausnahme aus.  
  
 *lpszSQL*  
 Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:  
  
-   Ein **NULL** Zeiger.  
  
-   Name der Tabelle  
  
-   Eine SQL **wählen** Anweisung (optional mit einem SQL- **, in denen** oder **ORDER BY** Klausel).  
  
-   Ein **Aufrufen** Anweisung, die den Namen einer vordefinierten Abfrage (gespeicherten Prozedur) angeben. Achten Sie darauf, dass Sie kein Leerzeichen zwischen der geschweiften Klammer einfügen und die **Aufrufen** Schlüsselwort.  
  
 Weitere Informationen zu dieser Zeichenfolge finden Sie in der Tabelle und der Diskussion über die Rolle von ClassWizard unter Hinweisen.  
  
> [!NOTE]
>  Die Reihenfolge der Spalten im Resultset muss die Reihenfolge der RFX-entsprechen oder der Bulk-RFX-Funktionsaufrufe in Ihre [DoFieldExchange](#dofieldexchange) oder [DoBulkFieldExchange](#dobulkfieldexchange) -funktionsüberschreibung.  
  
 *Wert*  
 Eine Bitmaske, die eine Kombination der unten aufgeführten Werte angeben kann. Einige davon schließen sich einander aus. Der Standardwert ist **keine**.  
  
- **CRecordset:: None** ohne Optionen festzulegen. Dieser Parameterwert und alle anderen Werte schließen einander aus. Standardmäßig kann das Recordset mit aktualisiert [bearbeiten](#edit) oder [löschen](#delete) und ermöglicht das Anfügen von neuer Datensätzen mit [AddNew](#addnew). Aktualisierbarkeit hängt von der Datenquelle als auch auf die *nOpenType* Option, die Sie angeben. Optimierung für Massenhinzufügeaktionen ist nicht verfügbar. Das gesammelte Abrufen von Zeilen wird nicht implementiert. Gelöschte Datensätze werden während der Recordsetnavigation nicht übersprungen. Lesezeichen sind nicht verfügbar. Automatische Überprüfung fehlerhafter Felder wird implementiert.  
  
- **CRecordset:: AppendOnly** dürfen keine `Edit` oder `Delete` auf das Recordset. Lassen Sie nur `AddNew` zu. Diese Option ist mit sich gegenseitig ausschließende **CRecordset:: ReadOnly**.  
  
- **CRecordset:: ReadOnly** Öffnen des Recordsets als schreibgeschützt. Diese Option ist mit sich gegenseitig ausschließende **CRecordset:: AppendOnly**.  
  
- **CRecordset:: optimizeBulkAdd** eine vorbereitete SQL­Anweisung für die Optimierung auf einmal Hinzufügen von Datensätzen verwendet. Gilt nur, wenn Sie nicht die ODBC-API-Funktion verwenden **SQLSetPos** zum Aktualisieren des Recordsets. Das erste Update bestimmt die geänderten Felder. Diese Option und `CRecordset::useMultiRowFetch` schließen einander aus.  
  
- `CRecordset::useMultiRowFetch` Implementieren Sie die gesammelte damit mehrere Zeilen in einem Abrufvorgang abgerufen werden können. Das ist eine erweiterte Funktion, die zum Verbessern der Leistung entworfen wurde. Allerdings wird der Massenaustausch von Datensatzfeldern von ClassWizard nicht unterstützt. Diese Option ist mit sich gegenseitig ausschließende **optimizeBulkAdd**. Beachten Sie, dass bei Angabe von `CRecordset::useMultiRowFetch`, klicken Sie dann die Option **:: Nodirtyfieldcheck** wird automatisch aktiviert wird (doppelte Pufferung ist nicht verfügbar), auf die Forward-only-Recordsets, die Option  **:: Useextendedfetch** wird automatisch aktiviert werden. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
- **CRecordset:: Skipdeletedrecords** beim Navigieren durch das Recordset alle gelöschten Datensätze zu überspringen. Das verlangsamt in bestimmten relativen Abrufen die Leistung. Diese Option ist bei forward-only-Recordsets ungültig. Beim Aufrufen [verschieben](#move) mit der *nRows* Parameter auf 0 festgelegt, und die **CRecordset:: Skipdeletedrecords** option festgelegt ist, `Move` implementiert. Beachten Sie, dass **CRecordset:: Skipdeletedrecords** ähnelt *treiberverpackung*, d. h., die Zeilen gelöscht werden aus dem Recordset entfernt. Wenn der Treiber allerdings Datensätze verpackt, werden nur die von Ihnen gelöschten Datensätze übersprungen. Die von anderen Benutzern gelöschten Datensätze werden nicht übersprungen, solange das Recordset geöffnet ist. **CRecordset:: Skipdeletedrecords** überspringt die von anderen Benutzern gelöschten Zeilen.  
  
- **CRecordset:: useBookmarks** möglicherweise Lesezeichen für das Recordset verwenden, wenn unterstützt. Lesezeichen verlangsamen den Datenabruf, verbessern aber die Leistung bei der Datennavigation. In forward-only-Recordsets ist das ungültig. Weitere Informationen finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
- **:: Nodirtyfieldcheck** Deaktivieren der automatischen Überprüfung (doppelte Pufferung). Dadurch wird die Leistung verbessert. Sie müssen allerdings Felder manuell als geändert kennzeichnen, indem Sie die Memberfunktionen `SetFieldDirty` und `SetFieldNull` aufrufen. Beachten Sie, dass die doppelte Pufferung in der `CRecordset`-Klasse der doppelten Pufferung in der `CDaoRecordset`-Klasse ähnelt. Bei `CRecordset` können Sie die doppelte Pufferung allerdings nicht für einzelne Felder aktivieren. Sie können sie für alle Felder aktivieren oder deaktivieren. Beachten Sie, dass bei Angabe die Option `CRecordset::useMultiRowFetch`, klicken Sie dann **:: Nodirtyfieldcheck** wird eingeschaltet werden, automatisch; allerdings `SetFieldDirty` und `SetFieldNull` kann nicht in Recordsets, die gesammelte implementieren verwendet werden.  
  
- **CRecordset:: ExecuteDirect** verwenden Sie keine vorbereitete SQL-Anweisung. Zum Verbessern der Leistung Geben Sie diese Option, wenn die `Requery` Memberfunktion wird nie aufgerufen werden.  
  
- **:: Useextendedfetch** implementieren `SQLExtendedFetch** instead of `SQLFetch`. This is designed for implementing bulk row fetching on forward-only recordsets. If you specify the option `Wert CRecordset:: useMultiRowFetch "auf einen Forward-only-Recordset, dann **:: Useextendedfetch** wird aktiviert automatisch.  
  
- **CRecordset:: userAllocMultiRowBuffers** der Benutzer wird den Daten Speicherpuffer zuordnen. Verwenden Sie diese Option in Verbindung mit `CRecordset::useMultiRowFetch`, wenn Sie Ihren eigenen Speicher zuordnen möchten. Andernfalls ordnet wird der notwendigen Speicher vom Framework automatisch zugeordnet. Weitere Informationen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Beachten Sie, dass die Angabe **CRecordset:: userAllocMultiRowBuffers** ohne `CRecordset::useMultiRowFetch` führt zu einem fehlgeschlagenen Assertion.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CRecordset` -Objekt erfolgreich geöffnet wurde; andernfalls 0, wenn [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (sofern aufgerufen) 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Memberfunktion zum Ausführen der vom Recordset definierten Abfrage aufrufen. Vor dem Aufruf `Open`, müssen Sie das Recordset-Objekt erstellen.  
  
 Verbindung des Recordsets mit der Datenquelle hängt von der Erstellung des Recordsets vor dem Aufruf von `Open`. Wenn Sie übergeben ein [CDatabase](../../mfc/reference/cdatabase-class.md) Objekt an den recordsetkonstruktor, die nicht mit der Datenquelle verbunden wurde, verwendet diese Memberfunktion [GetDefaultConnect](#getdefaultconnect) versucht, das Datenbankobjekt zu öffnen. Wenn Sie übergeben **NULL** an den recordsetkonstruktor der Konstruktor erstellt ein `CDatabase` -Objekt für Sie und `Open` versucht, das Datenbankobjekt zu verbinden. Weitere Informationen zum Schließen des Recordsets und die Verbindung in diesen unterschiedlichen Situationen finden Sie unter [schließen](#close).  
  
> [!NOTE]
>  Der Zugriff auf eine Datenquelle durch ein `CRecordset`-Objekt wird immer freigegeben. Anders als die `CDaoRecordset`-Klasse können Sie kein `CRecordset`-Objekt zum Öffnen einer Datenquelle mit exklusivem Zugriff verwenden.  
  
 Beim Aufruf `Open`, eine Abfrage, in der Regel eine SQL **wählen** -Anweisung, wählt die Datensätze auf Grundlage der Kriterien, die in der folgenden Tabelle gezeigt.  
  
|Der Wert des lpszSQL-Parameters.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||  
|SQL-Tabellenname|Alle Spalten der Tabellenliste in `DoFieldExchange` oder `DoBulkFieldExchange`.|`"Customer"`|  
|Der vordefinierte Name der Abfrage (gespeicherten Prozedur)|Die Spalten, zu denen die Abfrage per Definition zurückgibt.|`"{call OverDueAccts}"`|  
|**Wählen Sie** Spaltenliste **FROM** Tabellenliste|Die angegebenen Spalten aus den angegebenen Tabellen.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  Achten Sie darauf, dass keine zusätzlichen Leerzeichen in der SQL-Zeichenfolge eingefügt werden. Z. B., wenn Sie Leerzeichen zwischen der geschweiften Klammer einfügen und die **Aufrufen** Schlüsselwort MFC wird fälschlicherweise die SQL-Zeichenfolge als Tabellenname und bindet sie in einer **wählen** -Anweisung, die führt ein ausgelöste Ausnahme. Auf ähnliche Weise, wenn die vordefinierten Abfrage einen Output-Parameter verwendet, fügen Sie keine Leerzeichen zwischen der geschweiften Klammer und dem '' Symbol. Schließlich müssen Sie nicht Leerzeichen vor in der geschweiften Klammer einfügen ein **Aufrufen** Anweisung oder vor der **auswählen** -Schlüsselwort in einer **wählen** Anweisung.  
  
 Die übliche Vorgehensweise ist die Übergabe **NULL** auf `Open`; in diesem Fall `Open` Aufrufe [GetDefaultSQL](#getdefaultsql). Wenn Sie eine abgeleitete verwenden `CRecordset` -Klasse, **GetDefaultSQL** bietet Ihnen in ClassWizard angegebenen bzw. für die Tabelle. Sie können stattdessen andere Informationen im `lpszSQL`-Parameter angeben.  
  
 Jede Übergabe `Open` erstellt eine endgültige SQL-Zeichenfolge für die Abfrage (die Zeichenfolge möglicherweise die SQL **, in dem** und **ORDER BY** Klauseln angefügt, um die `lpszSQL` Sie übergebene Zeichenfolge) und führt dann die Abfrage. Sie können die erstellte Zeichenfolge überprüfen, durch den Aufruf [GetSQL](#getsql) nach dem Aufruf *`Open`. Weitere Informationen darüber, wie das Recordset erstellt eine SQL-Anweisung und die Auswahl von Datensätzen finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
 Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 Wenn Sie Optionen für das Recordset, z. B. einen Filter oder eine Sortierung festlegen möchten geben Sie diese nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf `Open`. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie [Requery](#requery).  
  
 Weitere Informationen sowie weitere Beispiele finden Sie in den Artikeln [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), und [Recordset: Erstellen und schließen Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Die folgenden Codebeispiele zeigen verschiedene Formen von der `Open` aufrufen.  
  
 [!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset  
 Aktualisiert die Daten und den Status für eine Zeile im aktuellen Rowset.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parameter  
 *wRow*  
 Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 0 (null), um die Größe des Rowsets liegen.  
  
 *wLockType*  
 Ein Wert, der angibt, wie Sie die Zeile gesperrt wird, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert von 0 (null) für übergeben *wRow*, und klicken Sie dann jede Zeile im Rowset aktualisiert wird.  
  
 Mit `RefreshRowset`, gesammelte durch Angabe implementiert haben muss die **CRecordset::useMulitRowFetch** -Option in der [öffnen](#open) Memberfunktion.  
  
 `RefreshRowset` Ruft die ODBC-API-Funktion **SQLSetPos**. Die *wLockType* Parameter gibt die Lock-Zustand der Zeile nach **SQLSetPos** ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für *wLockType*.  
  
|wLockType|Beschreibung|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (Standardwert)|Der Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in dem Zustand gesperrt oder entsperrt ist, vor dem `RefreshRowset` aufgerufen wurde.|  
|`SQL_LOCK_EXCLUSIVE`|Der Treiber oder die Datenquelle sperrt die Zeile ausschließlich aus. Nicht alle Datenquellen unterstützen diese Art von Sperren.|  
|`SQL_LOCK_UNLOCK`|Der Treiber oder die Datenquelle entsperrt die Zeile an. Nicht alle Datenquellen unterstützen diese Art von Sperren.|  
  
 Weitere Informationen zu **SQLSetPos**, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="requery"></a>  CRecordset  
 Wird neu erstellt (aktualisiert) einem Recordset.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset erfolgreich neu erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 In der Reihenfolge für das Recordset entsprechend der Hinzufügungen und löschungen, die Sie oder andere Benutzer an der Datenquelle ausführen möchten, müssen Sie das Recordset erstellen, durch Aufruf `Requery`. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer ihre vorhandene Datensätze (aber nicht Additions) Stellen angezeigt. Wenn das Recordset eine Momentaufnahme ist, müssen Sie aufrufen `Requery` auf Änderungen von anderen Benutzern als auch Hinzufügungen und löschungen sind.  
  
 Rufen Sie für ein Dynaset oder eine Momentaufnahme, `Requery` jederzeit das Recordset, das über einen neuen Filter oder sortieren oder neue Parameterwerte neu erstellt werden sollen. Legen Sie die neue filtern oder sortieren Eigenschaft durch Zuweisen von neuen Werten zu **M_strFilter** und `m_strSort` vor dem Aufruf `Requery`. Neue Parameter Parameterdatenmember vor dem Aufruf neue Werte zuweisen festlegen `Requery`. Wenn die Filter- und sortierungsausdrücke Zeichenfolgen unverändert sind, können Sie die Abfrage erneut zur Verbesserung, die Leistung beiträgt.  
  
 Schlägt der Versuch, das Recordset neu erstellen, wird das Recordset geschlossen. Vor dem Aufruf `Requery`, können Sie bestimmen, ob das Recordset durch den Aufruf erneut abgefragt werden kann die `CanRestart` Memberfunktion. `CanRestart` garantiert nicht, dass `Requery` wird erfolgreich ausgeführt.  
  
> [!CAUTION]
>  Rufen Sie `Requery` erst nach dem aufgerufenen [öffnen](#open).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein Recordset zum Anwenden von einer anderen Sortierreihenfolge neu erstellt.  
  
 [!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>  CRecordset:: SetAbsolutePosition auf  
 Positioniert das Recordset im Datensatz, der angegebene Datensatz entspricht.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>Parameter  
 *nRows*  
 Die vom einsbasierte Ordnungsposition für den aktuellen Datensatz des Recordsets.  
  
### <a name="remarks"></a>Hinweise  
 `SetAbsolutePosition` Verschiebt den Zeiger für den aktuellen Datensatz basierend auf diese Position.  
  
> [!NOTE]
>  Diese Memberfunktion ist bei Forward-only-Recordsets ungültig.  
  
 Für ODBC-Recordsets bezieht sich auf den ersten Eintrag im Recordset eine absolute Position-Einstellung von 1. die Einstellung 0 bezieht sich auf die Position der Anfang der Datei (BOF).  
  
 Sie können auch negative Werte zu übergeben `SetAbsolutePosition`. In diesem Fall wird das Recordset Position am Ende des Recordsets ausgewertet. Beispielsweise `SetAbsolutePosition( -1 )` bewegt den aktuellen Datensatz Zeiger auf den letzten Datensatz des Recordsets.  
  
> [!NOTE]
>  Absolute Position ist nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode der beibehalten und die Rückgabe an einer bestimmten Position seit einen Datensatz Position ändert sich, wenn die vorherigen Datensätze gelöscht werden. Darüber hinaus, Sie können nicht gewährleistet werden, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets nicht garantiert ist, es sei denn, es mit einer SQL-Anweisung mit einer erstelltwird**ORDER BY** Klausel.  
  
 Weitere Informationen zu Recordsetnavigation und Lesezeichen, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="setbookmark"></a>  CRecordset::SetBookmark  
 Der Datensatz mit dem angegebenen Lesezeichen positioniert das Recordset.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 *varBookmark*  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) Objekt mit dem Lesezeichenwert für einen bestimmten Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Um festzustellen, ob Lesezeichen, auf das Recordset unterstützt werden, rufen [CanBookmark](#canbookmark). Um Lesezeichen verfügbar zu machen, wenn sie unterstützt werden, müssen Sie festlegen der **CRecordset:: useBookmarks** -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
>  Wenn das Lesezeichen nicht unterstützte oder nicht verfügbar sind, beim Aufrufen `SetBookmark` führt dazu, eine Ausnahme ausgelöst. Lesezeichen werden nicht auf die Forward-only-Recordsets unterstützt.  
  
 Um das Lesezeichen für den aktuellen Datensatz zuerst abzurufen, rufen Sie [GetBookmark](#getbookmark), speichert den Lesezeichenwert, der eine `CDBVariant` Objekt. Sie können später an diesen Datensatz zurückgeben, durch den Aufruf `SetBookmark` mit dem gespeicherten Lesezeichenwert.  
  
> [!NOTE]
>  Überprüfen Sie nach bestimmten Vorgängen Recordset die Persistenz Lesezeichen vor dem Aufruf `SetBookmark`. Wenn Sie ein Lesezeichen mit abrufen, z. B. `GetBookmark` und rufen dann `Requery`, das Lesezeichen kann nicht mehr gültig sein. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty  
 Kennzeichnet einen Felddatenmember des Recordset-Objekts als geändert oder als unverändert.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *PV*  
 Enthält die Adresse des eine felddatenelement im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember der Recordset gekennzeichnet sind. (C++ **NULL** entspricht nicht dem als Null in der Terminologie von Datenbanken, d. h. "kann kein Wert".)  
  
 *bDirty*  
 **"True"** ist der Felddatenmember als "(geändert) modifizierte Seiten" markiert werden. Andernfalls **"false"** ist das felddatenelement als "(unverändert) bereinigen" markiert werden.  
  
### <a name="remarks"></a>Hinweise  
 Markieren von Feldern als unverändert wird sichergestellt, dass das Feld wird nicht aktualisiert und führt zu weniger SQL-Datenverkehr.  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht anwendbar auf Recordsets, die gesammelte verwenden. Gesammelte, klicken Sie dann implementiert, `SetFieldDirty` führt zu einem fehlgeschlagenen Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie auf den Datensatz in der Datenquelle durch die Datensatzfeldaustausch (RFX)-Mechanismus geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld dirty automatisch, sodass Sie nur selten aufrufen müssen `SetFieldDirty` selbst, aber Sie können in einigen Fällen möchten sicherstellen, dass Spalten werden explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert in die Felddaten ist Member.  
  
> [!CAUTION]
>  Rufen Sie diese Memberfunktion auf, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mit **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder, nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder sind nicht betroffen.  
  
 Auf **Param** Felder, geben Sie an die tatsächliche Adresse der Person **Param** auf, wie z. B. zusammenarbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, dass Sie nicht alle festlegen **Param** Felder **NULL**, wie Sie mit **OutputColumn** Felder.  
  
##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull  
 Felddatenmember der Recordset als Null (insbesondere mit kein Wert) oder als nicht-Null-Flags.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *PV*  
 Enthält die Adresse des eine felddatenelement im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember der Recordset gekennzeichnet sind. (C++ **NULL** entspricht nicht dem als Null in der Terminologie von Datenbanken, d. h. "kann kein Wert".)  
  
 *bNull*  
 Wert ungleich NULL, wenn die Felddatenmember gekennzeichnet wird, dass kein Wert (Null) ist. Andernfalls 0, wenn das felddatenelement wird als ungleich Null gekennzeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) modifizierte Seiten" markiert. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits über Werte verfügen oder Null sind.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nicht in Recordsets, die gesammelte verwenden. Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, beim Aufrufen von `SetFieldNull` führt zu einem fehlgeschlagenen Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Wenn Sie ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert ein, rufen Sie möchten `SetFieldNull` mit *bNull* festgelegt **"true"** so kennzeichnen Sie es als Null. Wenn ein Feld wurde zuvor Null markiert, und jetzt Sie ihm einen Wert zuzuweisen möchten, legen Sie einfach den neuen Wert. Sie müssen nicht mit der Null-Flag entfernen `SetFieldNull`. Um zu bestimmen, ob das Feld NULL zulässig ist, rufen Sie `IsFieldNullable`.  
  
> [!CAUTION]
>  Rufen Sie diese Memberfunktion auf, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mit **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder, nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder sind nicht betroffen.  
  
 Auf **Param** Felder, geben Sie an die tatsächliche Adresse der Person **Param** auf, wie z. B. zusammenarbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, dass Sie nicht alle festlegen **Param** Felder **NULL**, wie Sie mit **OutputColumn** Felder.  
  
> [!NOTE]
>  Beim Festlegen der Parameter auf Null, einen Aufruf von `SetFieldNull` , bevor das Recordset geöffnet Ergebnisse in eine Assertion ist. In diesem Fall rufen [SetParamNull](#setparamnull).  
  
 `SetFieldNull` wird durch implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode  
 Legt das Sperrverhalten "optimistic" Sperren (Standard) oder "vollständige" Sperren. Bestimmt, wie Datensätze gesperrt werden, nach Updates.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>Parameter  
 *nMode*  
 Enthält die folgenden Werte aus der **Enum LockMode**:  
  
- **optimistische** eingeschränktes Sperren sperrt den aktualisierten Datensatz gelesen nur während des Aufrufs `Update`.  
  
- **Eingeschränkte** pessimistische Sperren den Datensatz sperrt, möglichst bald `Edit` aufgerufen und bleibt gesperrt, bis die `Update` Aufruf abgeschlossen wird, oder Sie verschieben, um einen neuen Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, welche der beiden Datensatzsperren Strategien geben an, die das Recordset für Updates verwendet werden sollen. Standardmäßig wird das Sperrverhalten von einem Recordset **optimistische**. Sie können ändern, um eine größere Vorsicht walten **eingeschränkte** Strategie sperren. Rufen Sie `SetLockingMode` nach dem Erstellen und öffnen Sie das Recordsetobjekt, aber vor dem Aufruf `Edit`.  
  
##  <a name="setparamnull"></a>  CRecordset::SetParamNull  
 Flags-Parameter als Null (insbesondere mit kein Wert) oder als ungleich Null.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 *nIndex*  
 Der nullbasierte Index des Parameters.  
  
 *bNull*  
 Wenn **"true"** (Standardwert), wird der Parameter als Null gekennzeichnet. Andernfalls wird der Parameter als ungleich Null gekennzeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [SetFieldNull](#setfieldnull), Sie können Aufrufen `SetParamNull` , bevor Sie das Recordset geöffnet haben.  
  
 `SetParamNull` wird i. d. r. mit vordefinierten Abfragen (gespeicherte Prozeduren) verwendet werden.  
  
##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition  
 Verschiebt den Cursor an einer Zeile innerhalb des aktuellen Rowsets.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parameter  
 *wRow*  
 Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.  
  
 *wLockType*  
 Der Wert, der angibt, wie Sie die Zeile gesperrt wird, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Bei der Implementierung von gesammelte werden Datensätze von Rowsets abgerufen, in dem der erste Datensatz des abgerufenen Rowsets des aktuellen Datensatzes ist. Um den aktuellen Datensatz zu einem anderen Datensatz innerhalb des Rowsets machen, rufen `SetRowsetCursorPosition`. Sie können z. B. kombinieren `SetRowsetCursorPosition` mit der [GetFieldValue](#getfieldvalue) Memberfunktion versucht, die Daten aus jeder Datensatz des Recordsets dynamisch abzurufen.  
  
 Mit `SetRowsetCursorPosition`, gesammelte durch Angabe implementiert haben muss der `CRecordset::useMultiRowFetch` -Option von der *Wert* Parameter in der [öffnen](#open) Memberfunktion.  
  
 `SetRowsetCursorPosition` Ruft die ODBC-API-Funktion **SQLSetPos**. Die *wLockType* Parameter gibt die Lock-Zustand der Zeile nach **SQLSetPos** ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für *wLockType*.  
  
|wLockType|Beschreibung|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE` (Standardwert)|Der Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in dem Zustand gesperrt oder entsperrt ist, vor dem `SetRowsetCursorPosition` aufgerufen wurde.|  
|`SQL_LOCK_EXCLUSIVE`|Der Treiber oder die Datenquelle sperrt die Zeile ausschließlich aus. Nicht alle Datenquellen unterstützen diese Art von Sperren.|  
|`SQL_LOCK_UNLOCK`|Der Treiber oder die Datenquelle entsperrt die Zeile an. Nicht alle Datenquellen unterstützen diese Art von Sperren.|  
  
 Weitere Informationen zu **SQLSetPos**, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize  
 Gibt die Anzahl der Datensätze, die Sie während eines Abrufs abrufen möchten.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>Parameter  
 *dwNewRowsetSize*  
 Die Anzahl der Zeilen, die während einer bestimmten Fetch abgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dieser virtuelle Memberfunktion gibt an, wie viele Zeilen, die Sie während einer einzigen Abfrage abrufen, wenn gesammelte verwenden möchten. Um gesammelte zu implementieren, müssen Sie festlegen der `CRecordset::useMultiRowFetch` -Option in der *OpenEx* Parameter von der [öffnen](#open) Memberfunktion.  
  
> [!NOTE]
>  Aufrufen von `SetRowsetSize` ohne Implementierung Bulk gesammelte führt zu einer fehlgeschlagenen Assertion.  
  
 Rufen Sie `SetRowsetSize` vor dem Aufruf `Open` zunächst die Rowsetgröße für das Recordset festlegen. Die Standardgröße des Rowsets bei der Implementierung gesammelte ist 25.  
  
> [!NOTE]
>  Seien Sie vorsichtig beim Aufrufen von `SetRowsetSize`. Wenn Sie Speicher für die Daten manuell zugeordnet sind (nach den Angaben von der **CRecordset:: userAllocMultiRowBuffers** Option des Parameters Wert in `Open`), sollten Sie überprüfen, ob Sie diesen Speicher neu zuordnen müssen nach dem Aufruf puffert `SetRowsetSize`, jedoch vor dem Ausführen alle Navigationsvorgang Cursor.  
  
 Um die aktuelle Einstellung für die Größe des Rowsets abzurufen, rufen [GetRowsetSize](#getrowsetsize).  
  
 Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="update"></a>  CRecordset:: Update  
 Schließt eine `AddNew` oder `Edit` Vorgangs durch die neuen oder bearbeiteten Daten speichern, für die Datenquelle.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Datensatz wurde erfolgreich aktualisiert wurde; andernfalls 0, wenn keine Spalten sich geändert haben. Wenn keine Datensätze aktualisiert wurden oder wenn mehr als einen Datensatz aktualisiert wurde, wird eine Ausnahme ausgelöst. Eine Ausnahme wird auch für die Datenquelle für alle anderen Fehler ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, nach einem Aufruf von der [AddNew](#addnew) oder [bearbeiten](#edit) Memberfunktion. Dieser Aufruf ist erforderlich, um das Abschließen der `AddNew` oder `Edit` Vorgang.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie können nicht `Update`. Dadurch wird ein Assertionsfehler zurückgeben. Obwohl Klasse `CRecordset` bietet einen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Beide `AddNew` und `Edit` vorbereiten Bearbeitungspuffer, in dem die hinzugefügten oder bearbeiteten Daten platziert ist, für die Speicherung der Datenquelle. `Update` Speichert die Daten. Nur Felder erkannt, dass geändert oder markiert werden aktualisiert.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Update` aufrufen (und der entsprechenden `AddNew` oder `Edit` aufrufen) Teil einer Transaktion. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!CAUTION]
>  Beim Aufrufen `Update` ohne Aufruf eines `AddNew` oder `Edit`, `Update` löst eine `CDBException`. Beim Aufrufen `AddNew` oder `Edit`, rufen Sie `Update` vor dem Aufrufen einer `Move` Vorgang oder vor dem Schließen des Recordsets oder Verbindung mit der Datenquelle. Andernfalls sind Ihre Änderungen verloren gehen, ohne Benachrichtigung.  
  
 Weitere Informationen zum Umgang mit `Update` auftretenden Fehlern, finden Sie im Artikel [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordView-Klasse](../../mfc/reference/crecordview-class.md)
