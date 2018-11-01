---
title: CRecordset-Klasse
ms.date: 11/04/2016
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
ms.openlocfilehash: f8193e071d9c7730e85cabbcb10a701ca763085e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621393"
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
|[CRecordset::CRecordset](#crecordset)|Erstellt ein `CRecordset`-Objekt. Die abgeleitete Klasse muss einen Konstruktor bereitstellen, der diese aufruft.|

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|Bereitet zum Hinzufügen eines neuen Eintrags. Rufen Sie `Update` das Hinzufügen abgeschlossen.|
|[CRecordset::CanAppend](#canappend)|Gibt ungleich NULL, wenn das Recordset über neue Datensätze hinzugefügt werden können die `AddNew` Member-Funktion.|
|[CRecordset:: CanBookmark](#canbookmark)|Gibt, die ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|
|[CRecordset::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess aus einem zweiten Thread ab.|
|[CRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer `AddNew` oder `Edit` Vorgang.|
|[CRecordset::CanRestart](#canrestart)|Ungleich NULL zurück, wenn `Requery` aufgerufen werden, um die Abfrage des Recordsets erneut ausführen.|
|[CRecordset::CanScroll](#canscroll)|Gibt, die ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|
|[CRecordset::CanTransact](#cantransact)|Gibt, die ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|
|[CRecordset::CanUpdate](#canupdate)|Gibt ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|
|[CRecordset::CheckRowsetError](#checkrowseterror)|Wird aufgerufen, zur Behandlung von Fehlern, die während des Abrufens der Datensatz generiert.|
|[CRecordset::Close](#close)|Schließt das Recordset und der ODBC-Befehls beschäftigt zugeordnet.|
|[CRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang scrollen.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Wird aufgerufen, zum Austauschen von Datenzeilen aus der Datenquelle auf das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).|
|[CRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).|
|[CRecordset::Edit](#edit)|Bereitet für Änderungen an den aktuellen Datensatz. Rufen Sie `Update` um die Bearbeitung abzuschließen.|
|[CRecordset::FlushResultSet](#flushresultset)|Gibt zurück, die ungleich NULL, wenn ein anderes Resultsets vorhanden ist, wurde abgerufen werden soll, wenn Sie eine vordefinierte Abfrage verwenden.|
|[CRecordset::GetBookmark](#getbookmark)|Weist den Lesezeichenwert, der einen Datensatz an das Parameterobjekt.|
|[GetDefaultConnect](#getdefaultconnect)|Wird aufgerufen, um die Standardverbindungszeichenfolge zu erhalten.|
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, rufen Sie die Standard-SQL-Zeichenfolge ausgeführt wird.|
|[CRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Gibt die Anzahl der Felder im Recordset zurück.|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Gibt bestimmte Arten von Informationen zu den Feldern in einem Recordset zurück.|
|[CRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze im Recordset zurück.|
|[CRecordset::GetRowsetSize](#getrowsetsize)|Gibt die Anzahl der Datensätze, die Sie während einer einzigen Abfrage abrufen möchten.|
|[CRecordset::GetRowsFetched](#getrowsfetched)|Gibt die tatsächliche Anzahl der Zeilen, während ein Abrufvorgang abgerufen werden.|
|[CRecordset::GetRowStatus](#getrowstatus)|Gibt den Status der Zeile nach einer Fetch zurück.|
|[CRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset.|
|[CRecordset::GetStatus](#getstatus)|Ruft den Status des Recordset-Objekts ab: der Index des aktuellen Datensatzes und gibt an, ob eine endgültige Anzahl der Datensätze abgerufen wurden.|
|[CRecordset::GetTableName](#gettablename)|Ruft den Namen der Tabelle auf der das Recordset basiert.|
|[CRecordset::IsBOF](#isbof)|Gibt, die ungleich NULL, wenn das Recordset vor dem ersten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.|
|[CRecordset::IsDeleted](#isdeleted)|Gibt, die ungleich NULL, wenn das Recordset in einem gelöschten Datensatz positioniert ist.|
|[CRecordset::IsEOF](#iseof)|Gibt, die ungleich NULL, wenn das Recordset nach dem letzten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.|
|[CRecordset::IsFieldDirty](#isfielddirty)|Gibt, die ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|
|[CRecordset::IsFieldNull](#isfieldnull)|Ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz null wird zurückgegeben (hat kein Wert).|
|[CRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz auf null festgelegt werden kann (mit keinen Wert) zurück.|
|[CRecordset::IsOpen](#isopen)|Ungleich NULL zurück, wenn `Open` wurde zuvor aufgerufen.|
|[CRecordset](#move)|Positioniert das Recordset auf eine angegebene Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|
|[CRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz für den ersten Datensatz im Recordset. Test für `IsBOF` erste.|
|[CRecordset::MoveLast](#movelast)|Positioniert den aktuellen Datensatz an, auf den letzten Datensatz oder des letzten Rowsets. Test für `IsEOF` erste.|
|[CRecordset::MoveNext](#movenext)|Positioniert den aktuellen Datensatz an, auf den nächsten Datensatz oder des nächsten Rowsets. Test für `IsEOF` erste.|
|[CRecordset::MovePrev](#moveprev)|Positioniert den aktuellen Datensatz an, auf den vorherigen Datensatz oder auf der vorherigen Rowsets. Test für `IsBOF` erste.|
|[CRecordset::OnSetOptions](#onsetoptions)|Wird zum Festlegen von Optionen, die (über Auswahl verwendet) für die angegebene ODBC-Anweisung aufgerufen.|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Zum Festlegen von Optionen (Update verwendet) für die angegebene ODBC-Anweisung aufgerufen.|
|[CRecordset:: Open](#open)|Öffnet das Recordset, indem die Tabelle abgerufen oder die vom Recordset darstellte Abfrage durchgeführt wird.|
|[CRecordset::RefreshRowset](#refreshrowset)|Aktualisiert die Daten und Status die angegebene(n) Zeile(n).|
|[CRecordset](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|
|[CRecordset:: SetAbsolutePosition auf](#setabsoluteposition)|Positioniert das Recordset für den Datensatz, der angegebene Datensatz-Anzahl entspricht.|
|[CRecordset::SetBookmark](#setbookmark)|Positioniert das Recordset für den Datensatz, der vom Lesezeichen angegeben.|
|[CRecordset::SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz an, als geändert.|
|[CRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds in den aktuellen Datensatz auf null (kein Wert mit) fest.|
|[CRecordset::SetLockingMode](#setlockingmode)|Legt den Sperrmodus "vollständige" gesperrt (Standard) oder "vollständige" Sperren fest. Bestimmt, wie Datensätze für Updates gesperrt werden.|
|[CRecordset::SetParamNull](#setparamnull)|Legt den angegebenen Parameter auf null (kein Wert mit) fest.|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Positioniert den Cursor in der angegebenen Zeile im Rowset.|
|[CRecordset::SetRowsetSize](#setrowsetsize)|Gibt die Anzahl der Datensätze, die während der ein Abrufvorgang abgerufen werden sollen.|
|[CRecordset:: Update](#update)|Schließt eine `AddNew` oder `Edit` Vorgang, durch die neuen oder bearbeiteten Daten speichern, in der Datenquelle.|

### <a name="public-data-members"></a>Öffentliche Datenmember

|Name|Beschreibung|
|----------|-----------------|
|[M_hstmt](#m_hstmt)|Enthält die ODBC-Anweisungshandle für das Recordset. Geben Sie `HSTMT` ein.|
|[CRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember im Recordset. Geben Sie `UINT` ein.|
|[CRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in Recordsets. Geben Sie `UINT` ein.|
|[CRecordset::m_pDatabase](#m_pdatabase)|Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.|
|[CRecordset:: M_strfilter](#m_strfilter)|Enthält eine `CString` , der angibt, dass eine URL (SQL = Structured Query Language) `WHERE` Klausel. Als Filter verwendet, um nur die Datensätze auszuwählen, die bestimmte Kriterien erfüllen.|
|[CRecordset::m_strSort](#m_strsort)|Enthält eine `CString` , die angibt, dass einer SQL `ORDER BY` Klausel. Zum Steuern, wie die Datensätze sortiert werden.|

## <a name="remarks"></a>Hinweise

Bekannt als "Recordsets," `CRecordset` Objekte dienen in der Regel in zwei Formen: Dynasets und Momentaufnahmen. Ein Dynaset bleibt er von anderen Benutzern vorgenommene Aktualisierungen synchronisiert. Eine Momentaufnahme ist eine statische Ansicht der Daten. Jedes Formular stellt eine Gruppe von Datensätzen, die behoben werden, zu dem Zeitpunkt, die das Recordset geöffnet wird, aber wenn Sie einen Bildlauf zu einem Datensatz in einem Dynaset ausführen, gibt es Änderungen anschließend an den Datensatz, entweder durch andere Benutzer oder durch weitere Recordsets in Ihrer Anwendung.

> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt mit der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Overview: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).

Um mit den beiden Anwendungsarten Recordset arbeiten, leiten Sie in der Regel eine anwendungsspezifische Recordset-Klasse von `CRecordset`. Durch Recordsets Datensätze aus einer Datenquelle auswählen, und klicken Sie dann können Sie:

- Durch die Datensätze scrollen.

- Aktualisieren Sie der Datensätze, und geben Sie einen Sperrmodus.

- Filtern Sie das Recordset aus, um die Datensätze zu beschränken, für die Datenquelle aus den verfügbaren ausgewählt.

- Sortieren Sie das Recordset.

- Parametrisieren Sie das Recordset aus, um die Auswahl mit Informationen, die nicht bis zur Laufzeit bekannt anzupassen.

Um Ihre Klasse verwenden zu können, öffnen Sie eine Datenbank aus, und erstellen Sie ein Recordsetobjekt, und übergeben dem Konstruktor einen Zeiger auf Ihre `CDatabase` Objekt. Rufen Sie dann der Recordsets `Open` Member-Funktion, in dem Sie angeben können, ob das Objekt ein Dynaset oder eine Momentaufnahme ist. Aufrufen von `Open` wählt Daten aus der Datenquelle. Nach dem Öffnen des Recordset-Objekts verwenden Sie die Member-Funktionen und Datenmember, durch die Datensätze scrollen und auf ihnen ausgeführt werden. Die verfügbaren Vorgänge davon abhängen, ob das Objekt ein Dynaset oder eine Momentaufnahme ist, es aktualisierbar oder schreibgeschützt ist (Dies hängt die Fähigkeit von der Datenquelle für Open Database Connectivity (ODBC)), und gibt an, ob massenzeilenabruf implementiert haben. Um Datensätze zu aktualisieren, die möglicherweise wurde geändert oder hinzugefügt werden, da die `Open` aufzurufen, rufen Sie des Objekts `Requery` Member-Funktion. Aufrufen des Objekts `Close` Member Funktion, und das Objekt zerstört, wenn Sie damit fertig sind.

In einer abgeleiteten `CRecordset` Klasse, die Datensatzfeldaustausch (RFX) oder der Massen-Datensatzfeldaustausch (Bulk-RFX) wird verwendet, um das Lesen und Aktualisieren von Datensatzfeldern zu unterstützen.

Weitere Informationen über das Exchange-Recordsets und DNS-Feld finden Sie unter den Artikeln [Overview: Programmieren von Datenbank](../../data/data-access-programming-mfc-atl.md), [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md). Schwerpunkt auf Dynasets und Momentaufnahmen, finden Sie in den Artikeln [Dynaset](../../data/odbc/dynaset.md) und [Momentaufnahme](../../data/odbc/snapshot.md).

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

##  <a name="addnew"></a>  CRecordset::AddNew

Bereitet zum Hinzufügen eines neuen Datensatzes in die Tabelle.

```
virtual void AddNew();
```

### <a name="remarks"></a>Hinweise

Rufen Sie die [Requery](#requery) Memberfunktion versucht, die neu hinzugefügte Datensatz finden Sie unter. Der Felder, die ursprünglich Null sind. (Null, in der datenbankterminologie bedeutet "kein Wert having" und entspricht nicht der NULL-Wert in C++.) Um den Vorgang abzuschließen, müssen Sie den Aufrufen der [Update](#update) Member-Funktion. `Update` Speichert die Änderungen an die Datenquelle an.

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `AddNew`. Dies führt eine fehlgeschlagene Assertion. Obwohl Klasse `CRecordset` stellt keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, indem Sie mithilfe der ODBC-API-Funktion `SQLSetPos`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew` Bereitet eine neue, leere Datensatz, der mit dem Recordset Felddatenmembern vor. Nach dem Aufruf von `AddNew`, legen Sie die gewünschten Werte in die Recordset Felddatenmembern. (Sie müssen keine rufen Sie die [bearbeiten](#edit) Memberfunktion zu diesem Zweck; verwenden Sie stattdessen `Edit` nur für vorhandene Datensätze.) Wenn Sie anschließend einen Aufruf `Update`, geänderte Werte in den Felddatenmembern in der Datenquelle gespeichert sind.

> [!CAUTION]
>  Wenn Sie vor dem Aufruf an einen neuen Datensatz Scrollen `Update`des neuen Eintrags geht verloren, und keine Warnung ausgegeben.

Wenn die Datenquelle Transaktionen unterstützt, können Sie machen Ihre `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDatabase](../../mfc/reference/cdatabase-class.md). Beachten Sie, die Sie aufrufen sollten [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf `AddNew`.

> [!NOTE]
>  Neue Datensätze werden für Dynasets als letzten Datensatz des Recordsets hinzugefügt. Hinzugefügte Datensätze werden nicht für Momentaufnahmen hinzugefügt. Rufen Sie `Requery` das Recordset zu aktualisieren.

Es ist nicht zulässig, rufen Sie `AddNew` für ein Recordset, deren `Open` Memberfunktion nicht aufgerufen wurde. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen `AddNew` für ein Recordset, die an kann nicht angefügt. Sie können bestimmen, ob das Recordset aktualisierbar, durch den Aufruf ist [CanAppend](#canappend).

Weitere Informationen finden Sie unter den folgenden Artikeln: [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), und [Transaktion () ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Beispiel

Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="canappend"></a>  CRecordset::CanAppend

Bestimmt, ob das zuvor geöffnete Recordset Sie neue Datensätze hinzufügen kann.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset ermöglicht neue Datensätze hinzufügen; andernfalls 0. `CanAppend` Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet.

##  <a name="canbookmark"></a>  CRecordset:: CanBookmark

Bestimmt, ob das Recordset Sie Datensätze, die mithilfe von Lesezeichen markieren kann.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset Lesezeichen unterstützt; andernfalls 0.

### <a name="remarks"></a>Hinweise

Diese Funktion ist unabhängig von der `CRecordset::useBookmarks` option die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion. `CanBookmark` Gibt an, ob die angegebene ODBC-Treiber und der Cursor unterstützt Lesezeichen eingeben. `CRecordset::useBookmarks` Gibt an, ob Lesezeichen verfügbar sein soll, sofern diese unterstützt werden.

> [!NOTE]
>  Lesezeichen werden auf die Forward-only-Recordsets nicht unterstützt.

Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cancel"></a>  CRecordset::Cancel

Fordert an, dass die Datenquelle entweder ein asynchroner Vorgang ausgeführt wird oder einen Prozess aus einem zweiten Thread abzubrechen.

```
void Cancel();
```

### <a name="remarks"></a>Hinweise

Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt die ODBC-API-Funktion aufrufen `SQLSetConnectOption`. Weitere Informationen finden Sie im Thema "Funktionen asynchron ausführen" in der *ODBC SDK Handbuch für Programmierer*.

##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate

Bricht alle ausstehenden Updates, die aufgrund einer [bearbeiten](#edit) oder [AddNew](#addnew) -Vorgang vor dem [Update](#update) aufgerufen wird.

```
void CancelUpdate();
```

### <a name="remarks"></a>Hinweise

> [!NOTE]
>  Diese Memberfunktion ist nicht anwendbar auf Recordsets, das gesammelte, da solche Recordsets nicht aufrufen können verwenden `Edit`, `AddNew`, oder `Update`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Wenn die automatische Überprüfung fehlerhafter Felder aktiviert ist, `CancelUpdate` stellen die Membervariablen auf die Werte, die sie zuvor `Edit` oder `AddNew` war aufgerufen; andernfalls, alle Änderungen bleiben. Automatische Feld zu überprüfen ist standardmäßig aktiviert, wenn das Recordset geöffnet wird. Um es zu deaktivieren, müssen Sie angeben der `CRecordset::noDirtyFieldCheck` in die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion.

Weitere Informationen zum Aktualisieren von Daten finden Sie im Artikel [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).

##  <a name="canrestart"></a>  CRecordset::CanRestart

Bestimmt, ob das Recordset ermöglicht das Neustarten der Abfrage (Wenn Sie die Datensätze zu aktualisieren) durch Aufrufen der `Requery` Member-Funktion.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn Requery zulässig ist; andernfalls 0.

##  <a name="canscroll"></a>  CRecordset::CanScroll

Bestimmt, ob das Recordset ermöglicht das Durchführen eines Bildlaufs.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset ermöglicht das Durchführen eines Bildlaufs; andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen zu scrollen, finden Sie im Artikel [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cantransact"></a>  CRecordset::CanTransact

Bestimmt, ob das Recordset Transaktionen ermöglicht.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset Transaktionen ermöglicht; andernfalls 0.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>  CRecordset::CanUpdate

Bestimmt, ob das Recordset aktualisiert werden kann.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset aktualisiert werden kann; andernfalls 0.

### <a name="remarks"></a>Hinweise

Ein Recordset kann schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist, oder wenn Sie angegeben haben `CRecordset::readOnly` in die *DwOptions* Parameter an, wenn Sie das Recordset geöffnet.

##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError

Wird aufgerufen, zur Behandlung von Fehlern, die während des Abrufens der Datensatz generiert.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Parameter

*nRetCode*<br/>
Rückgabecode für eine ODBC-API-Funktion. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Dieser virtuelle Memberfunktion behandelt Fehler, die auftreten, wenn Datensätze abgerufen wurden, und eignet sich während des Abrufens von Zeilen. Möglicherweise sollten überschreiben möchten `CheckRowsetError` eigene Fehlerbehandlung implementieren.

`CheckRowsetError` wird automatisch aufgerufen, in ein Navigationsvorgang Cursor, wie z. B. `Open`, `Requery`, oder ein beliebiges `Move` Vorgang. Es wird den Rückgabewert von der ODBC-API-Funktion übergeben `SQLExtendedFetch`. Die folgende Tabelle enthält die möglichen Werte für die *nRetCode* Parameter.

|nRetCode|Beschreibung|
|--------------|-----------------|
|SQL_SUCCESS|Die Funktion wurde erfolgreich abgeschlossen. Es ist keine zusätzlichen Informationen verfügbar.|
|SQL_SUCCESS_WITH_INFO|Die Funktion wurde erfolgreich abgeschlossen, möglicherweise mit einem nicht schwerwiegenden Fehler. Weitere Informationen erhalten Sie durch Aufrufen von `SQLError`.|
|SQL_NO_DATA_FOUND|Alle Zeilen aus dem Resultset wurden abgerufen.|
|SQL_ERROR|Fehler bei der Funktion. Weitere Informationen erhalten Sie durch Aufrufen von `SQLError`.|
|SQL_INVALID_HANDLE|Fehler bei der Funktion aufgrund einer ungültigen Umgebungshandle, Verbindungshandle oder Anweisungshandle. Dies weist einen Programmierungsfehler hin. Keine zusätzlichen Informationen steht in `SQLError`.|
|SQL_STILL_EXECUTING|Eine Funktion, die asynchron gestartet wurde, wird weiterhin ausgeführt. Beachten Sie, dass standardmäßig nie diesen Wert übergeben wird `CheckRowsetError`; MFC weiterhin aufrufen `SQLExtendedFetch` bis nicht mehr SQL_STILL_EXECUTING zurückgegeben.|

Weitere Informationen zu `SQLError`, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="close"></a>  CRecordset::Close

Schließt das Recordset.

```
virtual void Close();
```

### <a name="remarks"></a>Hinweise

Die ODBC HSTMT und den gesamten Speicher das Framework für das Recordset zugeordnet werden freigegeben. In der Regel nach dem Aufruf `Close`, wenn mit dem Speicher belegt wurde, löschen Sie das C++-Recordset-Objekt **neue**.

Rufen Sie `Open` erneut nach dem Aufruf `Close`. Dadurch können Sie die Wiederverwendung des Recordset-Objekts. Die Alternative ist das Aufrufen `Requery`.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

##  <a name="crecordset"></a>  CRecordset::CRecordset

Erstellt ein `CRecordset`-Objekt.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Parameter

*pDatabase*<br/>
Enthält einen Zeiger auf eine `CDatabase` Objekt oder den Wert NULL. Falls ungleich NULL und `CDatabase` des Objekts `Open` Memberfunktion nicht aufgerufen wurde, um es an die Datenquelle zu verbinden, versucht Sie, dass das Recordset es für Sie öffnen, während eine eigene `Open` aufrufen. Wenn Sie NULL übergeben eine `CDatabase` Objekt erstellt und verbunden sind, Sie verwenden die Datenquelleninformationen, die Sie angegeben, wenn Sie mit Klassen-Assistent-Recordset-Klasse abgeleitet ist.

### <a name="remarks"></a>Hinweise

Sie können entweder `CRecordset` direkt oder leiten Sie eine anwendungsspezifische Klasse von `CRecordset`. Klassen-Assistenten können Sie die Recordset-Klassen abgeleitet werden.

> [!NOTE]
>  Eine abgeleitete Klasse *müssen* seinen eigenen Konstruktor bereitstellen. Rufen Sie im Konstruktor einer abgeleiteten Klasse den Konstruktor `CRecordset::CRecordset`, die entsprechenden Parameter zusammen an sie übergibt.

Übergeben Sie NULL an Ihre recordsetkonstruktor haben eine `CDatabase` Objekt erstellt und für Sie automatisch verbunden. Dies ist eine nützliche kompakteigenschaft, die nicht erforderlich ist, erstellen und verbinden Sie ein `CDatabase` Objekt vor dem Erstellen eines Recordsets.

### <a name="example"></a>Beispiel

Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

##  <a name="delete"></a>  CRecordset::Delete

Löscht den aktuellen Datensatz.

```
virtual void Delete();
```

### <a name="remarks"></a>Hinweise

Nach einem erfolgreichen Löschvorgang, dem Recordset Felddatenmember werden auf einen Nullwert festgelegt, und Sie müssen explizit aufrufen eines der `Move` Funktionen, um den gelöschten Datensatz zu verschieben. Nachdem Sie aus dem gelöschten Datensatz verschoben haben, ist es nicht möglich, zurückzugeben. Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Delete` Teil einer Transaktion aufrufen. Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `Delete`. Dies führt eine fehlgeschlagene Assertion. Obwohl Klasse `CRecordset` stellt keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, indem Sie mithilfe der ODBC-API-Funktion `SQLSetPos`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
>  Muss das Recordset aktualisierbar sein und müssen ein gültiger Datensatz im Recordset aktuelle beim Aufrufen `Delete`ist, andernfalls ein Fehler auftritt. Z. B., wenn Sie einen Datensatz löschen, aber kein Bildlauf zu einem neuen Datensatz vor dem Aufruf `Delete` in diesem Fall `Delete` löst eine [CDBException](../../mfc/reference/cdbexception-class.md).

Im Gegensatz zu [AddNew](#addnew) und [bearbeiten](#edit), einen Aufruf von `Delete` folgt nicht durch einen Aufruf von [Update](#update). Wenn eine `Delete` Aufruf ein Fehler auftritt, die Felddaten Member bleiben unverändert.

### <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein Recordset, das auf den Rahmen einer Funktion erstellt. Im Beispiel wird davon ausgegangen, `m_dbCust`, eine Membervariable des Typs `CDatabase` bereits mit der Datenquelle verbunden ist.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange

Wird aufgerufen, zum Austauschen von Datenzeilen aus der Datenquelle auf das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird bereits dieses Objekts eingerichtet haben, einen Kontext für den Exchange-Vorgang Feld anzugeben.

### <a name="remarks"></a>Hinweise

Wenn massenzeilenabruf implementiert ist, ruft das Framework diese Memberfunktion zum Übertragen von Daten automatisch aus der Datenquelle auf das Recordsetobjekt. `DoBulkFieldExchange` Parameterdatenmember, bindet zudem ggf. Parameterplatzhalter in der SQL-Anweisung-Zeichenfolge für das Recordset Auswahl.

Wenn gesammelte nicht implementiert wird, um das Framework ruft [DoFieldExchange](#dofieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die *DwOptions* Parameter in der [öffnen](#open) Member-Funktion.

> [!NOTE]
> `DoBulkFieldExchange` ist nur verfügbar, wenn Sie eine Klasse, die von abgeleiteten verwenden `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, rufen Sie die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.

Sammel-Datensatzfeldaustausch (Bulk-RFX) ähnelt Datensatzfeldaustausch (RFX). Daten werden automatisch auf das Recordsetobjekt aus der Datenquelle übertragen. Rufen Sie jedoch nicht möglich `AddNew`, `Edit`, `Delete`, oder `Update` zur Übertragung von Änderungen an der Datenquelle. Klasse `CRecordset` derzeit keinen Mechanismus für die Aktualisierung von Datenzeilen; Sie können jedoch Ihre eigenen Funktionen schreiben, mit der ODBC-API-Funktion `SQLSetPos`.

Beachten Sie, dass massenaustausch von ClassWizard nicht unterstützt wird; aus diesem Grund müssen Sie überschreiben `DoBulkFieldExchange` manuell durch Aufrufe der Bulk-RFX-Funktionen zu schreiben. Weitere Informationen zu diesen Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).

Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="dofieldexchange"></a>  CRecordset:: DoFieldExchange

Wird aufgerufen, zum Austauschen von Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Parameter

*pFX*<br/>
Ein Zeiger auf eine [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird bereits dieses Objekts eingerichtet haben, einen Kontext für den Exchange-Vorgang Feld anzugeben.

### <a name="remarks"></a>Hinweise

Wenn gesammelte nicht implementiert ist, ruft das Framework diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern eines Recordset-Objekts und den entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch an. `DoFieldExchange` Parameterdatenmember, bindet zudem ggf. Parameterplatzhalter in der SQL-Anweisung-Zeichenfolge für das Recordset Auswahl.

Wenn massenzeilenabruf implementiert wird, um das Framework ruft [DoBulkFieldExchange](#dobulkfieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die *DwOptions* Parameter in der [öffnen](#open) Member-Funktion.

> [!NOTE]
> `DoFieldExchange` ist nur verfügbar, wenn Sie eine Klasse, die von abgeleiteten verwenden `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, rufen Sie die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.

Der Austausch von Felddaten, namens-Datensatzfeldaustausch (RFX), funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes für die Datenquelle, und aus dem Datensatz in der Datenquelle auf das Recordsetobjekt.

Die einzige Aktion, die normalerweise nötig sind, um implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse ist, erstellen Sie die Klasse mit dem Klassen-Assistenten, und geben Sie den Namen und Datentypen, der den Felddatenmembern. Sie können auch Code hinzufügen, in welche ClassWizard geschrieben, um Parameterdatenmember oder zur Behandlung von Spalten, die Sie dynamisch binden. Weitere Informationen finden Sie im Artikel [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

Wenn Sie mit Klassen-Assistent abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` für Sie das folgende Beispiel ähnelt:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

Weitere Informationen zu der RFX-Funktionen, finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).

Weitere Beispiele und Informationen zu `DoFieldExchange`, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Allgemeine Informationen über RFX finden Sie im Artikel [Record Field Exchange](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="edit"></a>  CRecordset::Edit

Ermöglicht Änderungen an den aktuellen Datensatz.

```
virtual void Edit();
```

### <a name="remarks"></a>Hinweise

Nach dem Aufruf von `Edit`, Sie können die Felddatenmembern ändern, indem Sie direkt auf ihre Werte zurücksetzen. Der Vorgang wurde abgeschlossen, wenn Sie anschließend einen Aufruf der [Update](#update) Member-Funktion, um die Änderungen für die Datenquelle zu speichern.

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `Edit`. Dies führt eine fehlgeschlagene Assertion. Obwohl Klasse `CRecordset` stellt keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, indem Sie mithilfe der ODBC-API-Funktion `SQLSetPos`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit` Speichert die Werte der Datenelemente des Recordsets. Wenn Sie aufrufen `Edit`, nehmen Änderungen vor, und rufen dann `Edit` in diesem Fall werden die Werte des Datensatzes vor dem ersten einstellungsänderungen wiederhergestellt `Edit` aufrufen.

In einigen Fällen möchten möglicherweise eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Zu diesem Zweck rufen [SetFieldNull](#setfieldnull) mit dem Parameter "true" markieren Sie das Feld Null; dies auch bewirkt, dass die Spalte aktualisiert werden. Wenn Sie möchten ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert wurde, rufen Sie [SetFieldDirty](#setfielddirty) mit dem Parameter "true". Dies funktioniert auch, wenn das Feld den Wert Null haben.

Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Edit` Teil einer Transaktion aufrufen. Beachten Sie, die Sie aufrufen sollten [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf `Edit` und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) ist kein Ersatz für den Aufruf `Update` zum Abschließen der `Edit` Vorgang. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).

Abhängig von der aktuellen Sperren, die zu aktualisierende Datensatz wird von gesperrt `Edit` bis zum Aufruf von `Update` , oder Scrollen Sie zu einem anderen Datensatz, oder er kann gesperrt werden, nur während der `Edit` aufrufen. Sie können ändern, dass der Sperrmodus mit [SetLockingMode](#setlockingmode).

Der vorherige Wert des aktuellen Datensatzes wird wiederhergestellt, wenn Sie einen Bildlauf zu einem neuen Datensatz vor dem Aufruf nach `Update`. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen `Edit` für ein Recordset, das nicht aktualisiert werden kann oder kein aktueller Datensatz vorhanden ist.

Weitere Informationen finden Sie in den Artikeln [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md) und [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

##  <a name="flushresultset"></a>  CRecordset::FlushResultSet

Ruft das nächste Resultset einer vordefinierten Abfrage (gespeicherten Prozedur) ab, wenn mehrere Resultsets vorhanden sind.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn es gibt mehrere Resultsets abgerufen werden sollen; andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie `FlushResultSet` nur wenn Sie mit dem Cursor auf das aktuelle Resultset vollständig abgeschlossen sind. Beachten Sie, dass, wenn Sie das nächste Resultset, der durch den Aufruf abrufen `FlushResultSet`, der Cursor gilt nicht für das Resultset, rufen Sie die [MoveNext](#movenext) Memberfunktion nach dem Aufruf `FlushResultSet`.

Wenn eine vordefinierte Abfrage ein Output-Parameter oder Eingabe/Ausgabe-Parameter verwendet, müssen Sie aufrufen `FlushResultSet` bis zurückgegeben `FALSE` (der Wert 0), um diese Werte zu erhalten.

`FlushResultSet` Ruft die ODBC-API-Funktion `SQLMoreResults`. Wenn `SQLMoreResults` gibt SQL_ERROR oder SQL_INVALID_HANDLE, klicken Sie dann `FlushResultSet` wird eine Ausnahme ausgelöst. Weitere Informationen zu `SQLMoreResults`, finden Sie im Windows SDK.

Die gespeicherte Prozedur muss Felder gebunden haben, wenn Sie aufrufen möchten `FlushResultSet`.

### <a name="example"></a>Beispiel

Der folgende Code setzt voraus, dass `COutParamRecordset` ist eine `CRecordset`-abgeleitetes Objekt basierend auf einer vordefinierten Abfrage mit einem Eingabeparameter und ein Output-Parameter, und dass mehrere Resultsets. Beachten Sie die Struktur der [DoFieldExchange](#dofieldexchange) außer Kraft setzen.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

##  <a name="getbookmark"></a>  CRecordset::GetBookmark

Ruft den Wert für das Lesezeichen für den aktuellen Datensatz ab.

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parameter

*varBookmark*<br/>
Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) Objekt, das das Lesezeichen für den aktuellen Datensatz darstellt.

### <a name="remarks"></a>Hinweise

Um festzustellen, ob Lesezeichen im Datensatz unterstützt werden, rufen Sie [CanBookmark](#canbookmark). Um Lesezeichen verfügbar machen, wenn sie unterstützt werden, müssen Sie festlegen der `CRecordset::useBookmarks` option die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion.

> [!NOTE]
>  Wenn das Lesezeichen nicht unterstützte oder nicht verfügbar sind, wird beim Aufrufen `GetBookmark` führt dazu, dass eine Ausnahme ausgelöst wird. Lesezeichen werden auf die Forward-only-Recordsets nicht unterstützt.

`GetBookmark` weist den Wert, der das Lesezeichen für den aktuellen Datensatz zu einer `CDBVariant` Objekt. Rufen Sie zum Zurückgeben an diesen Datensatz zu einem beliebigen Zeitpunkt nach dem Wechsel zu einem anderen Datensatz [SetBookmark](#setbookmark) mit dem entsprechenden `CDBVariant` Objekt.

> [!NOTE]
>  Lesezeichen können nach bestimmten Vorgängen Recordset nicht mehr gültig sein. Wenn Sie aufrufen, z. B. `GetBookmark` gefolgt von `Requery`, möglicherweise nicht auf den Datensatz mit zurückgeben `SetBookmark`. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.

Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="getdefaultconnect"></a>  GetDefaultConnect

Wird aufgerufen, um die Standardverbindungszeichenfolge zu erhalten.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die die standardmäßige Verbindungszeichenfolge enthält.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Member-Funktion, um die Standardverbindungszeichenfolge für die Datenquelle zu erhalten, auf dem das Recordset basiert. Klassen-Assistent implementiert diese Funktion für Sie durch das Identifizieren der gleiche Datenquelle, die Sie zum Abrufen von Informationen zu Tabellen und Spalten im Klassen-Assistenten zu verwenden. Wahrscheinlich werden finden Sie es sinnvoll, diese Verbindung standardmäßig während der Entwicklung Ihrer Anwendung abhängig. Aber die standardverbindung möglicherweise nicht für Benutzer Ihrer Anwendung geeignet. Wenn dies der Fall ist, sollten Sie diese Funktion erneut implementieren Verwerfen des Klassen-Assistent-Version. Weitere Informationen zu Verbindungszeichenfolgen finden Sie im Artikel [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md).

##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL

Wird aufgerufen, rufen Sie die Standard-SQL-Zeichenfolge ausgeführt wird.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Rückgabewert

Ein `CString` , die die Standard-SQL-Anweisung enthält.

### <a name="remarks"></a>Hinweise

Das Framework ruft diese Member-Funktion, um die Standard-SQL-Anweisung zu erhalten, auf der das Recordset basiert. Dies ist möglicherweise ein Tabellenname oder SQL **wählen** Anweisung.

Sie definieren die Standard-SQL-Anweisung indirekt durch Deklarieren des Recordset-Klasse mit dem Klassen-Assistenten, und der Klassen-Assistent führt diese Aufgabe für Sie.

Wenn Sie die SQL-Anweisung-Zeichenfolge für die eigene Verwendung benötigen, rufen Sie `GetSQL`, womit die SQL-Anweisung verwendet, um dem Recordset Datensätze ausgewählt werden soll, wenn es geöffnet wurde. Sie können die Standard-SQL-Zeichenfolge in Ihr die Überschreibung der Bearbeiten `GetDefaultSQL`. Beispielsweise können Sie angeben, einen Aufruf einer vordefinierten Abfrage mit einem **Aufrufen** Anweisung. (Beachten Sie, dass, auch wenn Sie jedoch bearbeiten `GetDefaultSQL`, müssen Sie auch ändern `m_nFields` mit der Anzahl der Spalten in der Datenquelle übereinstimmen.)

Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
>  Die wird als Tabellenname leer, wenn das Framework einen Tabellennamen ein, nicht identifizieren kann mehrere Tabellennamen zur Verfügung gestellt wurden, oder wenn eine **Aufrufen** Anweisung konnte nicht interpretiert werden. Beachten Sie, dass bei Verwendung einer **Aufrufen** -Anweisung darf kein Leerzeichen zwischen der geschweiften Klammer eingefügt und die **Aufrufen** -Schlüsselwort, noch sollte Sie Leerzeichen vor der geschweiften Klammer oder vor dem Einfügen der  **Wählen Sie** -Schlüsselwort in einer **wählen** Anweisung.

##  <a name="getfieldvalue"></a>  CRecordset:: GetFieldValue

Ruft die Feld-Daten in den aktuellen Datensatz ab.

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

*Wert*<br/>
Der Name eines Felds.

*VarValu*e ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) -Objekt, das der Wert des Felds gespeichert werden.

*nFieldType*<br/>
Der ODBC-C-Datentyp des Felds. Erzwingt die Verwendung des Standardwerts, DEFAULT_FIELD_TYPE, `GetFieldValue` basierend auf der folgenden Tabelle aus der SQL-Datentyp, den C-Datentyp zu ermitteln. Andernfalls können Sie angeben, die Daten direkt eingeben, oder wählen Sie einen kompatiblen Datentyp; Beispielsweise können Sie einen beliebigen Datentyp in SQL_C_CHAR speichern.

|C-Datentyp|SQL-Datentyp|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

Weitere Informationen zu ODBC-Datentypen finden Sie unter den Themen "SQL-Datentypen" und "C-Datentypen" in Anhang D des Windows SDK.

*nIndex*<br/>
Der nullbasierte Index des Felds.

*strValue gespeichert*<br/>
Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) Objekt, das der Wert des Felds zu speichern, wird in Text konvertiert, unabhängig vom Datentyp des Felds.

### <a name="remarks"></a>Hinweise

Sie können ein Feld nach Name oder Index nachschlagen. Sie können den Wert des Felds speichern, entweder in eine `CDBVariant` Objekt oder ein `CString` Objekt.

Wenn Sie die massenzeilenabruf implementiert haben, wird der aktuelle Datensatz immer für den ersten Datensatz in einem Rowset positioniert. Verwendung von `GetFieldValue` für einen Datensatz in ein angegebenes Rowset, müssen Sie zuerst Aufrufen der [SetRowsetCursorPosition](#setrowsetcursorposition) Memberfunktion versucht, den Cursor an der gewünschten Zeile innerhalb dieses Rowset besitzt verschieben. Rufen Sie anschließend `GetFieldValue` für diese Zeile. Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die *DwOptions* Parameter in der [öffnen](#open) Member-Funktion.

Sie können `GetFieldValue` dynamisch Felder auf statisch zur Entwurfszeit zu binden, statt zur Laufzeit abrufen. Angenommen, Sie direkt aus einem Recordset-Objekt deklariert haben `CRecordset`, verwenden Sie `GetFieldValue` zum Abrufen der Feld-Daten; die Datensatzfeldaustausch (RFX) oder die Massen-Datensatzfeldaustausch (Bulk-RFX), ist nicht implementiert.

> [!NOTE]
>  Wenn Sie einem Recordset-Objekt deklarieren, ohne eine Ableitung von `CRecordset`, müssen Sie nicht die ODBC-Cursorbibliothek geladen. Die Cursorbibliothek erfordert, dass das Recordset muss mindestens eine gebundene Spalte verfügen. Wenn Sie jedoch verwenden, `CRecordset` direkt keine der Spalten gebunden sind. Die Memberfunktionen [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) und [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) steuern, ob die Cursorbibliothek geladen werden.

`GetFieldValue` Ruft die ODBC-API-Funktion `SQLGetData`. Wenn der Treiber den Wert SQL_NO_TOTAL für die tatsächliche Länge des Feldwerts, gibt `GetFieldValue` löst eine Ausnahme aus. Weitere Informationen zu `SQLGetData`, finden Sie im Windows SDK.

### <a name="example"></a>Beispiel

Der folgende Beispielcode veranschaulicht Aufrufe `GetFieldValue` für die ein Recordset-Objekt direkt vom deklarierten `CRecordset`.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
>  Im Gegensatz zu den DAO-Klasse `CDaoRecordset`, `CRecordset` verfügt nicht über eine `SetFieldValue` Member-Funktion. Wenn Sie ein Objekt direkt vom Erstellen `CRecordset`, es ist absolut schreibgeschützt.

Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount

Ruft die Gesamtzahl der Felder in das Recordset-Objekt ab.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Felder im Recordset.

### <a name="remarks"></a>Hinweise

Weitere Informationen zum Erstellen von Recordsets finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo

Ruft Informationen über die Felder im Recordset.

```
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Parameter

*Wert*<br/>
Der Name eines Felds.

*FieldInfo*<br/>
Ein Verweis auf eine `CODBCFieldInfo` Struktur.

*nIndex*<br/>
Der nullbasierte Index des Felds.

### <a name="remarks"></a>Hinweise

Eine Version der Funktion können Sie ein Feld nach Namen zu suchen. Die andere Version können Sie ein Feld über einen Index zu suchen.

Eine Beschreibung zu den Informationen zurückgegeben werden soll, finden Sie unter den [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) Struktur.

Weitere Informationen zum Erstellen von Recordsets finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount

Bestimmt die Größe des Recordsets.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Datensätze im Recordset; 0, wenn das Recordset keine Datensätze enthält; oder -1, wenn die Anzahl der Datensätze nicht bestimmt werden kann.

### <a name="remarks"></a>Hinweise

> [!CAUTION]
>  Die Anzahl der Datensätze ist als eine "High Water Mark," der höchsten Datensatz beibehalten, aber dennoch angezeigt, wenn der Benutzer durch die Datensätze bewegt. Die Gesamtzahl der Datensätze ist nur bekannt, nachdem der Benutzer über den letzten Datensatz verschoben wurde. Zur Verbesserung der Leistung, die Anzahl wird nicht aktualisiert, wenn Sie aufrufen `MoveLast`. Aufrufen, um sich die Datensätze zu zählen, `MoveNext` solange wiederholt, bis `IsEOF` ungleich NULL zurückgibt. Hinzufügen eines Datensatzes über `CRecordset:AddNew` und `Update` erhöht die Anzahl; Löschen eines Datensatzes über `CRecordset::Delete` verringert die Anzahl die.

##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize

Ruft die aktuelle Einstellung für die Anzahl der Zeilen, die Sie während des angegebenen Fetch abrufen möchten.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeilen, die während der angegebenen Fetch abgerufen.

### <a name="remarks"></a>Hinweise

Wenn Sie gesammelte verwenden, ist die Rowsetgröße Standardwert, wenn das Recordset geöffnet wird 25; Andernfalls ist der Wert 1.

Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` option die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion. Um die Einstellung für die Größe des Rowsets zu ändern, rufen [SetRowsetSize](#setrowsetsize).

Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched

Bestimmt, wie viele Datensätze nach einer Fetch tatsächlich abgerufen wurden.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Rückgabewert

Die Anzahl der Zeilen, die einem Abrufvorgang aus der Datenquelle abgerufen werden.

### <a name="remarks"></a>Hinweise

Dies ist nützlich, wenn Sie die massenzeilenabruf implementiert haben. Die Größe des Rowsets gibt normalerweise an, wie viele Zeilen aus einem Abrufvorgang abgerufen werden; Allerdings wirkt sich auf die Gesamtanzahl der Zeilen im Recordset auch wie viele Zeilen in einem Rowset abgerufen werden. Beispielsweise verfügt das Recordset 10 Datensätze mit der Einstellung Rowset Größe von 4, klicken Sie dann durchlaufen des Recordset durch Aufrufen von `MoveNext` des letzten Rowsets mit nur 2 Datensätzen führt.

Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` option die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion. Rufen Sie zum Angeben der Rowsetgröße [SetRowsetSize](#setrowsetsize).

Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus

Der Status für eine Zeile im aktuellen Rowset abgerufen.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Parameter

*wRow*<br/>
Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.

### <a name="return-value"></a>Rückgabewert

Ein Statuswert für die Zeile. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

`GetRowStatus` Gibt ein Wert, der angibt, entweder Änderung in den Status der Zeile dass seit dem letzten abgerufen wird, aus der Datenquelle oder, die keine Zeile entspricht *wRow* wurde abgerufen. In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:

|Der Wert des Status|Beschreibung|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Die Zeile unverändert.|
|SQL_ROW_UPDATED|Die Zeile wurde aktualisiert.|
|SQL_ROW_DELETED|Die Zeile wurde gelöscht.|
|SQL_ROW_ADDED|Die Zeile wurde hinzugefügt.|
|SQL_ROW_ERROR|Die Zeile ist aufgrund eines Fehlers nicht abrufbar.|
|SQL_ROW_NOROW|Es gibt keine Zeile, die entspricht *wRow*.|

Weitere Informationen finden Sie in der ODBC-API-Funktion `SQLExtendedFetch` im Windows SDK.

##  <a name="getstatus"></a>  CRecordset::GetStatus

Bestimmt den Index des aktuellen Datensatzes in das Recordset und gibt an, ob der letzte Datensatz vorgekommen ist.

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Parameter

*rStatus*<br/>
Ein Verweis auf ein `CRecordsetStatus`-Objekt. Weitere Informationen finden Sie im Abschnitt Hinweise.

### <a name="remarks"></a>Hinweise

`CRecordset` versucht, den Index zu verfolgen, aber unter Umständen dadurch möglicherweise nicht möglich. Finden Sie unter [GetRecordCount](#getrecordcount) erläutert.

Die `CRecordsetStatus` Struktur weist folgende Form:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

Die beiden Member der `CRecordsetStatus` haben folgende Bedeutung:

- `m_lCurrentRecord` Den nullbasierten Index des aktuellen Datensatzes im Recordset enthält, sofern bekannt. Wenn der Index kann nicht bestimmt werden, enthält dieser Member AFX_CURRENT_RECORD_UNDEFINED (-2). Wenn `IsBOF` ist "true" (leere Datensatzgruppe oder wurde versucht, scrollen Sie vor dem ersten Datensatz), klicken Sie dann `m_lCurrentRecord` auf AFX_CURRENT_RECORD_BOF (-1) festgelegt ist. Wenn für den ersten Datensatz aus, klicken Sie dann es auf 0 festgelegt ist, Zweitens 1 aufzuzeichnen, und so weiter.

- `m_bRecordCountFinal` Ungleich NULL, wenn die Gesamtzahl der Datensätze im Recordset ermittelt wurde. Dies muss in der Regel erreicht werden, wobei am Anfang des Recordset-Objekts und Aufruf `MoveNext` bis `IsEOF` ungleich NULL zurückgibt. Wenn dieser Member 0 (null) ist, wird der Datensatz zählen, wie vom `GetRecordCount`, wenn nicht-1 ist, wird nur eine "High Water Mark" Anzahl von Datensätzen.

##  <a name="getsql"></a>  CRecordset::GetSQL

Rufen Sie diese Memberfunktion rufen Sie die SQL-Anweisung, die verwendet wurde, des Recordsets Datensätze auswählen, wenn sie geöffnet wurde.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Verweis auf eine `CString` , die die SQL-Anweisung enthält.

### <a name="remarks"></a>Hinweise

Diese werden in der Regel eine SQL **wählen** Anweisung. Die Zeichenfolge, die vom `GetSQL` ist schreibgeschützt.

Die Zeichenfolge, die vom `GetSQL` unterscheidet sich in der Regel von einer beliebigen Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die *LpszSQL* Parameter, um die `Open` Member-Funktion. Dies ist, da das Recordset eine vollständige SQL-Anweisung, die basierend erstellt auf der Sie übergeben `Open`, angegebene Klassen-Assistent, was Sie in angegeben haben möglicherweise die `m_strFilter` und `m_strSort` Datenmember und alle Parameter, die Sie möglicherweise angegeben. Details wie das Recordset wird erstellt, diese SQL-Anweisung finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

> [!NOTE]
>  Rufen Sie nur nach dem Aufruf dieser Memberfunktion [öffnen](#open).

##  <a name="gettablename"></a>  CRecordset::GetTableName

Ruft den Namen der SQL-Tabelle auf der die Abfrage des Recordsets basiert.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Rückgabewert

Ein **const** Verweis auf eine `CString` , die in der Tabelle enthält name, wenn das Recordset ist in einer Tabelle basiert, andernfalls eine leere Zeichenfolge.

### <a name="remarks"></a>Hinweise

`GetTableName` ist nur gültig, wenn das Recordset für eine Tabelle keine Verknüpfung von mehreren Tabellen oder eine vordefinierte Abfrage (gespeicherten Prozedur) basiert. Der Name ist schreibgeschützt.

> [!NOTE]
>  Rufen Sie nur nach dem Aufruf dieser Memberfunktion [öffnen](#open).

##  <a name="isbof"></a>  CRecordset::IsBOF

Gibt, die ungleich NULL, wenn das Recordset vor dem ersten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset keine Datensätze enthält, oder wenn Sie kein Bildlauf rückwärts vor dem ersten Datensatz durchgeführt haben; andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf von Datensatz zu Datensatz darüber, ob Sie vor dem ersten Datensatz des Recordsets durchgeführt haben. Sie können auch `IsBOF` zusammen mit `IsEOF` bestimmen, ob das Recordset keine Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von `Open`, wenn keine Datensätze, das Recordset enthält `IsBOF` ungleich NULL zurückgibt. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz den aktuellen Datensatz und `IsBOF` gibt 0 zurück.

Wenn der erste Datensatz der aktuelle Datensatz ist ein, und Sie rufen `MovePrev`, `IsBOF` anschließend ungleich NULL zurück. Wenn `IsBOF` ungleich Null gibt und Sie rufen `MovePrev`, ein Fehler auftritt. Wenn `IsBOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und jede Aktion, die einen aktuellen Datensatz erforderlich sind, führt zu einem Fehler.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet `IsBOF` und `IsEOF` die Grenzen eines Recordsets zu erkennen, wenn der Code durch das Recordset in beide Richtungen einen Bildlauf durchführt.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

##  <a name="isdeleted"></a>  CRecordset::IsDeleted

Bestimmt, ob der aktuelle Datensatz gelöscht wurde.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das Recordset auf einen gelöschten Datensatz positioniert ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Wenn Sie auf einen Datensatz scrollen und `IsDeleted` gibt "true" (ungleich null), und Sie müssen einen Bildlauf zu einem anderen Datensatz, bevor Sie alle anderen Recordset-Vorgänge ausführen können.

Das Ergebnis des `IsDeleted` hängt von vielen Faktoren ab, wie z. B. den Recordsettyp, ob das Recordset aktualisierbar ist, ist, ob die angegebene die `CRecordset::skipDeletedRecords` option, wenn Sie den Recordset geöffnet wird, ob Ihre Treiber Packs Datensätze gelöscht, und ob vorhanden sind mehrere Benutzer.

Weitere Informationen zu `CRecordset::skipDeletedRecords` und Treiber, packen, finden Sie unter den [öffnen](#open) Member-Funktion.

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, sollten Sie nicht aufrufen `IsDeleted`. Rufen Sie stattdessen die [GetRowStatus](#getrowstatus) Member-Funktion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="iseof"></a>  CRecordset::IsEOF

Gibt, die ungleich NULL, wenn das Recordset nach dem letzten Datensatz positioniert ist. Es ist kein aktueller Datensatz vorhanden.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset keine Datensätze enthält, oder Sie hinter dem letzten Datensatz gescrollt haben; andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion auf, wie Sie einen Bildlauf von Datensatz zu Datensatz darüber, ob Sie den letzten Datensatz des Recordsets überschritten haben. Sie können auch `IsEOF` bestimmen, ob das Recordset keine Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von `Open`, wenn keine Datensätze, das Recordset enthält `IsEOF` ungleich NULL zurückgibt. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz den aktuellen Datensatz und `IsEOF` gibt 0 zurück.

Wenn der letzte Datensatz beim Aufrufen des aktuellen Datensatzes ist `MoveNext`, `IsEOF` anschließend ungleich NULL zurück. Wenn `IsEOF` ungleich Null gibt und Sie rufen `MoveNext`, ein Fehler auftritt. Wenn `IsEOF` ungleich NULL zurückgegeben wird, der aktuelle Datensatz nicht definiert ist, und jede Aktion, die einen aktuellen Datensatz erforderlich sind, führt zu einem Fehler.

### <a name="example"></a>Beispiel

Siehe das Beispiel für [IsBOF](#isbof).

##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty

Bestimmt, ob der angegebene Feld den Datenmember seit geändert wurde [bearbeiten](#edit) oder [AddNew](#addnew) aufgerufen wurde.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder geändert werden.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn der angegebene Feld-Datenmember, seit dem Aufrufen geändert wurde `AddNew` oder `Edit`, andernfalls 0.

### <a name="remarks"></a>Hinweise

Die Daten in alle Felddatenmember übertragen werden sollen den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der [Update](#update) Memberfunktion `CRecordset` (nach einem Aufruf von `Edit` oder `AddNew`).

> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die Massenabrufen verwenden. Wenn Sie das gesammelte, klicken Sie dann implementiert haben `IsFieldDirty` immer "false" zurück und führt dazu, eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Aufrufen von `IsFieldDirty` setzt die Auswirkungen vorheriger Aufrufe [SetFieldDirty](#setfielddirty) seit der geänderten Status der das Feld neu ausgewertet wird. In der `AddNew` Fall der Pseudo-null-Wert, der aktuellen Feldwert unterscheidet der Feldstatus wird festgelegt, wenn geändert. In der `Edit` Fall, wenn der Wert des Felds aus den zwischengespeicherten Wert unterscheidet, wird der Status für das Feld geändert festgelegt.

`IsFieldDirty` wird durch implementiert [DoFieldExchange](#dofieldexchange).

Weitere Informationen zu den dirty-Flag, finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull

Ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz Null wird zurückgegeben (hat kein Wert).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder Null sind.

### <a name="return-value"></a>Rückgabewert

Ungleich NULL ist, wenn das angegebene Feld-Daten-Element, als Null gekennzeichnet ist; andernfalls 0.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember eines Recordset-Objekts als Null gekennzeichnet wurde. (Null, in der datenbankterminologie bedeutet "kein Wert having" und entspricht nicht der NULL-Wert in C++.) Wenn ein Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte mit den aktuellen Datensatz interpretiert für die kein Wert vorhanden ist.

> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die Massenabrufen verwenden. Wenn Sie das gesammelte, klicken Sie dann implementiert haben `IsFieldNull` immer "false" zurück und führt dazu, eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull` wird durch implementiert [DoFieldExchange](#dofieldexchange).

##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable

Gibt einen ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz auf Null festgelegt werden kann (mit keinen Wert) zurück.

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Ein Zeiger auf den Felddatenmember, deren Status zu überprüfen, oder NULL, um zu bestimmen, ob eines der Felder auf einen Null-Wert festgelegt werden kann.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion, um festzustellen, ob das angegebene Feld-Datenelement "NULL" ist (möglicherweise auf einen Null-Wert festgelegt NULL in C++ ist nicht identisch mit Null, womit, in der datenbankterminologie "having kein Wert").

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `IsFieldNullable`. Rufen Sie stattdessen die [GetODBCFieldInfo](#getodbcfieldinfo) Memberfunktion, um zu bestimmen, ob ein Feld auf einen Null-Wert festgelegt werden kann. Beachten Sie, die Sie, immer aufrufen können `GetODBCFieldInfo`, unabhängig davon, ob massenzeilenabruf implementiert haben. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, ein solches Feld auf Null, die beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und [aktualisieren](#update) wird eine Ausnahme ausgelöst. Die Ausnahme tritt auf, beim Aufrufen `Update`, nicht beim Aufrufen [SetFieldNull](#setfieldnull).

Verwenden NULL für das erste Argument der Funktion nur für die Funktion angewendet wird `outputColumn` Feldern nicht `param` Felder. Z. B. der Aufruf

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

wird nur festgelegt, `outputColumn` Felder NULL. `param` Felder nicht betroffen.

Auf `param` Felder müssen Sie angeben, die tatsächliche Adresse der Person, die `param` , z. B. arbeiten möchten:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Dies bedeutet, dass Sie nicht alle festlegen `param` Felder für NULL-Werte, mit `outputColumn` Felder.

`IsFieldNullable` wird durch implementiert [DoFieldExchange](#dofieldexchange).

##  <a name="isopen"></a>  CRecordset::IsOpen

Bestimmt, ob das Recordset noch geöffnet ist.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich Null des Recordset-Objekts [öffnen](#open) oder [Requery](#requery) Member-Funktion wurde zuvor aufgerufen und das Recordset nicht geschlossen wurde; andernfalls 0.

##  <a name="m_hstmt"></a>  M_hstmt

Enthält ein Handle für die ODBC-Anweisung Datenstruktur, des Typs Befehls beschäftigt, das Recordset zugeordnet.

### <a name="remarks"></a>Hinweise

Jede Abfrage mit einer ODBC-Datenquelle ist eine Befehls beschäftigt zugeordnet.

> [!CAUTION]
>  Verwenden Sie keine `m_hstmt` vor [öffnen](#open) aufgerufen wurde.

Normalerweise Sie müssen nicht den Befehls beschäftigt direkt zugreifen, aber Sie möglicherweise benötigen sie für die direkte Ausführung von SQL-Anweisungen. Die `ExecuteSQL` Memberfunktion der Klasse `CDatabase` enthält ein Beispiel der Verwendung von `m_hstmt`.

##  <a name="m_nfields"></a>  CRecordset::m_nFields

Enthält die Anzahl der Felddatenmember der Recordset-Klasse. d. h. die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.

### <a name="remarks"></a>Hinweise

Der Konstruktor für das Recordset-Klasse muss initialisiert werden `m_nFields` mit der richtigen Anzahl. Wenn Sie die gesammelte nicht implementiert haben, schreibt Klassen-Assistent diese Initialisierung für Sie aus, wenn Sie es verwenden, um die Recordset-Klasse zu deklarieren. Sie können es auch manuell schreiben.

Das Framework verwendet diese Zahl zum Verwalten der Interaktion zwischen den Felddatenmembern und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle.

> [!CAUTION]
>  Diese Zahl muss entsprechen, die Spaltenanzahl "Ausgabe" in registriert die `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit dem Parameter `CFieldExchange::outputColumn`.

Sie können Spalten, wie in diesem Artikel erläutert, dynamisch binden "Recordset: dynamisch Datenspalten für die Bindung." Wenn Sie dies tun, müssen Sie die Anzahl die in erhöhen `m_nFields` entsprechend der Anzahl der RFX- oder der Bulk-RFX-Funktion aufruft, Ihre `DoFieldExchange` oder `DoBulkFieldExchange` Memberfunktion für die dynamisch gebundenen Spalten.

Weitere Informationen finden Sie in den Artikeln [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

Finden Sie im Artikel [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_nparams"></a>  CRecordset::m_nParams

Enthält die Anzahl der Parameter-Datenelemente im Recordset-Klasse. übergeben die Anzahl von Parametern, also mit der Abfrage des Recordsets.

### <a name="remarks"></a>Hinweise

Wenn Recordset-Klasse keine Parameter statischen Datenmember verfügt, muss der Konstruktor für die Klasse initialisiert `m_nParams` mit der richtigen Anzahl. Der Wert des `m_nParams` hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen (die Sie manuell ausführen müssen) müssen Sie eine Initialisierung auch manuell hinzufügen, in den Konstruktor der Klasse, entsprechend die Anzahl von Parametern (die muss mindestens so groß wie die Anzahl der "Platzhalter in Ihre `m_strFilter` oder `m_strSort`Zeichenfolge).

Das Framework verwendet diese Zahl an, wenn sie die Abfrage des Recordsets parametrisiert.

> [!CAUTION]
>  Diese Zahl muss entsprechen, die Anzahl der "Params" in registriert die `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit einem Parameterwert der `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, oder `CFieldExchange::inoutParam`.

### <a name="example"></a>Beispiel

  Finden Sie in den Artikeln [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) und [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase

Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.

### <a name="remarks"></a>Hinweise

Diese Variable wird auf zwei Arten festgelegt werden. In der Regel, übergeben Sie einen Zeiger auf ein bereits verbundenen `CDatabase` -Objekt beim Erstellen des Recordsetobjekts. Wenn Sie stattdessen, NULL übergeben `CRecordset` erstellt eine `CDatabase` -Objekt für Sie und verbindet ihn. In beiden Fällen `CRecordset` der Zeiger in dieser Variable gespeichert.

Normalerweise Sie nicht direkt benötigen, verwenden Sie den Zeiger, der in gespeicherten `m_pDatabase`. Wenn Sie Ihre eigenen Erweiterungen schreiben `CRecordset`, allerdings müssen möglicherweise den Zeiger zu verwenden. Z. B. möglicherweise den Zeiger, wenn Sie lösen eigene `CDBException`s. Oder vielleicht benötigen Sie es bei Bedarf zu einer Aktion mit dem gleichen `CDatabase` Objekt, z. B. Transaktionen, Festlegen von Timeouts, ausführen oder das Aufrufen der `ExecuteSQL` Memberfunktion der Klasse `CDatabase` , SQL-Anweisungen direkt auszuführen.

##  <a name="m_strfilter"></a>  CRecordset:: M_strfilter

Nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf der `Open` Member funktioniert, verwenden Sie zum Speichern dieses Datenelement eine `CString` mit einer SQL **, in denen** Klausel.

### <a name="remarks"></a>Hinweise

Das Recordset wird diese Zeichenfolge verwendet, es während der wählt, Datensätze einschränken (oder Filtern) den `Open` oder `Requery` aufrufen. Dies ist nützlich für die Auswahl einer Teilmenge der Datensätze, wie z. B. "alle Vertriebsmitarbeiter in Kalifornien, USA basierte" ("State = CA"). Die ODBC-SQL-Syntax für eine **, in denen** -Klausel

`WHERE search-condition`

Beachten Sie, die Sie nicht einschließen, die **, in denen** Schlüsselwort in der Zeichenfolge. Das Framework stellt es bereit.

Sie können auch der Filterzeichenfolge parametrisieren, indem Sie platzieren '' Platzhalter, deklarieren einen Parameter-Datenmember in der Klasse für jeden Platzhalter, und übergeben von Parametern an den Recordset zur Laufzeit. Dadurch können Sie die Filter zur Laufzeit zu erstellen. Weitere Informationen finden Sie im Artikel [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Weitere Informationen zu SQL **, in denen** Klauseln finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum auswählen und Filtern von Datensätzen finden Sie im Artikel [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

##  <a name="m_strsort"></a>  CRecordset::m_strSort

Nach dem Erstellen des Recordsetobjekts, aber vor dem Aufruf der `Open` Member funktioniert, verwenden Sie zum Speichern dieses Datenelement eine `CString` mit einer SQL **ORDER BY** Klausel.

### <a name="remarks"></a>Hinweise

Das Recordset verwendet diese Zeichenfolge, die Datensätze sortiert, es während wählt, der `Open` oder `Requery` aufrufen. Sie können dieses Feature verwenden, um ein Recordset in einem oder mehreren Spalten sortieren. Die ODBC-SQL-Syntax für eine **ORDER BY** -Klausel

`ORDER BY sort-specification [, sort-specification]...`

wobei ist eine Art-Spezifikation eine ganze Zahl oder einen Spaltennamen an. Sie können auch die aufsteigende oder absteigende Reihenfolge (Standardmäßig ist die Reihenfolge aufsteigend) angeben, durch Anfügen von "ASC" oder "DESC" an der Liste der Spalten in der Sortierzeichenfolge. Die ausgewählten Datensätze werden zunächst nach der ersten Spalte aufgeführt, wird die zweite usw. sortiert. Sie können z. B. ein "Customers" Recordset nach Nachnamen und Vornamen, dann sortieren. Die Anzahl der Spalten, die Sie eintragen können, hängt von der Datenquelle ab. Weitere Informationen finden Sie im Windows-SDK.

Beachten Sie, die Sie nicht einschließen, die **ORDER BY** Schlüsselwort in der Zeichenfolge. Das Framework stellt es bereit.

Weitere Informationen zu SQL-Klauseln, finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum Sortieren von Datensätzen finden Sie im Artikel [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

##  <a name="move"></a>  CRecordset

Verschiebt die Zeiger für den aktuellen Datensatz im Recordset, entweder vorwärts oder rückwärts.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Parameter

*nRows*<br/>
Die Anzahl der Zeilen, die vorwärts oder rückwärts bewegen. Positive Werte vorwärts, zum Ende des Recordset-Objekts. Negative Werte werden zurück, bis zum Anfang verschieben.

*wFetchType*<br/>
Bestimmt das Rowset, `Move` abruft. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Wenn Sie den Wert 0 für übergeben *nRows*, `Move` aktualisiert den aktuellen Datensatz; `Move` wird beendet alle aktuelle `AddNew` oder `Edit` Modus, und stellen den aktuellen Datensatz Wert vor `AddNew` oder `Edit` aufgerufen wurde.

> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können Sie gelöschte Datensätze nicht überspringen. Finden Sie unter [CRecordset::IsDeleted](#isdeleted) für Weitere Informationen. Beim Öffnen einer `CRecordset` mit der `skipDeletedRecords` Optionssatz, `Move` bestätigt wird, wenn die *nRows* Parameter gleich 0 ist. Dieses Verhalten wird verhindert, dass die Aktualisierung von Zeilen, die von anderen Clientanwendungen, die mit denselben Daten gelöscht werden. Finden Sie unter den *DwOption* Parameter im [öffnen](#open) eine Beschreibung der `skipDeletedRecords`.

`Move` Verschiebt das Recordset von Rowsets. Anhand der Werte für *nRows* und *wFetchType*, `Move` wird das entsprechende Rowset abgerufen und dann wird der erste Datensatz in dieses Rowset besitzt den aktuellen Datensatz. Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, ist die Größe des Rowsets immer 1. Beim Abrufen eines Rowsets, `Move` ruft direkt die [CheckRowsetError](#checkrowseterror) Member-Funktion zum Behandeln von Fehlern, die sich aus der Abruf ergeben.

Abhängig von den Werten, die Sie übergeben, `Move` ist gleichbedeutend mit anderen `CRecordset` Memberfunktionen. Insbesondere für den Wert der *wFetchType* deuten auf eine Memberfunktion, die intuitiver und häufig die bevorzugte Methode zum Verschieben des aktuellen Datensatzes.

Die folgende Tabelle enthält die möglichen Werte für *wFetchType*, das Rowset, `Move` abrufen wird basierend auf *wFetchType* und *nRows*, und alle entsprechenden Member, die Funktion entspricht *wFetchType*.

|wFetchType|Abgerufenen Rowsets|Entsprechender Member-Funktion|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (Standardwert)|Das Rowset starten *nRows* Zeile(n) aus der ersten Zeile im aktuellen Rowset.||
|SQL_FETCH_NEXT|Das nächste Rowset. *nRows* wird ignoriert.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|Das vorherige Rowset. *nRows* wird ignoriert.|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|Das erste Rowset im Recordset. *nRows* wird ignoriert.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Die letzte vollständige Rowset im Recordset. *nRows* wird ignoriert.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|Wenn *nRows* > 0, der das Rowset ab *nRows* Zeilen vom Anfang des Recordset-Objekts. Wenn *nRows* < 0, der das Rowset ab *nRows* Zeilen vom Ende des Recordset-Objekts. Wenn *nRows* = 0 (null), und klicken Sie dann eine Bedingung der Anfang der Datei (BOF) zurückgegeben wird.|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Das Rowset ab, die in der Zeile, deren Wert für Lesezeichen entspricht *nRows*.|[SetBookmark](#setbookmark)|

> [!NOTE]
>  Für Forward-only-Recordsets `Move` ist nur gültig mit einem Wert von SQL_FETCH_NEXT für *wFetchType*.

> [!CAUTION]
>  Aufrufen von `Move` löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Um zu bestimmen, ob das Recordset alle Einträge verfügt, rufen Sie [IsBOF](#isbof) und [IsEOF](#iseof).

> [!NOTE]
>  Wenn Sie direkt hinter dem Anfang oder Ende des Recordset gescrollt haben (`IsBOF` oder `IsEOF` ungleich NULL zurückgibt), wird beim Aufruf einer `Move` Funktion löst möglicherweise eine `CDBException`. Z. B. wenn `IsEOF` ungleich NULL zurückgibt und `IsBOF` jedoch nicht, klicken Sie dann `MoveNext` löst eine Ausnahme, aber `MovePrev` nicht der Fall ist.

> [!NOTE]
>  Wenn Sie aufrufen `Move` während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Weitere Informationen zur Recordsetnavigation, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie unter der ODBC-API-Funktion `SQLExtendedFetch` im Windows SDK.

### <a name="example"></a>Beispiel

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

##  <a name="movefirst"></a>  CRecordset::MoveFirst

Wird der erste Datensatz in das erste Rowset den aktuellen Datensatz.

```
void MoveFirst();
```

### <a name="remarks"></a>Hinweise

Unabhängig davon, ob massenzeilenabruf implementiert wurde wird dies immer der erste Datensatz im Recordset sein.

Sie müssen keine Aufrufen `MoveFirst` sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt ist der erste Datensatz (sofern vorhanden) automatisch den aktuellen Datensatz.

> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.

> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können Sie gelöschte Datensätze nicht überspringen. Finden Sie unter den [IsDeleted](#isdeleted) Memberfunktion Details.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Um zu bestimmen, ob das Recordset alle Einträge verfügt, rufen Sie `IsBOF` und `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Weitere Informationen zur Recordsetnavigation, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [IsBOF](#isbof).

##  <a name="movelast"></a>  CRecordset::MoveLast

Wird der erste Datensatz in die letzte vollständige Rowset den aktuellen Datensatz.

```
void MoveLast();
```

### <a name="remarks"></a>Hinweise

Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, also `MoveLast` einfach wechselt zum letzten Datensatz im Recordset.

> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.

> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können Sie gelöschte Datensätze nicht überspringen. Finden Sie unter den [IsDeleted](#isdeleted) Memberfunktion Details.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Um zu bestimmen, ob das Recordset alle Einträge verfügt, rufen Sie `IsBOF` und `IsEOF`.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Weitere Informationen zur Recordsetnavigation, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [IsBOF](#isbof).

##  <a name="movenext"></a>  CRecordset::MoveNext

Wird der erste Datensatz in der nächsten Rowsets des aktuellen Datensatzes.

```
void MoveNext();
```

### <a name="remarks"></a>Hinweise

Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, also `MoveNext` einfach auf den nächsten Datensatz wechselt.

> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können Sie gelöschte Datensätze nicht überspringen. Finden Sie unter den [IsDeleted](#isdeleted) Memberfunktion Details.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Um zu bestimmen, ob das Recordset alle Einträge verfügt, rufen Sie `IsBOF` und `IsEOF`.

> [!NOTE]
>  Es wird empfohlen, dass Sie aufrufen `IsEOF` vor dem Aufruf `MoveNext`. Wenn Sie nach dem Ende des Recordset, gescrollt haben z. B. `IsEOF` ungleich NULL ist; gibt ein nachfolgender Aufruf von `MoveNext` würde eine Ausnahme auslösen.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Weitere Informationen zur Recordsetnavigation, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [IsBOF](#isbof).

##  <a name="moveprev"></a>  CRecordset::MovePrev

Wird der erste Datensatz in der vorherigen Rowsets des aktuellen Datensatzes.

```
void MovePrev();
```

### <a name="remarks"></a>Hinweise

Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, also `MovePrev` einfach wechselt zum vorherigen Datensatz.

> [!NOTE]
>  Diese Memberfunktion ist für die Forward-only-Recordsets ungültig.

> [!NOTE]
>  Wenn Sie über ein Recordset verschieben, können Sie gelöschte Datensätze nicht überspringen. Finden Sie unter den [IsDeleted](#isdeleted) Memberfunktion Details.

> [!CAUTION]
>  Aufrufen einer der der `Move` Funktionen löst eine Ausnahme aus, wenn das Recordset keine Einträge besitzt. Um zu bestimmen, ob das Recordset alle Einträge verfügt, rufen Sie `IsBOF` und `IsEOF`.

> [!NOTE]
>  Es wird empfohlen, dass Sie aufrufen `IsBOF` vor dem Aufruf `MovePrev`. Wenn Sie vor dem Anfang des Recordset, gescrollt haben z. B. `IsBOF` ungleich NULL ist; gibt ein nachfolgender Aufruf von `MovePrev` würde eine Ausnahme auslösen.

> [!NOTE]
>  Wenn Sie eine der Aufrufen der `Move` Funktionen während der aktuelle Datensatz wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung verloren gehen.

Weitere Informationen zur Recordsetnavigation, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Beispiel

  Siehe das Beispiel für [IsBOF](#isbof).

##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions

Wird zum Festlegen von Optionen, die (über Auswahl verwendet) für die angegebene ODBC-Anweisung aufgerufen.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parameter

*Befehls beschäftigt*<br/>
Die Befehls beschäftigt der ODBC-Anweisung sind, dass deren Optionen festgelegt werden.

### <a name="remarks"></a>Hinweise

Rufen Sie `OnSetOptions` (verwendete für Auswahl) Optionen für die angegebene ODBC-Anweisung festgelegt. Das Framework ruft diese Member-Funktion, um anfängliche Optionen für das Recordset festzulegen. `OnSetOptions` die Datenquelle unterstützt, scrollfähige Cursor und Cursorparallelität bestimmt und dem Recordset Optionen entsprechend festgelegt. (Während `OnSetOptions` dient zur Auswahlvorgänge, `OnSetUpdateOptions` wird für Updatevorgänge verwendet.)

Außer Kraft setzen `OnSetOptions` Optionen für den Treiber oder die Datenquelle spezifischen festlegen. Z. B. wenn die Datenquelle unterstützt, die für den exklusiven Zugriff geöffnet, Sie können außer Kraft gesetzt `OnSetOptions` diese Möglichkeit nutzen.

Weitere Informationen zu Cursorn finden Sie im Artikel [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions

Zum Festlegen von Optionen (Update verwendet) für die angegebene ODBC-Anweisung aufgerufen.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Parameter

*Befehls beschäftigt*<br/>
Die Befehls beschäftigt der ODBC-Anweisung sind, dass deren Optionen festgelegt werden.

### <a name="remarks"></a>Hinweise

Rufen Sie `OnSetUpdateOptions` (Update verwendete) Optionen für die angegebene ODBC-Anweisung festgelegt. Das Framework ruft diese Memberfunktion auf, nach dem Erstellen einer Befehls beschäftigt, um Daten in einem Recordset zu aktualisieren. (Während `OnSetOptions` dient zur Auswahlvorgänge, `OnSetUpdateOptions` wird für Updatevorgänge verwendet.) `OnSetUpdateOptions` bestimmt der Datenquelle unterstützt, scrollfähige Cursor und Cursorparallelität und dem Recordset Optionen entsprechend festgelegt.

Außer Kraft setzen `OnSetUpdateOptions` Optionen einer ODBC-Anweisung festgelegt wird, bevor die Anweisung für den Datenbankzugriff verwendet wird.

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

*nOpenType*<br/>
Akzeptieren Sie den Standardwert, AFX_DB_USE_DEFAULT_TYPE, oder verwenden Sie einen der folgenden Werte aus der `enum OpenType`:

- `CRecordset::dynaset` Ein Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets bestimmt. Die von anderen Benutzern an den Datenwerten vorgenommenen Änderungen sind nach einem Abrufvorgang allerdings sichtbar. Dynasets sind auch als keysetgesteuerte Recordsets bekannt.

- `CRecordset::snapshot` Ein statisches Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets und die Datenwerte beim Abrufen der Datensätze bestimmt. Die von anderen Benutzern vorgenommenen Änderungen sind nicht sichtbar, bis das Recordset geschlossen und erneut geöffnet wird.

- `CRecordset::dynamic` Ein Recordset mit bidirektionalem Bildlauf. Die von anderen Benutzern an der Mitgliedschaft, der Reihenfolge und den Datenwerten vorgenommen Änderungen sind nach einem Abrufvorgang sichtbar. Beachten Sie, dass dieser Recordsettyp von vielen ODBC-Treibern nicht unterstützt wird.

- `CRecordset::forwardOnly` Ein schreibgeschütztes Recordset mit Bildlauf ausschließlich vorwärts ausgeführt.

   Für `CRecordset`, der Standardwert ist `CRecordset::snapshot`. Mithilfe des Standardwertmechanismus kann bei Visual C++-Assistenten mit ODBC-`CRecordset` sowie DAO- `CDaoRecordset`, die über unterschiedliche Standardwerte verfügen, interagiert werden.

Weitere Informationen über diese Recordsettypen finden Sie im Artikel [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md). Weitere Informationen finden Sie im Artikel "Verwenden von Blocks und bildlauffähigen Cursorn" im Windows SDK.

> [!CAUTION]
>  Wenn der angeforderte Typ nicht unterstützt wird, löst das Framework eine Ausnahme aus.

*lpszSQL*<br/>
Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:

- Ein Nullzeiger.

- Name der Tabelle

- Eine SQL **wählen** Anweisung (optional mit einem SQL- **, in denen** oder **ORDER BY** Klausel).

- Ein **Aufrufen** Anweisung, die den Namen einer vordefinierten Abfrage (gespeicherten Prozedur) angeben. Achten Sie darauf, dass Sie kein Leerzeichen zwischen der geschweiften Klammer eingefügt werden und die **Aufrufen** Schlüsselwort.

Weitere Informationen zu dieser Zeichenfolge finden Sie in der Tabelle und der Diskussion über die Rolle von ClassWizard unter Hinweisen.

> [!NOTE]
>  Die Reihenfolge der Spalten im Resultset muss die Reihenfolge der RFX-entsprechen oder der Bulk-RFX-Funktionsaufrufe in Ihre [DoFieldExchange](#dofieldexchange) oder [DoBulkFieldExchange](#dobulkfieldexchange) Funktion außer Kraft setzen.

*dwOptions*<br/>
Eine Bitmaske, die eine Kombination der unten aufgeführten Werte angeben kann. Einige davon schließen sich einander aus. Der Standardwert ist **keine**.

- `CRecordset::none` Keine Optionen festgelegt. Dieser Parameterwert und alle anderen Werte schließen einander aus. Standardmäßig kann das Recordset mit aktualisiert werden [bearbeiten](#edit) oder [löschen](#delete) und ermöglicht das Anfügen von neuer Datensätzen mit [AddNew](#addnew). Aktualisierbarkeit hängt von der Datenquelle als auch auf die *nOpenType* Option, die Sie angeben. Optimierung für Massenhinzufügeaktionen ist nicht verfügbar. Das gesammelte Abrufen von Zeilen wird nicht implementiert. Gelöschte Datensätze werden während der Recordsetnavigation nicht übersprungen. Lesezeichen sind nicht verfügbar. Automatische Überprüfung fehlerhafter Felder wird implementiert.

- `CRecordset::appendOnly` Erlauben Sie keine `Edit` oder `Delete` im Recordset. Lassen Sie nur `AddNew` zu. Diese Option und `CRecordset::readOnly` schließen einander aus.

- `CRecordset::readOnly` Öffnen Sie das Recordset als schreibgeschützt. Diese Option und `CRecordset::appendOnly` schließen einander aus.

- `CRecordset::optimizeBulkAdd` Verwenden Sie eine vorbereitete SQL­Anweisung, um viele Datensätze auf einmal hinzufügen zu optimieren. Gilt nur, wenn Sie nicht die ODBC-API-Funktion verwenden `SQLSetPos` zum Aktualisieren des Recordsets. Das erste Update bestimmt die geänderten Felder. Diese Option und `CRecordset::useMultiRowFetch` schließen einander aus.

- `CRecordset::useMultiRowFetch` Implementieren Sie die gesammelte damit mehrere Zeilen in einem Abrufvorgang abgerufen werden kann. Das ist eine erweiterte Funktion, die zum Verbessern der Leistung entworfen wurde. Allerdings wird der Massenaustausch von Datensatzfeldern von ClassWizard nicht unterstützt. Diese Option und `CRecordset::optimizeBulkAdd` schließen einander aus. Beachten Sie, dass bei Angabe von `CRecordset::useMultiRowFetch`, klicken Sie dann die Option `CRecordset::noDirtyFieldCheck` wird automatisch aktiviert wird (doppelte Pufferung ist nicht verfügbar sein), auf die Forward-only-Recordsets, die Option `CRecordset::useExtendedFetch` wird automatisch aktiviert werden. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords` Bei der Navigation durch das Recordset alle gelöschten Datensätze zu überspringen. Das verlangsamt in bestimmten relativen Abrufen die Leistung. Diese Option ist bei forward-only-Recordsets ungültig. Wenn Sie aufrufen [verschieben](#move) mit der *nRows* Parameter auf 0 festgelegt, und die `CRecordset::skipDeletedRecords` option festgelegt ist, `Move` bestätigt. Beachten Sie, dass `CRecordset::skipDeletedRecords` ähnelt *treiberverpackung*, d. h., die Zeilen gelöscht werden aus dem Recordset entfernt. Wenn der Treiber allerdings Datensätze verpackt, werden nur die von Ihnen gelöschten Datensätze übersprungen. Die von anderen Benutzern gelöschten Datensätze werden nicht übersprungen, solange das Recordset geöffnet ist. `CRecordset::skipDeletedRecords` Überspringt die von anderen Benutzern gelöschten Zeilen.

- `CRecordset::useBookmarks` Lesezeichen kann für das Recordset verwendet werden, wenn unterstützt. Lesezeichen verlangsamen den Datenabruf, verbessern aber die Leistung bei der Datennavigation. In forward-only-Recordsets ist das ungültig. Weitere Informationen finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- `CRecordset::noDirtyFieldCheck` Deaktivieren Sie automatische fehlerhafter Felder überprüfen (doppelte Pufferung). Dadurch wird die Leistung verbessert. Sie müssen allerdings Felder manuell als geändert kennzeichnen, indem Sie die Memberfunktionen `SetFieldDirty` und `SetFieldNull` aufrufen. Beachten Sie, dass die doppelte Pufferung in der `CRecordset`-Klasse der doppelten Pufferung in der `CDaoRecordset`-Klasse ähnelt. Bei `CRecordset` können Sie die doppelte Pufferung allerdings nicht für einzelne Felder aktivieren. Sie können sie für alle Felder aktivieren oder deaktivieren. Beachten Sie, dass bei Angabe der Option `CRecordset::useMultiRowFetch`, klicken Sie dann `CRecordset::noDirtyFieldCheck` aktiviert wird, wird automatisch; allerdings `SetFieldDirty` und `SetFieldNull` kann nicht in Recordsets, die gesammelte implementieren verwendet werden.

- `CRecordset::executeDirect` Verwenden Sie eine vorbereitete SQL­Anweisung nicht. Zur Verbesserung der Leistung Geben Sie diese Option, wenn die `Requery` Memberfunktion wird nie aufgerufen werden.

- `CRecordset::useExtendedFetch` Implementieren `SQLExtendedFetch` anstelle von `SQLFetch`. Dies wurde für das Implementieren des gesammelten Abrufens von Zeilen in forward-only-Recordsets entworfen. Wenn Sie die Option `CRecordset::useMultiRowFetch` auf einer Forward-only-Recordset, klicken Sie dann `CRecordset::useExtendedFetch` wird automatisch aktiviert werden.

- `CRecordset::userAllocMultiRowBuffers` Der Benutzer belegt Speicherpuffer für die Daten. Verwenden Sie diese Option in Verbindung mit `CRecordset::useMultiRowFetch`, wenn Sie Ihren eigenen Speicher zuordnen möchten. Andernfalls ordnet wird der notwendigen Speicher vom Framework automatisch zugeordnet. Weitere Informationen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Beachten Sie, dass die Angabe `CRecordset::userAllocMultiRowBuffers` ohne `CRecordset::useMultiRowFetch` führt dazu, eine fehlgeschlagene Assertion.

### <a name="return-value"></a>Rückgabewert

Einen Wert ungleich null der `CRecordset` Objekt erfolgreich geöffnet wurde; andernfalls 0, wenn [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (sofern aufgerufen) 0 zurück.

### <a name="remarks"></a>Hinweise

Sie müssen diese Memberfunktion zum Ausführen der vom Recordset definierten Abfrage aufrufen. Vor dem Aufruf `Open`, müssen Sie das Recordset-Objekt erstellen.

Verbindung des Recordsets mit der Datenquelle, wie der Erstellung des Recordsets vor dem Aufruf hängt `Open`. Wenn Sie übergeben eine [CDatabase](../../mfc/reference/cdatabase-class.md) Objekt an den recordsetkonstruktor, die nicht mit der Datenquelle verbunden wurde, verwendet diese Memberfunktion [GetDefaultConnect](#getdefaultconnect) versucht, das Datenbankobjekt, das Öffnen. Wenn Sie NULL an den recordsetkonstruktor übergeben, wird der Konstruktor erstellt ein `CDatabase` Objekt für Sie und `Open` versucht, das Datenbankobjekt, das eine Verbindung herstellen. Ausführliche Informationen zum Schließen des Recordsets und die Verbindung in diesen unterschiedlichen Situationen, finden Sie unter [schließen](#close).

> [!NOTE]
>  Der Zugriff auf eine Datenquelle durch ein `CRecordset`-Objekt wird immer freigegeben. Anders als die `CDaoRecordset`-Klasse können Sie kein `CRecordset`-Objekt zum Öffnen einer Datenquelle mit exklusivem Zugriff verwenden.

Beim Aufruf `Open`, eine Abfrage, die in der Regel eine SQL **wählen** -Anweisung wählt die Datensätze auf Grundlage von Kriterien, die in der folgenden Tabelle gezeigt.

|Der Wert des lpszSQL-Parameters.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|
|------------------------------------|----------------------------------------|-------------|
|NULL|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||
|SQL-Tabellenname|Alle Spalten der Tabellenliste in `DoFieldExchange` oder `DoBulkFieldExchange`.|`"Customer"`|
|Der vordefinierte Name der Abfrage (gespeicherten Prozedur)|Die Spalten, zu denen die Abfrage per Definition zurückgibt.|`"{call OverDueAccts}"`|
|**Wählen Sie** Spaltenliste **FROM** Tabellenliste|Die angegebenen Spalten aus den angegebenen Tabellen.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
>  Achten Sie darauf, dass keine zusätzlichen Leerzeichen in der SQL-Zeichenfolge eingefügt werden. Z. B., wenn Sie die Leerzeichen zwischen der geschweiften Klammer einfügen und die **Aufrufen** MFC-Schlüsselwort, werden falsch interpretiert die SQL-Zeichenfolge als Tabellenname und bindet sie in einer **wählen** -Anweisung, die führt ein die Ausnahme ausgelöst wird. Auf ähnliche Weise, wenn vordefinierte Abfrage einen Output-Parameter verwendet, fügen Sie keine Leerzeichen zwischen der geschweiften Klammer und "Symbol. Schließlich darf kein eingefügt werden Leerzeichen vor der geschweiften Klammer in eine **Aufrufen** Anweisung oder vor der **wählen** -Schlüsselwort in eine **wählen** Anweisung.

Der üblichen Vorgehensweise wird zum Übergeben von NULL, um `Open`; in diesem Fall `Open` Aufrufe [GetDefaultSQL](#getdefaultsql). Wenn Sie eine abgeleitete arbeiten `CRecordset` -Klasse, `GetDefaultSQL` den bzw. die Sie in den Klassen-Assistenten angegeben haben. Sie können stattdessen andere Informationen im `lpszSQL`-Parameter angeben.

Jede Übergabe `Open` erstellt eine endgültige SQL-Zeichenfolge für die Abfrage (die Zeichenfolge möglicherweise die SQL **, in denen** und **ORDER BY** Klauseln angefügt, um die `lpszSQL` Sie übergebene Zeichenfolge) und führt dann die Abfrage. Sie können die erstellte Zeichenfolge überprüfen, durch den Aufruf [GetSQL](#getsql) nach dem Aufruf `Open`. Weitere Informationen darüber, wie das Recordset eine SQL-Anweisung erstellt und Auswahl von Datensätzen finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.

Wenn Sie Optionen für das Recordset, wie Sie einen Filter oder eine Sortierung festlegen möchten geben Sie diese nach der Erstellung des Recordset-Objekts, aber vor dem Aufruf `Open`. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie [Requery](#requery).

Weitere Informationen sowie weitere Beispiele finden Sie in den Artikeln [Recordsets (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), und [Recordset: Erstellen und schließen Durch Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Beispiel

Die folgenden Codebeispiele zeigen verschiedene Formen der der `Open` aufrufen.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset

Aktualisiert die Daten und den Status für eine Zeile im aktuellen Rowset.

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parameter

*wRow*<br/>
Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 0 (null), um die Größe des Rowsets liegen.

*wLockType*<br/>
Ein Wert, der angibt, wie Sie die Zeile gesperrt wird, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Wenn Sie den Wert 0 (null) für übergeben *wRow*, und klicken Sie dann jede Zeile im Rowset aktualisiert werden.

Mit `RefreshRowset`, muss implementierten gesammelte durch Angabe der `CRecordset::useMulitRowFetch` option die [öffnen](#open) Member-Funktion.

`RefreshRowset` Ruft die ODBC-API-Funktion `SQLSetPos`. Die *wLockType* Parameter gibt an, der Zustand der Zeile nach der Sperre `SQLSetPos` ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für *wLockType*.

|wLockType|Beschreibung|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (Standardwert)|Die Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in der gleichen gesperrt oder entsperrt Zustand wie vor `RefreshRowset` aufgerufen wurde.|
|SQL_LOCK_EXCLUSIVE|Die Treiber oder die Datenquelle wird ausschließlich die Zeile gesperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|
|SQL_LOCK_UNLOCK|Die Treiber oder die Datenquelle wird die Zeile entsperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|

Weitere Informationen zu `SQLSetPos`, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="requery"></a>  CRecordset

Wird neu erstellt (aktualisiert) einem Recordset.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn das Recordset erfolgreich neu erstellt wurde; andernfalls 0.

### <a name="remarks"></a>Hinweise

Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.

In der Reihenfolge für das Recordset entsprechend der Hinzufügungen und löschungen, die Sie oder andere Benutzer mit der Datenquelle vornehmen, müssen Sie das Recordset erstellen, durch Aufruf `Requery`. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer an die vorhandene Datensätze (aber nicht Additions) Stellen angezeigt. Wenn das Recordset eine Momentaufnahme ist, müssen Sie aufrufen `Requery` entsprechend der Änderungen von anderen Benutzern als auch Ergänzungen und löschungen.

Rufen Sie für ein Dynaset oder eine Momentaufnahme, `Requery` jederzeit das Recordset, das über einen neuen Filter oder sortieren oder neue Parameterwerte neu erstellen möchten. Legen Sie die neue Filter- oder Sortierausdruck-Eigenschaft durch Zuweisen von neuen Werten zu `m_strFilter` und `m_strSort` vor dem Aufruf `Requery`. Legen Sie die neuen Parameter Parameterdatenmember vor dem Aufruf neue Werte zuweisen `Requery`. Wenn die Filter- und sortierungsausdrücke Zeichenfolgen unverändert sind, können Sie die Abfrage wiederverwenden, wird die Leistung verbessert.

Wenn der Versuch, die das Recordset neu erstellen ein Fehler auftritt, wird das Recordset geschlossen. Vor dem Aufruf `Requery`, können Sie bestimmen, ob das Recordset, durch den Aufruf erneut abgefragt werden kann die `CanRestart` Member-Funktion. `CanRestart` garantiert nicht, dass `Requery` wird erfolgreich ausgeführt.

> [!CAUTION]
>  Rufen Sie `Requery` erst nach der Sie aufgerufen haben [öffnen](#open).

### <a name="example"></a>Beispiel

In diesem Beispiel wird neu erstellt, einem Recordset, um eine andere Sortierreihenfolge anzuwenden.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

##  <a name="setabsoluteposition"></a>  CRecordset:: SetAbsolutePosition auf

Positioniert das Recordset für den Datensatz, der angegebene Datensatz-Anzahl entspricht.

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Parameter

*nRows*<br/>
Die vom einsbasierte Ordnungsposition für den aktuellen Datensatz im Recordset.

### <a name="remarks"></a>Hinweise

`SetAbsolutePosition` Verschiebt den Zeiger für den aktuellen Datensatz basierend auf diese Position.

> [!NOTE]
>  Diese Memberfunktion ist bei Forward-only-Recordsets ungültig.

Für ODBC-Recordsets bezieht sich auf den ersten Datensatz im Recordset eine absolute Position-Einstellung von 1. die Einstellung 0 bezieht sich auf die Position der Anfang der Datei (BOF).

Sie können auch negative Werte übergeben `SetAbsolutePosition`. In diesem Fall wird die Recordset Position am Ende das Recordset ausgewertet. Z. B. `SetAbsolutePosition( -1 )` verschiebt die Zeiger für den aktuellen Datensatz zum letzten Datensatz im Recordset.

> [!NOTE]
>  Absolute Position dient nicht als Ersatz-Datensatznummer verwendet werden soll. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, auf eine bestimmte Position seit einer Datensatz Position ändert sich, wenn die vorherigen Datensätze gelöscht werden. Darüber hinaus, Sie können nicht gewährleistet werden, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze innerhalb eines Recordsets, nicht unbedingt, es sei denn, sie mit einer SQL-Anweisung mit einem erstelltwird**ORDER BY** Klausel.

Weitere Informationen zu Recordsetnavigation und Lesezeichen, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="setbookmark"></a>  CRecordset::SetBookmark

Positioniert das Recordset für den Datensatz mit dem angegebenen Lesezeichen.

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Parameter

*varBookmark*<br/>
Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) Objekt mit dem Lesezeichenwert für einen bestimmten Datensatz.

### <a name="remarks"></a>Hinweise

Um festzustellen, ob Lesezeichen im Datensatz unterstützt werden, rufen Sie [CanBookmark](#canbookmark). Um Lesezeichen verfügbar machen, wenn sie unterstützt werden, müssen Sie festlegen der `CRecordset::useBookmarks` option die *DwOptions* Parameter, der die [öffnen](#open) Member-Funktion.

> [!NOTE]
>  Wenn das Lesezeichen nicht unterstützte oder nicht verfügbar sind, wird beim Aufrufen `SetBookmark` führt dazu, dass eine Ausnahme ausgelöst wird. Lesezeichen werden auf die Forward-only-Recordsets nicht unterstützt.

Um das Lesezeichen für den aktuellen Datensatz zuerst zu abzurufen, rufen [GetBookmark](#getbookmark), die speichert des Lesezeichen-Wertes, der eine `CDBVariant` Objekt. Sie können später zu diesem Datensatz zurückkehren, indem `SetBookmark` unter Verwendung des gespeicherten lesezeichenwerts.

> [!NOTE]
>  Überprüfen Sie nach bestimmten Vorgängen Recordset die Persistenz Lesezeichen vor dem Aufruf `SetBookmark`. Wenn Sie ein Lesezeichen mit abrufen, z. B. `GetBookmark` und rufen dann `Requery`, das Lesezeichen möglicherweise nicht mehr gültig. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.

Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty

Kennzeichnet einen Felddatenmember des Recordset-Objekts als geändert oder als nicht geändert.

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Enthält die Adresse eines Datenmembers Feld in der Recordset oder NULL. Wenn der Wert NULL ist, werden alle Felddatenmember der Recordset gekennzeichnet. (NULL in C++ ist nicht identisch mit Null in der Terminologie von Datenbanken, d. h. "müssen keinen Wert.")

*bDirty*<br/>
True, wenn die Felddatenmember wie "(geändert) geändert" gekennzeichnet wird. Andernfalls "false" ist die Felddatenmember gekennzeichnet wird, wie "(unverändert) bereinigen".

### <a name="remarks"></a>Hinweise

Markieren die Felder als nicht geändert wird sichergestellt, das Feld wird nicht aktualisiert und führt zu weniger SQL-Datenverkehr.

> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die Massenabrufen verwenden. Wenn Sie das gesammelte, klicken Sie dann implementiert haben `SetFieldDirty` führt dazu, eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie von den Datensatzfeldaustausch (RFX)-Mechanismus auf den Eintrag für die Datenquelle geschrieben werden. Ändern den Wert eines Felds in der Regel legt das Feld geändert automatisch, sodass Sie nur selten aufrufen, müssen `SetFieldDirty` selbst, aber Sie sollten auch um sicherzustellen, dass die Spalten explizit, aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert in das Feld-Daten ist Member.

> [!CAUTION]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).

Verwenden NULL für das erste Argument der Funktion nur für die Funktion angewendet wird `outputColumn` Feldern nicht `param` Felder. Z. B. der Aufruf

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

wird nur festgelegt, `outputColumn` Felder NULL. `param` Felder nicht betroffen.

Auf `param` Felder müssen Sie angeben, die tatsächliche Adresse der Person, die `param` , z. B. arbeiten möchten:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Dies bedeutet, dass Sie nicht alle festlegen `param` Felder für NULL-Werte, mit `outputColumn` Felder.

##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull

Felddatenmember der Recordset als Null (insbesondere mit kein Wert) oder als nicht-Null-Flags.

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parameter

*PV*<br/>
Enthält die Adresse eines Datenmembers Feld in der Recordset oder NULL. Wenn der Wert NULL ist, werden alle Felddatenmember der Recordset gekennzeichnet. (NULL in C++ ist nicht identisch mit Null in der Terminologie von Datenbanken, d. h. "müssen keinen Wert.")

*bNull*<br/>
Legen Sie ungleich NULL, wenn es sich bei der Felddatenmember gekennzeichnet wird, als hätte er keine (Null) ist. Andernfalls 0, wenn der Feld-Datenmember ist, als nicht-Null gekennzeichnet wird.

### <a name="remarks"></a>Hinweise

Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) geändert" markiert. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits Werte oder Null sind.

> [!NOTE]
>  Rufen Sie diese Memberfunktion nicht in Recordsets, die Massenabrufen verwenden. Wenn Sie die massenzeilenabruf implementiert haben, wird beim Aufrufen `SetFieldNull` führt eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Wenn Sie ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert ein, rufen Sie möchten `SetFieldNull` mit *bNull* auf "true" festgelegt, um gekennzeichnet, die als Null. Wenn ein Feld wurde zuvor Null markiert, und jetzt Sie einen Wert fest möchten, legen Sie einfach den neuen Wert. Sie müssen nicht das Null-Flag mit entfernen `SetFieldNull`. Um zu bestimmen, ob das Feld NULL zulässig ist, rufen Sie `IsFieldNullable`.

> [!CAUTION]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).

Verwenden NULL für das erste Argument der Funktion nur für die Funktion angewendet wird `outputColumn` Feldern nicht `param` Felder. Z. B. der Aufruf

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

wird nur festgelegt, `outputColumn` Felder NULL. `param` Felder nicht betroffen.

Auf `param` Felder müssen Sie angeben, die tatsächliche Adresse der Person, die `param` , z. B. arbeiten möchten:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Dies bedeutet, dass Sie nicht alle festlegen `param` Felder für NULL-Werte, mit `outputColumn` Felder.

> [!NOTE]
>  Beim Festlegen der Parameter auf Null, einen Aufruf von `SetFieldNull` , bevor das Recordset geöffnet Ergebnisse in eine Assertion ist. In diesem Fall rufen [SetParamNull](#setparamnull).

`SetFieldNull` wird durch implementiert [DoFieldExchange](#dofieldexchange).

##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode

Legt den Sperrmodus "vollständige" gesperrt (Standard) oder "vollständige" Sperren fest. Bestimmt, wie Datensätze für Updates gesperrt werden.

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Parameter

*nMode*<br/>
Enthält einen der folgenden Werte aus der `enum LockMode`:

- `optimistic` Optimistische Sperren nur während des Aufrufs von aktualisierten Datensatzes `Update`.

- `pessimistic` Pessimistische Sperrung den Datensatz sperrt, sobald `Edit` wird aufgerufen, und hält sie gesperrt, bis die `Update` Aufruf abgeschlossen ist, oder Sie verschieben, um einen neuen Datensatz.

### <a name="remarks"></a>Hinweise

Rufen Sie diese Memberfunktion auf, wenn Sie müssen angeben, welche der beiden Datensatzsperre Strategien, die das Recordset für Updates verwendet. Standardmäßig ist das Sperrverhalten von einem Recordset `optimistic`. Sie können ändern, um eine größere Vorsicht walten `pessimistic` Strategie zu sperren. Rufen Sie `SetLockingMode` nach dem Erstellen und öffnen Sie das Recordsetobjekt, aber vor dem Aufruf `Edit`.

##  <a name="setparamnull"></a>  CRecordset::SetParamNull

Kennzeichnet einen Parameter an, als Null (insbesondere mit kein Wert) oder als ungleich Null.

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Parameter

*nIndex*<br/>
Der nullbasierte Index des Parameters.

*bNull*<br/>
Wenn "true" (Standardwert), der Parameter ist als Null gekennzeichnet. Andernfalls wird der Parameter als ungleich Null gekennzeichnet.

### <a name="remarks"></a>Hinweise

Im Gegensatz zu [SetFieldNull](#setfieldnull), rufen Sie `SetParamNull` , bevor Sie das Recordset geöffnet haben.

`SetParamNull` wird i. d. r. mit vordefinierten Abfragen (gespeicherte Prozeduren) verwendet werden.

##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition

Verschiebt den Cursor an einer Zeile im aktuellen Rowset.

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Parameter

*wRow*<br/>
Die einsbasierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.

*wLockType*<br/>
Der Wert, der angibt, wie Sie die Zeile gesperrt wird, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Wenn gesammelte zu implementieren, werden die Datensätze von Rowsets abgerufen, in dem der erste Datensatz in der abgerufenen Rowset der aktuelle Datensatz ist. Um einen anderen Datensatz im Rowset des aktuellen Datensatzes zu machen, rufen Sie `SetRowsetCursorPosition`. Sie können z. B. kombinieren `SetRowsetCursorPosition` mit der [GetFieldValue](#getfieldvalue) Memberfunktion versucht, das dynamische Abrufen von Daten aus jedem Datensatz des Recordsets.

Mit `SetRowsetCursorPosition`, muss implementierten gesammelte durch Angabe der `CRecordset::useMultiRowFetch` Möglichkeit, die *DwOptions* Parameter in der [öffnen](#open) Member-Funktion.

`SetRowsetCursorPosition` Ruft die ODBC-API-Funktion `SQLSetPos`. Die *wLockType* Parameter gibt an, der Zustand der Zeile nach der Sperre `SQLSetPos` ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für *wLockType*.

|wLockType|Beschreibung|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (Standardwert)|Die Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in der gleichen gesperrt oder entsperrt Zustand wie vor `SetRowsetCursorPosition` aufgerufen wurde.|
|SQL_LOCK_EXCLUSIVE|Die Treiber oder die Datenquelle wird ausschließlich die Zeile gesperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|
|SQL_LOCK_UNLOCK|Die Treiber oder die Datenquelle wird die Zeile entsperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|

Weitere Informationen zu `SQLSetPos`, finden Sie im Windows SDK. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize

Gibt die Anzahl der Datensätze, die während der ein Abrufvorgang abgerufen werden sollen.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Parameter

*dwNewRowsetSize*<br/>
Die Anzahl der Zeilen, die während der angegebenen Fetch abgerufen.

### <a name="remarks"></a>Hinweise

Dieser virtuelle Memberfunktion gibt an, wie viele Zeilen, die Sie während einer einzigen Abfrage abrufen, wenn gesammelte verwenden möchten. Um gesammelte zu implementieren, müssen Sie festlegen, die `CRecordset::useMultiRowFetch` option die *DwOptions* Parameter der [öffnen](#open) Member-Funktion.

> [!NOTE]
>  Aufrufen von `SetRowsetSize` ohne Implementierung Bulk Abrufen von Zeilen führt dazu, eine fehlgeschlagene Assertion.

Rufen Sie `SetRowsetSize` vor dem Aufruf `Open` fest, dass zunächst die Größe des Rowsets für das Recordset. Die Standardgröße Rowset bei der Implementierung gesammelte ist 25.

> [!NOTE]
>  Seien Sie vorsichtig beim Aufrufen von `SetRowsetSize`. Wenn Sie Speicher für die Daten manuell zugeordnet werden (gemäß der `CRecordset::userAllocMultiRowBuffers` Möglichkeit, den DwOptions-Parameter in `Open`), sollten Sie überprüfen, ob Sie müssen diese Speicherpuffer neu zuordnen, nach dem Aufruf von `SetRowsetSize`, jedoch vor dem Führen Sie Cursor Navigation-Vorgang.

Rufen Sie zum Abrufen der aktuellen Einstellung für die Rowsetgröße [GetRowsetSize](#getrowsetsize).

Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="update"></a>  CRecordset:: Update

Schließt eine `AddNew` oder `Edit` Vorgang, durch die neuen oder bearbeiteten Daten speichern, in der Datenquelle.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Rückgabewert

Ungleich NULL, wenn ein Datensatz wurde erfolgreich aktualisiert wurde; andernfalls 0, wenn keine Spalten geändert wurden. Wenn keine Datensätze aktualisiert wurden oder wenn mehr als einem Eintrag aktualisiert wurde, wird eine Ausnahme ausgelöst. Eine Ausnahme wird auch für die Datenquelle für alle anderen Fehler ausgelöst.

### <a name="remarks"></a>Hinweise

Rufen Sie nach einem Aufruf von dieser Memberfunktion die [AddNew](#addnew) oder [bearbeiten](#edit) Member-Funktion. Dieser Aufruf ist erforderlich, zum Abschließen der `AddNew` oder `Edit` Vorgang.

> [!NOTE]
>  Wenn Sie die massenzeilenabruf implementiert haben, Sie nicht aufrufen, `Update`. Dies führt eine fehlgeschlagene Assertion. Obwohl Klasse `CRecordset` stellt keinen Mechanismus zum Aktualisieren von Datenzeilen, können Sie Ihre eigenen Funktionen schreiben, indem Sie mithilfe der ODBC-API-Funktion `SQLSetPos`. Weitere Informationen über das gesammelte Abrufen von Zeilen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Beide `AddNew` und `Edit` Bearbeitungspuffer, die in der befindet sich die hinzugefügten oder bearbeiteten Daten vorbereiten, für das Speichern in der Datenquelle. `Update` Speichert die Daten. Es werden nur die Felder, markiert oder geändert erkannt, dass aktualisiert.

Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `Update` aufrufen (und der entsprechenden `AddNew` oder `Edit` aufrufen) Teil einer Transaktion. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).

> [!CAUTION]
>  Wenn Sie aufrufen `Update` ohne zuerst Aufrufen von entweder `AddNew` oder `Edit`, `Update` löst eine `CDBException`. Wenn Sie aufrufen `AddNew` oder `Edit`, rufen Sie `Update` vor dem Aufruf eine `Move` Vorgang oder bevor Sie entweder das Recordset oder die datenquellenverbindung schließen. Andernfalls sind Ihre Änderungen verloren gehen, ohne Benachrichtigung.

Weitere Informationen zum Umgang mit `Update` Fehlern finden Sie im Artikel [Recordset: wie Recordsets Update Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

### <a name="example"></a>Beispiel

Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="see-also"></a>Siehe auch

[CObject-Klasse](../../mfc/reference/cobject-class.md)<br/>
[Hierarchiediagramm](../../mfc/hierarchy-chart.md)<br/>
[CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)<br/>
[CRecordView-Klasse](../../mfc/reference/crecordview-class.md)
