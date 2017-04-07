---
title: CRecordset-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
- database records [C++]
- CRecordset class
- ODBC recordsets [C++], CRecordset objects
- sets of records [C++]
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: 23
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
ms.openlocfilehash: f7a05a5eefd6f55a68c6e9f1726dfb7c29f399f2
ms.lasthandoff: 02/24/2017

---
# <a name="crecordset-class"></a>CRecordset-Klasse
Stellt eine Gruppe von Datensätzen dar, die aus einer Datenquelle ausgewählt wurden.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|Erstellt ein `CRecordset`-Objekt. Die abgeleitete Klasse muss Konstruktor bereit, der diese aufruft.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|Vorbereitet für einen neuen Datensatz hinzufügen. Rufen Sie `Update` zum Abschluss.|  
|[CRecordset::CanAppend](#canappend)|Gibt einen Wert ungleich NULL, wenn das Recordset über neue Datensätze hinzugefügt werden können die `AddNew` -Memberfunktion.|  
|[CRecordset:: CanBookmark](#canbookmark)|Gibt einen Wert ungleich NULL, wenn das Recordset Lesezeichen unterstützt.|  
|[CRecordset::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess von einem zweiten Thread ab.|  
|[CRecordset::CancelUpdate](#cancelupdate)|Bricht alle ausstehenden Updates aufgrund einer `AddNew` oder `Edit` Vorgang.|  
|[CRecordset::CanRestart](#canrestart)|Gibt einen Wert ungleich NULL, wenn `Requery` aufgerufen werden, um die Recordset Abfrage auszuführen.|  
|[CRecordset::CanScroll](#canscroll)|Gibt einen Wert ungleich NULL, wenn Sie einen Bildlauf durch die Datensätze durchführen können.|  
|[CRecordset::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CRecordset::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn das Recordset aktualisiert werden kann (Sie können hinzufügen, aktualisieren oder Löschen von Datensätzen).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|Wird aufgerufen, zum Behandeln von Fehlern, die beim Abrufen der Datensatz generiert.|  
|[CRecordset::Close](#close)|Schließt das Recordset und der ODBC- **Befehls beschäftigt** zugeordnet.|  
|[CRecordset::Delete](#delete)|Löscht den aktuellen Datensatz aus dem Recordset. Sie müssen explizit mit einem anderen Datensatz nach dem Löschvorgang blättern.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Wird aufgerufen, um exchange von Datenzeilen aus der Datenquelle in das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).|  
|[CRecordset:: DoFieldExchange](#dofieldexchange)|Wird aufgerufen, um die exchange-Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).|  
|[CRecordset::Edit](#edit)|Vorbereitet für Änderungen an den aktuellen Datensatz. Rufen Sie `Update` um die Bearbeitung abzuschließen.|  
|[CRecordset::FlushResultSet](#flushresultset)|Gibt einen Wert ungleich NULL, wenn es ein anderes Ergebnis ist festgelegt abgerufen werden soll, wenn Sie eine vordefinierte Abfrage verwenden.|  
|[CRecordset::GetBookmark](#getbookmark)|Das Parameterobjekt der Lesezeichenwert eines Datensatzes zugewiesen.|  
|[GetDefaultConnect](#getdefaultconnect)|Wird aufgerufen, um die Standard-Verbindungszeichenfolge abzurufen.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Wird aufgerufen, um die Standard-SQL-Zeichenfolge ausführen abzurufen.|  
|[CRecordset:: GetFieldValue](#getfieldvalue)|Gibt den Wert eines Felds in einem Recordset zurück.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Gibt die Anzahl der Felder im Recordset-Objekt zurück.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Bestimmte Arten von Informationen zu den Feldern zurückgegeben in einem Recordset.|  
|[CRecordset::GetRecordCount](#getrecordcount)|Gibt die Anzahl der Datensätze im Recordset-Objekt zurück.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|Gibt die Anzahl der Datensätze, die Sie während einer einzigen Abfrage abrufen möchten.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|Gibt die tatsächliche Anzahl der Zeilen, die bei einem Abrufvorgang abgerufen.|  
|[CRecordset::GetRowStatus](#getrowstatus)|Der Status der Zeile zurückgegeben nach einem Abruf.|  
|[CRecordset::GetSQL](#getsql)|Ruft die SQL-Zeichenfolge, die zum Auswählen von Datensätzen für das Recordset verwendet.|  
|[CRecordset::GetStatus](#getstatus)|Ruft den Status des Recordsets ab: der Index des aktuellen Datensatzes und gibt an, ob eine endgültige Anzahl der Datensätze abgerufen wurden.|  
|[CRecordset::GetTableName](#gettablename)|Ruft den Namen der Tabelle, auf der das Recordset basiert.|  
|[CRecordset::IsBOF](#isbof)|Gibt einen Wert ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.|  
|[CRecordset::IsDeleted](#isdeleted)|Gibt einen Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist.|  
|[CRecordset::IsEOF](#iseof)|Gibt einen Wert ungleich NULL, wenn das Recordset wurde nach dem letzten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz geändert wurde.|  
|[CRecordset::IsFieldNull](#isfieldnull)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz null ist (keinen Wert enthält).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|Gibt einen Wert ungleich NULL, wenn das angegebene Feld des aktuellen Datensatzes auf null (kein Wert mit) festgelegt werden kann.|  
|[CRecordset::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn `Open` zuvor aufgerufen wurde.|  
|[CRecordset](#move)|Positioniert das Recordset mit einer angegebenen Anzahl von Datensätzen aus dem aktuellen Datensatz in beide Richtungen.|  
|[CRecordset::MoveFirst](#movefirst)|Positioniert den aktuellen Datensatz für den ersten Datensatz im Recordset. Testen Sie `IsBOF` erste.|  
|[CRecordset::MoveLast](#movelast)|Die Position des aktuellen Datensatzes auf den letzten Datensatz oder des letzten Rowsets. Testen Sie `IsEOF` erste.|  
|[CRecordset::MoveNext](#movenext)|Die Position des aktuellen Datensatzes auf den nächsten Datensatz oder des nächsten Rowsets. Testen Sie `IsEOF` erste.|  
|[CRecordset::MovePrev](#moveprev)|Die Position des aktuellen Datensatzes des vorherigen Datensatzes oder auf dem vorherigen Rowset. Testen Sie `IsBOF` erste.|  
|[CRecordset::OnSetOptions](#onsetoptions)|Zum Festlegen von Optionen (in der Auswahl verwendete) aufgerufen, für die angegebene ODBC-Anweisung.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Zum Festlegen von Optionen (Update) für die angegebene ODBC-Anweisung aufgerufen.|  
|[CRecordset:: Open](#open)|Öffnet das Recordset, indem die Tabelle abgerufen oder die vom Recordset darstellte Abfrage durchgeführt wird.|  
|[CRecordset::RefreshRowset](#refreshrowset)|Aktualisiert die Daten und den Status für die angegebene(n) Zeile(n).|  
|[CRecordset](#requery)|Führt die Abfrage erneut aus, um die ausgewählten Datensätze aktualisieren des Recordsets.|  
|[CRecordset:: SetAbsolutePosition auf](#setabsoluteposition)|Positioniert das Recordset für den Datensatz, der angegebene Datensatz entspricht.|  
|[CRecordset::SetBookmark](#setbookmark)|Positioniert das Recordset für den Datensatz, der durch das Lesezeichen angegeben.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|Markiert das angegebene Feld im aktuellen Datensatz, als geändert.|  
|[CRecordset::SetFieldNull](#setfieldnull)|Legt den Wert des angegebenen Felds im aktuellen Datensatz auf null (kein Wert mit) fest.|  
|[CRecordset::SetLockingMode](#setlockingmode)|Wird das Sperrverhalten "optimistische" Sperren (Standard) oder "vollständiges" Sperren. Bestimmt, wie Datensätze gesperrt werden, nach Updates.|  
|[CRecordset::SetParamNull](#setparamnull)|Setzt den angegebenen Parameter auf null (kein Wert mit).|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Positioniert den Cursor in der angegebenen Zeile im Rowset.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|Gibt die Anzahl der Datensätze, während ein Abrufvorgang abgerufen werden soll.|  
|[CRecordset:: Update](#update)|Schließt eine `AddNew` oder `Edit` Vorgang durch, indem die neuen oder bearbeiteten Daten für die Datenquelle zu speichern.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[M_hstmt](#m_hstmt)|Enthält das Handle der ODBC-Anweisung für das Recordset. Geben Sie `HSTMT` ein.|  
|[CRecordset::m_nFields](#m_nfields)|Enthält die Anzahl der Felddatenmember des Recordsets. Geben Sie `UINT` ein.|  
|[CRecordset::m_nParams](#m_nparams)|Enthält die Anzahl der Parameterdatenmember in Recordsets. Geben Sie `UINT` ein.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.|  
|[CRecordset:: M_strfilter](#m_strfilter)|Enthält eine `CString` , die angibt, Structured Query Language (SQL) `WHERE` Klausel. Als Filter verwendet, um nur die Datensätze auszuwählen, die bestimmte Kriterien erfüllen.|  
|[CRecordset::m_strSort](#m_strsort)|Enthält eine `CString` , angibt, dass eine SQL `ORDER BY` Klausel. Zum Steuern, wie die Datensätze sortiert werden.|  
  
## <a name="remarks"></a>Hinweise  
 Bekannt als "Recordsets" `CRecordset` Objekte dienen in der Regel in zwei Formen: Dynasets und Snapshots. Ein Dynaset bleibt synchronisierte Datenupdates, die von anderen Benutzern. Eine Momentaufnahme ist eine statische Ansicht der Daten. Jedes Formular stellt eine Gruppe von Datensätzen, die zum Zeitpunkt, wenn das Recordset geöffnet wird, aber, wenn Sie auf einen Datensatz in einem Dynaset Blättern, damit die Änderungen anschließend auf den Datensatz, anderen Benutzern oder anderen Recordsets in Ihrer Anwendung wiedergegeben.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Zum Arbeiten mit einer Art von Recordset leiten Sie in der Regel eine anwendungsspezifische Recordset-Klasse von `CRecordset`. Recordsets werden Datensätze aus einer Datenquelle auswählen, und anschließend können Sie:  
  
-   Führen Sie einen Bildlauf durch die Datensätze.  
  
-   Aktualisieren Sie die Datensätze zu, und geben Sie einen Sperrmodus.  
  
-   Filtern Sie das Recordset, um die Datensätze zu beschränken, auf die Datenquelle aus den verfügbaren auswählt.  
  
-   Sortieren Sie das Recordset.  
  
-   Parametrisieren Sie das Recordset angepasst werden, dessen Auswahl mit Informationen, die erst zur Laufzeit bekannt ist.  
  
 Um die Klasse zu verwenden, öffnen Sie eine Datenbank, und erstellen Sie ein Recordset-Objekt, und übergeben Sie dem Konstruktor einen Zeiger auf die `CDatabase` Objekt. Rufen Sie dann des Recordsets **öffnen** Member-Funktion, in dem Sie angeben können, ob das Objekt ein Dynaset oder eine Momentaufnahme ist. Aufrufen von **öffnen** wählt Daten aus der Datenquelle. Nach dem Öffnen des Recordset-Objekts verwenden Sie, die Mitglieder der Funktionen und Daten zu scrollen durch die Datensätze auf ihnen ausgeführt werden. Die verfügbaren Vorgänge abhängen, ob das Objekt ein Dynaset oder eine Momentaufnahme ist, ob es aktualisierbar oder schreibgeschützt ist (Dies hängt die Fähigkeit der Datenquelle Open Database Connectivity (ODBC)), und gibt an, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben. Datensätze zu aktualisieren, die möglicherweise wurde geändert oder hinzugefügt werden, da die **öffnen** aufrufen, rufen Sie die **Requery** Member-Funktion. Rufen Sie die **schließen** Member-Funktion und zerstören Sie das Objekt aus, wenn Sie damit fertig sind.  
  
 In einer abgeleiteten `CRecordset` Klasse, Datensatzfeldaustausch (RFX) oder Massen-Datensatzfeldaustausch (Bulk-RFX) wird zum Lesen und Aktualisieren von Datensatzfelder unterstützen.  
  
 Weitere Informationen über Recordsets und Datensatz Feld Exchange finden Sie in den Artikeln [Übersicht: Datenbank Programmierung](../../data/data-access-programming-mfc-atl.md), [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), und [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md). Schwerpunkt auf Dynasets und Momentaufnahmen, finden Sie in den Artikeln [Dynaset](../../data/odbc/dynaset.md) und [Snapshot](../../data/odbc/snapshot.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="addnew"></a>CRecordset::AddNew  
 Vorbereitet für einen neuen Datensatz in der Tabelle hinzufügen.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Hinweise  
 Müssen Sie aufrufen, die [Requery](#requery) Memberfunktion, die neu hinzugefügten Datensatz finden Sie unter. Felder des Datensatzes sind anfangs Null. (In der datenbankterminologie von-Null-man "kein Wert" und ist nicht identisch mit **NULL** in C++.) Um den Vorgang abzuschließen, müssen Sie aufrufen, die [Update](#update) Member-Funktion. **Update** speichert die Änderung an der Datenquelle.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie nicht aufrufen `AddNew`. Dies führt zu einem Assertionsfehler. Obwohl Klasse `CRecordset` stellt keinen Mechanismus für die Aktualisierung von Datenzeilen, können Sie eigene Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `AddNew`wird einen neuen, leeren Datensatz das Recordset-Felddatenmember vorbereitet. Nach dem Aufruf von `AddNew`, legen Sie die gewünschten Werte in die Recordset Felddatenmember. (Sie müssen nicht aufrufen, die [bearbeiten](#edit) Memberfunktion zu diesem Zweck; verwenden Sie stattdessen **bearbeiten** nur für vorhandene Datensätze.) Wenn Sie anschließend aufrufen **Update**, geänderte Werte in die Felddatenmember werden in der Datenquelle gespeichert.  
  
> [!CAUTION]
>  Wenn Sie zu einem neuen Datensatz scrollen, vor dem Aufruf von **Update**, der neue Datensatz geht verloren, und keine Warnung ausgegeben.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die `AddNew` Teil einer Transaktion aufrufen. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDatabase](../../mfc/reference/cdatabase-class.md). Beachten Sie, die aufgerufen werden soll [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf von `AddNew`.  
  
> [!NOTE]
>  Für Dynasets werden neue Datensätze als letzten Datensatz des Recordsets hinzugefügt. Hinzugefügte Datensätze werden Momentaufnahmen nicht hinzugefügt. Sie müssen Aufrufen **Requery** an das Recordset zu aktualisieren.  
  
 Es ist unzulässig, rufen Sie `AddNew` für ein Recordset, dessen **öffnen** Memberfunktion nicht aufgerufen wurde. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen, `AddNew` für ein Recordset, das auf angefügt werden kann. Sie können bestimmen, ob das Recordset aktualisierbar, durch Aufrufen von ist [CanAppend](#canappend).  
  
 Weitere Informationen finden Sie in den folgenden Artikeln: [Recordset: wie Recordsets Aktualisieren von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), und [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="canappend"></a>CRecordset::CanAppend  
 Bestimmt, ob das zuvor geöffnete Recordset Sie neue Datensätze hinzufügen können.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Hinzufügen von neuen Datensätzen; andernfalls 0. `CanAppend`Gibt 0 zurück, wenn Sie das Recordset als schreibgeschützt geöffnet.  
  
##  <a name="canbookmark"></a>CRecordset:: CanBookmark  
 Bestimmt, ob das Recordset Datensätze mithilfe von Lesezeichen markieren kann.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Der Wert ist ungleich NULL, wenn das Recordset Lesezeichen unterstützt; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Diese Funktion ist unabhängig von der **CRecordset:: useBookmarks** option der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion. `CanBookmark`Gibt an, ob die angegebene ODBC-Treiber und die Cursor unterstützen Lesezeichen. **CRecordset:: useBookmarks** gibt an, ob Lesezeichen verfügbar sein soll, sofern diese unterstützt werden.  
  
> [!NOTE]
>  Lesezeichen sind vorwärts-Recordsets nicht unterstützt.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cancel"></a>CRecordset::Cancel  
 Fordert an, dass die Datenquelle ein asynchroner Vorgang ausgeführt wird oder ein Prozess von einem zweiten Thread abzubrechen.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt die ODBC-API-Funktion aufrufen **SQLSetConnectOption**. Weitere Informationen finden Sie im Thema "Funktionen asynchron ausführen" in der *ODBC SDK Programmer's Guide*.  
  
##  <a name="cancelupdate"></a>CRecordset::CancelUpdate  
 Bricht alle ausstehenden Updates zurückzuführen, dass ein [bearbeiten](#edit) oder [AddNew](#addnew) Vorgang vor dem [Update](#update) aufgerufen wird.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht anwendbar auf Recordsets, die gesammelte, da solche Recordsets aufrufen können **bearbeiten**, `AddNew`, oder **Update**. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Wenn der automatischen Überprüfung aktiviert ist, `CancelUpdate` wird die Membervariablen wiederherstellen, auf die Werte, die sie bisher **bearbeiten** oder `AddNew` wurde aufgerufen; andernfalls, wertänderungen bleibt. Automatische Überprüfung Felder ist standardmäßig aktiviert, wenn das Recordset geöffnet wird. Um ihn zu deaktivieren, geben Sie die **Nodirtyfieldcheck** in der `dwOptions` Parameter der der [öffnen](#open) Member-Funktion.  
  
 Weitere Informationen zum Aktualisieren von Daten finden Sie im Artikel [Recordset: hinzufügen, aktualisieren und Löschen von Datensätzen (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  
  
##  <a name="canrestart"></a>CRecordset::CanRestart  
 Bestimmt, ob das Recordset ermöglicht das Neustarten der Abfrage (Wenn Sie die Datensätze zu aktualisieren) durch Aufrufen der **Requery** Member-Funktion.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn Requery zulässig ist; andernfalls 0.  
  
##  <a name="canscroll"></a>CRecordset::CanScroll  
 Bestimmt, ob das Recordset Bildlauf ermöglicht.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset ermöglicht das Durchführen eines Bildlaufs; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Durchführen eines Bildlaufs finden Sie im Artikel [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="cantransact"></a>CRecordset::CanTransact  
 Bestimmt, ob das Recordset Transaktionen ermöglicht.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset Transaktionen ermöglicht; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="canupdate"></a>CRecordset::CanUpdate  
 Bestimmt, ob das Recordset aktualisiert werden kann.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset aktualisiert werden kann; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Ein Recordset kann schreibgeschützt sein, wenn die zugrunde liegenden Datenquelle schreibgeschützt ist oder wenn Sie angegeben **CRecordset:: ReadOnly** in der `dwOptions` Parameter beim Öffnen des Recordsets.  
  
##  <a name="checkrowseterror"></a>CRecordset::CheckRowsetError  
 Wird aufgerufen, zum Behandeln von Fehlern, die beim Abrufen der Datensatz generiert.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>Parameter  
 `nRetCode`  
 Rückgabecode für eine ODBC-API-Funktion. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Dieser virtuelle Memberfunktion behandelt Fehler, die auftreten, wenn Datensätze abgerufen wurden, und ist nützlich bei gesammelte. Sie sollten überschreiben möchten `CheckRowsetError` eigene Fehlerbehandlung implementieren.  
  
 `CheckRowsetError`wird automatisch aufgerufen, in einem Vorgang für den Cursor-Navigation, wie z. B. **öffnen**, **Requery**, oder eine beliebige **verschieben** Vorgang. Den Rückgabewert der ODBC-API-Funktion übergeben **SQLExtendedFetch**. Die folgende Tabelle enthält die möglichen Werte für die `nRetCode` Parameter.  
  
|nRetCode|Beschreibung|  
|--------------|-----------------|  
|**SQL_SUCCESS**|Die Funktion wurde erfolgreich abgeschlossen. Es ist keine zusätzlichen Informationen verfügbar.|  
|**SQL_SUCCESS_WITH_INFO**|Die Funktion wurde erfolgreich abgeschlossen, möglicherweise mit einem nicht schwerwiegenden Fehler. Weitere Informationen erhalten Sie durch Aufrufen von **SQLError**.|  
|**SQL_NO_DATA_FOUND**|Alle Zeilen aus dem Resultset wurden abgerufen.|  
|**SQL_ERROR**|Fehler bei der Funktion. Weitere Informationen erhalten Sie durch Aufrufen von **SQLError**.|  
|**SQL_INVALID_HANDLE**|Fehler bei der Funktion aufgrund einer ungültigen Umgebungshandle Verbindungshandle oder Anweisungshandle. Hiermit wird einen Programmierfehler. Keine zusätzlichen Informationen steht **SQLError**.|  
|`SQL_STILL_EXECUTING`|Eine Funktion, die asynchron gestartet wurde, wird weiterhin ausgeführt. Beachten Sie, dass MFC standardmäßig diesen Wert nie weitergibt `CheckRowsetError`; MFC weiterhin aufrufen **SQLExtendedFetch** bis nicht mehr zurückgegeben `SQL_STILL_EXECUTING`.|  
  
 Weitere Informationen zu **SQLError**, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="close"></a>CRecordset::Close  
 Schließt das Recordset.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Die ODBC **Befehls beschäftigt** und den gesamten Arbeitsspeicher freigegeben, das Framework für das Recordset zugeordnet. In der Regel nach dem Aufruf von **schließen**, die C++-Recordset-Objekt zu löschen, wenn sie mit reserviert wurde **neue**.  
  
 Rufen Sie **öffnen** erneut nach dem Aufruf von **schließen**. Dadurch können Sie das Recordset-Objekt wiederverwenden. Die Alternative besteht im Aufrufen **Requery**.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&17;](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="crecordset"></a>CRecordset::CRecordset  
 Erstellt ein `CRecordset`-Objekt.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Parameter  
 `pDatabase`  
 Enthält einen Zeiger auf eine `CDatabase` oder der Wert **NULL**. Wenn dies nicht **NULL** und `CDatabase` des Objekts **öffnen** Memberfunktion nicht aufgerufen wurde, um es an die Datenquelle eine Verbindung herstellen, wird das Recordset öffnen Sie während der eigenen **öffnen** aufrufen. Wenn Sie übergeben **NULL**, ein `CDatabase` Objekt erstellt und mithilfe von Informationen mit der Datenquelle bei abgeleiteten Recordset-Klasse mit dem Klassen-Assistenten angegebene verbunden ist.  
  
### <a name="remarks"></a>Hinweise  
 Sie können entweder `CRecordset` direkt oder ableiten eine Klasse von anwendungsspezifischen von `CRecordset`. Klassen-Assistenten können Sie die Recordset-Klassen abgeleitet werden.  
  
> [!NOTE]
>  Eine abgeleitete Klasse *müssen* Geben Sie einen eigenen Konstruktor. Rufen Sie im Konstruktor der abgeleiteten Klasse den Konstruktor `CRecordset::CRecordset`, die entsprechenden Parameter entlang an sie übergibt.  
  
 Übergeben Sie **NULL** an der Recordset-Konstruktor haben ein `CDatabase` Objekt erstellt und automatisch für Sie verbunden. Dies ist nützlich, Kurzform, die nicht erforderlich ist, erstellen und verbinden Sie ein `CDatabase` Objekt vor dem Erstellen des Recordsets.  
  
### <a name="example"></a>Beispiel  
 Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
##  <a name="delete"></a>CRecordset::Delete  
 Löscht den aktuellen Datensatz.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach einer erfolgreichen löschen, werden das Recordset-Felddatenmember auf einen Nullwert festgelegt, und Sie müssen explizit aufrufen eines der **verschieben** Funktionen, um den gelöschten Datensatz zu verschieben. Nachdem Sie den gelöschten Datensatz verlassen, ist es nicht möglich, zurückzugeben. Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **löschen** Teil einer Transaktion aufrufen. Weitere Informationen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie nicht aufrufen **löschen**. Dies führt zu einem Assertionsfehler. Obwohl Klasse `CRecordset` stellt keinen Mechanismus für die Aktualisierung von Datenzeilen, können Sie eigene Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!CAUTION]
>  Das Recordset muss aktualisierbar sein und es muss ein gültiger Datensatz im Recordset aktuelle beim Aufruf von **löschen**ist, andernfalls ein Fehler auftritt. Beispielsweise, wenn Sie einen Datensatz löschen, jedoch kein Bildlauf zu einem neuen Datensatz vor dem Aufruf von **löschen** erneut **löschen** löst ein [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Im Gegensatz zu [AddNew](#addnew) und [bearbeiten](#edit), einen Aufruf von **löschen** folgt nicht durch einen Aufruf von [Update](#update). Wenn ein **löschen** Aufruf fehlschlägt, ist die Felddaten Mitglieder bleiben unverändert.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt eine Datensatzgruppe erstellt im Rahmen einer Funktion. Im Beispiel wird davon ausgegangen, `m_dbCust`, eine Membervariable vom Typ `CDatabase` bereits mit der Datenquelle verbunden ist.  
  
 [!code-cpp[NVC_MFCDatabase&18;](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange  
 Wird aufgerufen, um exchange von Datenzeilen aus der Datenquelle in das Recordset. Implementiert den Sammel-Datensatzfeldaustausch (Bulk-RFX).  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird dieses Objekt bereits eingerichtet haben, einen Kontext für den Betrieb von Exchange Feld angeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn gesammelte implementiert wird, ruft das Framework diese Member-Funktion, um Daten automatisch aus der Datenquelle in das Recordset-Objekt zu übertragen. `DoBulkFieldExchange`Außerdem bindet Parameterdatenmember, falls vorhanden, die Parameterplatzhaltern in der SQL-Anweisung-Zeichenfolge für die Auswahl des Recordsets.  
  
 Wenn gesammelte nicht implementiert ist, ruft das Framework [DoFieldExchange](#dofieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die `dwOptions` -Parameter in der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
> `DoBulkFieldExchange`ist nur verfügbar, wenn Sie eine Klasse, die von abgeleiteten arbeiten `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, müssen Sie aufrufen, die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.  
  
 Massen-Datensatzfeldaustausch (Bulk-RFX) ähnelt Datensatzfeldaustausch (RFX). Daten werden automatisch auf das Recordsetobjekt aus der Datenquelle übertragen. Sie können nicht aufgerufen `AddNew`, **bearbeiten**, **löschen**, oder **Update** Änderungen zurück an die Datenquelle übertragen. Klasse `CRecordset` derzeit keinen Mechanismus zum Aktualisieren von Datenzeilen; Sie können jedoch eigene Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**.  
  
 Beachten Sie, dass der Klassen-Assistent Massen-Datensatzfeldaustausch nicht unterstützt. aus diesem Grund müssen Sie überschreiben `DoBulkFieldExchange` manuell durch Aufrufe der Bulk-RFX-Funktionen zu schreiben. Weitere Informationen zu diesen Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).  
  
 Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie im Artikel [Datensatzfeldaustausch (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="dofieldexchange"></a>CRecordset:: DoFieldExchange  
 Wird aufgerufen, um die exchange-Daten (in beide Richtungen) zwischen den Felddatenmembern des Recordsets und der entsprechende Datensatz in der Datenquelle. Implementiert Datensatzfeldaustausch (RFX).  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Parameter  
 `pFX`  
 Ein Zeiger auf eine [CDBException](../../mfc/reference/cfieldexchange-class.md) Objekt. Das Framework wird dieses Objekt bereits eingerichtet haben, einen Kontext für den Betrieb von Exchange Feld angeben.  
  
### <a name="remarks"></a>Hinweise  
 Wenn gesammelte nicht implementiert ist, ruft das Framework diese Memberfunktion zum Austauschen von Daten zwischen den Felddatenmembern des Recordset-Objekts und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle automatisch an. `DoFieldExchange`Außerdem bindet Parameterdatenmember, falls vorhanden, die Parameterplatzhaltern in der SQL-Anweisung-Zeichenfolge für die Auswahl des Recordsets.  
  
 Wenn das gesammelte implementiert wird, ruft das Framework [DoBulkFieldExchange](#dobulkfieldexchange). Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die `dwOptions` -Parameter in der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
> `DoFieldExchange`ist nur verfügbar, wenn Sie eine Klasse, die von abgeleiteten arbeiten `CRecordset`. Wenn Sie direkt aus einem Recordset-Objekt erstellt haben `CRecordset`, müssen Sie aufrufen, die [GetFieldValue](#getfieldvalue) Member-Funktion zum Abrufen von Daten.  
  
 Der Austausch von Felddaten, namens Datensatzfeldaustausch (RFX), funktioniert in beide Richtungen: Felddatenmember des Recordset-Objekts, auf die Felder des Datensatzes in der Datenquelle und aus dem Datensatz in der Datenquelle in das Recordset-Objekt.  
  
 Die einzige Aktion, die normalerweise durchzuführenden implementieren `DoFieldExchange` für das Recordset abgeleiteten Klasse ist, erstellen Sie die Klasse mit dem Klassen-Assistenten, und geben Sie die Namen und Datentypen der Felddatenmember des. Sie können auch Code hinzufügen, in was ClassWizard geschrieben, um Parameterdatenmember oder dynamisch gebundenen Spalten behandeln. Weitere Informationen finden Sie im Artikel [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Wenn Sie Klassen-Assistent abgeleiteten Recordset-Klasse deklarieren, schreibt der Assistent eine Überschreibung der `DoFieldExchange` , die etwa wie folgt:  
  
 [!code-cpp[NVC_MFCDatabase Nr.&19;](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 Weitere Informationen über RFX-Funktionen finden Sie im Thema [Funktionen für den Datensatzfeldaustausch](../../mfc/reference/record-field-exchange-functions.md).  
  
 Weitere Beispiele und Informationen zu `DoFieldExchange`, finden Sie im Artikel [Datensatzfeldaustausch: Funktionsweise von RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Allgemeine Informationen über RFX finden Sie im Artikel [Record Field Exchange](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="edit"></a>CRecordset::Edit  
 Ermöglicht Änderungen an den aktuellen Datensatz.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Aufruf von **bearbeiten**, Sie können die Felddatenmembern ändern, indem Sie direkt die Werte zurücksetzen. Der Vorgang ist abgeschlossen, wenn Sie anschließend Aufrufen der [Update](#update) Member-Funktion zum Speichern der Änderungen auf die Datenquelle.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie nicht aufrufen **bearbeiten**. Dies führt zu einem Assertionsfehler. Obwohl Klasse `CRecordset` stellt keinen Mechanismus für die Aktualisierung von Datenzeilen, können Sie eigene Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 **Bearbeiten Sie** speichert die Werte der Felddatenmember des Recordsets. Wenn Sie aufrufen **bearbeiten**, ändern, rufen Sie dann **bearbeiten** erneut, die Werte des Datensatzes wiederhergestellt werden vor dem ersten Originalwerts **bearbeiten** aufrufen.  
  
 In einigen Fällen möchten möglicherweise eine Spalte zu aktualisieren, indem Sie somit Null (keine Daten enthält). Rufen Sie hierzu [SetFieldNull](#setfieldnull) mit einem Parameter des **TRUE** , markieren Sie das Feld Null; Dadurch wird auch die Spalte aktualisiert werden. Wenn Sie möchten, dass ein Feld mit der Datenquelle geschrieben werden, auch wenn der Wert nicht geändert hat, rufen Sie [SetFieldDirty](#setfielddirty) mit einem Parameter des **TRUE**. Dies funktioniert auch, wenn das Feld den Wert Null haben.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **bearbeiten** Teil einer Transaktion aufrufen. Beachten Sie, die aufgerufen werden soll [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) vor dem Aufruf von **bearbeiten** und nach dem Öffnen des Recordsets. Beachten Sie außerdem, dass der Aufruf [CDatabase:: CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) ist kein Ersatz für den Aufruf von **Update** zum Abschließen der **bearbeiten** Vorgang. Weitere Informationen über Transaktionen finden Sie unter Klasse [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Abhängig von der aktuellen Sperren, die zu aktualisierende Datensatz kann gesperrt sein **bearbeiten** bis zum Aufruf von **Update** oder führen Sie einen Bildlauf zu einem anderen Datensatz, oder er kann gesperrt werden, nur während der **bearbeiten** aufrufen. Sie können ändern, das Sperrverhalten mit [SetLockingMode](#setlockingmode).  
  
 Der vorherige Wert des aktuellen Datensatzes wird wiederhergestellt, wenn Sie einen Bildlauf zu einem neuen Datensatz vor dem Aufruf nach **Update**. Ein `CDBException` wird ausgelöst, wenn Sie aufrufen **bearbeiten** für ein Recordset, das aktualisiert werden kann oder wenn es keinen aktuellen Datensatz.  
  
 Weitere Informationen finden Sie in den Artikeln [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md) und [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&20;](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="flushresultset"></a>CRecordset::FlushResultSet  
 Ruft das nächste Resultset einer vordefinierten Abfrage (gespeicherten Prozedur) ab, wenn mehrere Resultsets vorhanden sind.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn es gibt mehrere Resultsets abgerufen werden sollen; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `FlushResultSet` nur wenn Sie mit dem Cursor auf das aktuelle Resultset vollständig abgeschlossen sind. Beachten Sie, dass beim Abrufen der nächsten Resultset durch Aufrufen von `FlushResultSet`, der Cursor ist nicht gültig für das Resultset, rufen Sie die [MoveNext](#movenext) Member-Funktion nach dem Aufruf von `FlushResultSet`.  
  
 Wenn eine vordefinierte Abfrage ein Output-Parameter oder Eingabe/Ausgabe-Parameter verwendet, müssen Sie aufrufen `FlushResultSet` bis zurückgegeben `FALSE` (der Wert 0), um diese Parameterwerte zu erhalten.  
  
 `FlushResultSet`Ruft die ODBC-API-Funktion `SQLMoreResults`. Wenn `SQLMoreResults` gibt `SQL_ERROR` oder `SQL_INVALID_HANDLE`, dann `FlushResultSet` löst eine Ausnahme aus. Weitere Informationen zu `SQLMoreResults`, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Die gespeicherte Prozedur muss Felder gebunden haben, wenn Sie aufrufen möchten `FlushResultSet`.  
  
### <a name="example"></a>Beispiel  
 Im folgende Code wird vorausgesetzt, dass `COutParamRecordset` ist eine `CRecordset`-abgeleitetes Objekt basierend auf einer vordefinierten Abfrage mit einem Eingabeparameter und ein Output-Parameter, und dass mehrere Resultsets. Beachten Sie die Struktur der [DoFieldExchange](#dofieldexchange) außer Kraft setzen.  
  
 [!code-cpp[NVC_MFCDatabase&21;](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase&#22;](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="getbookmark"></a>CRecordset::GetBookmark  
 Ruft den Lesezeichenwert für den aktuellen Datensatz.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) -Objekt, das Lesezeichen für den aktuellen Datensatz darstellt.  
  
### <a name="remarks"></a>Hinweise  
 Um festzustellen, ob das Recordset Lesezeichen unterstützt werden, rufen Sie [CanBookmark](#canbookmark). Um Lesezeichen zur Verfügung stellen, wenn sie unterstützt werden, müssen Sie festlegen der **CRecordset:: useBookmarks** option der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
>  Wenn Lesezeichen nicht unterstützte oder nicht verfügbar sind, werden beim Aufrufen `GetBookmark` führt dazu, dass eine Ausnahme ausgelöst wird. Lesezeichen sind vorwärts-Recordsets nicht unterstützt.  
  
 `GetBookmark`weist den Wert des Lesezeichens für den aktuellen Datensatz auf eine `CDBVariant` Objekt. Rufen Sie zum Zurückgeben zu diesem Datensatz zu einem beliebigen Zeitpunkt nach dem Wechsel zu einem anderen Datensatz [SetBookmark](#setbookmark) mit dem entsprechenden `CDBVariant` Objekt.  
  
> [!NOTE]
>  Nach bestimmten Vorgängen Recordset Lesezeichen möglicherweise nicht mehr gültig. Wenn Sie aufrufen, z. B. `GetBookmark` gefolgt von **Requery**, möglicherweise nicht zu dem Datensatz zurückgeben `SetBookmark`. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="getdefaultconnect"></a>GetDefaultConnect  
 Wird aufgerufen, um die Standard-Verbindungszeichenfolge abzurufen.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , das Standard-Verbindungszeichenfolge enthält.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Member-Funktion, um die Standard-Verbindungszeichenfolge für die Datenquelle zu erhalten, auf dem das Recordset basiert. Klassen-Assistent implementiert diese Funktion für Sie durch Identifizieren der gleichen Datenquelle, die Sie zum Abrufen von Informationen zu Tabellen und Spalten im Klassen-Assistenten zu verwenden. Wahrscheinlich werden finden Sie es sinnvoll, diese Standardeinstellung Verbindung bei der Entwicklung Ihrer Anwendung abhängig. Aber die standardmäßige Verbindung für Benutzer der Anwendung möglicherweise nicht. Wenn dies der Fall ist, sollten Sie diese Funktion implementieren, verwirft der Klassen-Assistent-Version. Weitere Informationen zu Verbindungszeichenfolgen finden Sie im Artikel [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md).  
  
##  <a name="getdefaultsql"></a>CRecordset::GetDefaultSQL  
 Wird aufgerufen, um die Standard-SQL-Zeichenfolge ausführen abzurufen.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `CString` , enthält die Standard-SQL-Anweisung.  
  
### <a name="remarks"></a>Hinweise  
 Das Framework ruft diese Member-Funktion, um die Standard-SQL-Anweisung zu erhalten, auf der das Recordset basiert. Dies ist möglicherweise ein Tabellenname oder ein SQL **wählen** Anweisung.  
  
 Sie definieren die Standard-SQL-Anweisung indirekt durch deklarieren die Recordset-Klasse mit dem Klassen-Assistent und der Klassen-Assistent führt diese Aufgabe für Sie.  
  
 Rufen Sie ggf. die SQL-Anweisung-Zeichenfolge zur eigenen Verwendung `GetSQL`, womit die SQL-Anweisung verwendet, um Datensätze des Recordsets auszuwählen, wenn sie geöffnet wurde. Sie können die Standard-SQL-Zeichenfolge in der Klasse überschreiben der Bearbeiten `GetDefaultSQL`. Sie könnten z. B. einen Aufruf einer vordefinierten Abfrage mit angeben einer **Aufrufen** Anweisung. (Beachten Sie jedoch, dass bei der Bearbeitung `GetDefaultSQL`, müssen Sie auch ändern `m_nFields` mit der Anzahl der Spalten in der Datenquelle übereinstimmen.)  
  
 Weitere Informationen finden Sie im Artikel [Recordset: Deklarieren einer Klasse für eine Tabelle (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
> [!CAUTION]
>  Der Tabellenname ist leer, wenn das Framework einen Tabellennamen ein, wenn mehrere Tabellennamen angegeben wurden, oder wenn nicht identifizieren ein **Aufrufen** Anweisung konnte nicht interpretiert werden. Beachten Sie, dass bei Verwendung einer **Aufrufen** -Anweisung darf kein Leerzeichen zwischen der geschweiften Klammer eingefügt und die **Aufrufen** -Schlüsselwort, noch sollten Sie Leerzeichen vor der geschweiften Klammer oder Einfügen der **auswählen** -Schlüsselwort in eine **wählen** Anweisung.  
  
##  <a name="getfieldvalue"></a>CRecordset:: GetFieldValue  
 Ruft die Daten im aktuellen Datensatz ab.  
  
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
 `lpszName`  
 Der Name eines Felds.  
  
 *VarValu*e  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) -Objekt, das den Wert des Felds gespeichert werden sollen.  
  
 `nFieldType`  
 Der ODBC-C-Datentyp des Felds. Mit dem Standardwert **DEFAULT_FIELD_TYPE**, erzwingt `GetFieldValue` basierend auf der folgenden Tabelle den C-Datentyp aus der SQL-Datentyp zu ermitteln. Andernfalls können die Daten direkt eingeben, oder wählen Sie einen kompatiblen Datentyp angeben. Sie können z. B. jeden Datentyp in speichern **SQL_C_CHAR**.  
  
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
  
 Weitere Informationen zu ODBC-Datentypen finden Sie unter den Themen "SQL-Datentypen" und "C-Datentypen" in Anhang D der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nIndex`  
 Der nullbasierte Index des Felds.  
  
 `strValue`  
 Ein Verweis auf eine [CString](../../atl-mfc-shared/reference/cstringt-class.md) -Objekt, das den Wert des Felds zu speichern, wird in Text konvertiert, unabhängig von dem Datentyp des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Sie können ein Feld nach Name oder Index nachschlagen. Sie können den Wert des Felds in entweder speichern eine `CDBVariant` Objekt oder ein `CString` Objekt.  
  
 Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, wird der aktuelle Datensatz immer für den ersten Datensatz in einem Rowset positioniert. Mit `GetFieldValue` auf einen Datensatz innerhalb eines bestimmten Rowsets, müssen Sie zuerst Aufrufen der [SetRowsetCursorPosition](#setrowsetcursorposition) Memberfunktion, um den Cursor an der gewünschten Zeile in diesem Rowset verschieben. Rufen Sie anschließend `GetFieldValue` für diese Zeile. Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` Möglichkeit, die `dwOptions` -Parameter in der [öffnen](#open) Member-Funktion.  
  
 Sie können `GetFieldValue` Felder statisch zur Entwurfszeit zu binden, statt zur Laufzeit dynamisch abgerufen. Beispielsweise, wenn Sie direkt aus einem Recordset-Objekt deklariert haben `CRecordset`, verwenden Sie `GetFieldValue` zum Abrufen der Felddaten; Datensatzfeldaustausch (RFX) oder Massen-Datensatzfeldaustausch (Bulk-RFX) ist nicht implementiert.  
  
> [!NOTE]
>  Wenn Sie ein Recordset-Objekt deklarieren, ohne eine Ableitung von `CRecordset`, müssen Sie nicht die ODBC-Cursorbibliothek geladen. Die Cursorbibliothek erfordert, dass das Recordset mindestens eine gebundene Spalte. Wenn Sie jedoch verwenden `CRecordset` direkt keine der Spalten gebunden sind. Die Memberfunktionen [CDatabase:: OpenEx](../../mfc/reference/cdatabase-class.md#openex) und [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) steuern, ob die Cursorbibliothek geladen werden.  
  
 `GetFieldValue`Ruft die ODBC-API-Funktion **SQLGetData**. Wenn der Treiber den Wert zurückgibt, **SQL_NO_TOTAL** für die tatsächliche Länge des Feldwerts, `GetFieldValue` löst eine Ausnahme aus. Weitere Informationen zu **SQLGetData**, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 Der folgende Beispielcode veranschaulicht Aufrufe `GetFieldValue` für direkt aus einem Recordset-Objekt deklariert `CRecordset`.  
  
 [!code-cpp[NVC_MFCDatabase&23;](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  Im Gegensatz zu den DAO-Klasse `CDaoRecordset`, `CRecordset` verfügt nicht über eine `SetFieldValue` Member-Funktion. Wenn Sie ein Objekt direkt aus erstellen `CRecordset`, es ist absolut schreibgeschützt.  
  
 Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount  
 Ruft die Gesamtanzahl der Felder in das Recordset-Objekt.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Felder im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 Weitere Informationen zum Erstellen von Datensatzgruppen, finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getodbcfieldinfo"></a>CRecordset::GetODBCFieldInfo  
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
 `lpszName`  
 Der Name eines Felds.  
  
 `fieldinfo`  
 Ein Verweis auf eine `CODBCFieldInfo` Struktur.  
  
 `nIndex`  
 Der nullbasierte Index des Felds.  
  
### <a name="remarks"></a>Hinweise  
 Eine Version der Funktion können Sie ein Feld nach Namen suchen. Die andere Version können Sie ein Feld über einen Index zu suchen.  
  
 Eine Beschreibung zu den Informationen zurückgegeben werden, finden Sie unter der [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) Struktur.  
  
 Weitere Informationen zum Erstellen von Datensatzgruppen, finden Sie im Artikel [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="getrecordcount"></a>CRecordset::GetRecordCount  
 Bestimmt die Größe des Recordset-Objekts.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Datensätze im Recordset; 0, wenn das Recordset keine Datensätze enthält; oder -1, wenn die Anzahl der Datensätze bestimmt werden kann.  
  
### <a name="remarks"></a>Hinweise  
  
> [!CAUTION]
>  Die Anzahl der Datensätze wird als eine "oberem," den höchsten Datensatz beibehalten noch angezeigt, wenn der Benutzer durch die Datensätze bewegt. Die Gesamtzahl der Datensätze wird nur bezeichnet werden, nachdem der Benutzer über den letzten Datensatz gewechselt hat. Aus Gründen der Leistung die Anzahl wird nicht aktualisiert, beim Aufruf von `MoveLast`. Aufrufen, um die Datensätze selbst zählen, `MoveNext` solange wiederholt, bis `IsEOF` gibt einen Wert ungleich NULL zurück. Hinzufügen eines Datensatzes über **CRecordset:AddNew** und **Update** erhöht die Anzahl, Löschen eines Datensatzes über `CRecordset::Delete` verringert die Anzahl.  
  
##  <a name="getrowsetsize"></a>CRecordset::GetRowsetSize  
 Ruft die aktuelle Einstellung für die Anzahl der Zeilen, die Sie während einer bestimmten Fetch abrufen möchten.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen, die während einer bestimmten Fetch abgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte verwenden, ist die Standardgröße des Rowsets beim Öffnen des Recordsets 25. Andernfalls ist der Wert 1.  
  
 Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` option in der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion. Rufen Sie zum Ändern der Einstellung für die Größe des Rowsets [SetRowsetSize](#setrowsetsize).  
  
 Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="getrowsfetched"></a>CRecordset::GetRowsFetched  
 Bestimmt, wie viele Datensätze nach einem Abrufvorgang tatsächlich abgerufen wurden.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Die Anzahl der Zeilen, die einem Abrufvorgang aus der Datenquelle abgerufen werden.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist hilfreich, wenn Sie das gesammelte implementiert haben. Die Größe des Rowsets gibt normalerweise an, wie viele Zeilen aus einem Abrufvorgang abgerufen werden. Allerdings wirkt sich auf die Gesamtanzahl der Zeilen im Recordset auch wie viele Zeilen in einem Rowset abgerufen werden. Beispielsweise verfügt das Recordset 10 Datensätze mit der Einstellung Rowset Größe 4, dann durchlaufen des Recordset durch Aufrufen von `MoveNext` führt dazu, dass die endgültige Rowset mit nur 2 Datensätze.  
  
 Um gesammelte zu implementieren, müssen Sie angeben der `CRecordset::useMultiRowFetch` option in der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion. Rufen Sie zum Angeben der Rowsetgröße [SetRowsetSize](#setrowsetsize).  
  
 Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#24;](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="getrowstatus"></a>CRecordset::GetRowStatus  
 Der Status für eine Zeile im aktuellen Rowset abgerufen.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `wRow`  
 Die&1;-basierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Statuswert für die Zeile. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 `GetRowStatus`Gibt ein Wert an eine Änderung Status auf die Zeile seit dem letzten abgerufen, von der Datenquelle, oder keine Zeile entspricht `wRow` abgerufen wurde. In der folgenden Tabelle sind die möglichen Rückgabewerte aufgelistet:  
  
|Der Wert des Status|Beschreibung|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|Die Zeile unverändert.|  
|`SQL_ROW_UPDATED`|Die Zeile wurde aktualisiert.|  
|`SQL_ROW_DELETED`|Die Zeile wurde gelöscht.|  
|`SQL_ROW_ADDED`|Die Zeile wurde hinzugefügt.|  
|`SQL_ROW_ERROR`|Die Zeile ist aufgrund eines Fehlers nicht abrufbar.|  
|`SQL_ROW_NOROW`|Es gibt keine Zeile, die entspricht `wRow`.|  
  
 Weitere Informationen finden Sie in der ODBC-API-Funktion **SQLExtendedFetch** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getstatus"></a>CRecordset::GetStatus  
 Bestimmt den Index des aktuellen Datensatzes in das Recordset und gibt an, ob der letzte Datensatz verarbeitet wurde.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>Parameter  
 `rStatus`  
 Ein Verweis auf eine **CRecordsetStatus** Objekt. Weitere Informationen finden Sie im Abschnitt Hinweise.  
  
### <a name="remarks"></a>Hinweise  
 `CRecordset`versucht, den Index, verfolgen aber unter Umständen dies u. u. nicht möglich. Finden Sie unter [GetRecordCount](#getrecordcount) eine Erklärung.  
  
 Die **CRecordsetStatus** -Struktur hat folgende Form:  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 Die zwei Elemente der **CRecordsetStatus** haben folgende Bedeutung:  
  
- **M_lCurrentRecord** enthält den nullbasierten Index des aktuellen Datensatzes im Recordset, sofern bekannt. Wenn der Index nicht bestimmt werden kann, enthält dieses Element **AFX_CURRENT_RECORD_UNDEFINED** – (2). Wenn `IsBOF` ist **TRUE** (Recordset leer oder versuchen, die vor dem ersten Datensatz scrollen), dann **M_lCurrentRecord** festgelegt ist, um **AFX_CURRENT_RECORD_BOF** (-1). Wenn für den ersten Datensatz, es auf 0 festgelegt wird, Zweitens zeichnen Sie 1 auf usw..  
  
- **M_bRecordCountFinal** Nonzero aus, wenn die Gesamtzahl der Datensätze im Recordset festgelegt wurde. Dies muss in der Regel erreicht werden, wobei am Anfang des Recordset-Objekts und Aufrufen von `MoveNext` bis `IsEOF` gibt einen Wert ungleich NULL zurück. Wenn dieses Element NULL ist, der Datensatz zählen zurückgegebene `GetRecordCount`, wenn keine –&1; ist, ist nur eine "oberem" Anzahl der Datensätze.  
  
##  <a name="getsql"></a>CRecordset::GetSQL  
 Rufen Sie diese Memberfunktion, um die SQL-Anweisung zu erhalten, die verwendet wurde, um die Datensätze des Recordsets auswählen, wenn sie geöffnet wurde.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** ein Verweis auf eine `CString` , die die SQL-Anweisung enthält.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist in der Regel wird eine SQL **wählen** Anweisung. Die zurückgegebene Zeichenfolge `GetSQL` ist schreibgeschützt.  
  
 Die zurückgegebene Zeichenfolge `GetSQL` unterscheidet sich in der Regel eine beliebige Zeichenfolge, die Sie möglicherweise haben an, dass das Recordset in die `lpszSQL` Parameter, um die **öffnen** Member-Funktion. Dies ist, da das Recordset basierte auf den an Sie übergeben eine vollständige SQL­Anweisung erstellt **öffnen**, angegebene Klassen-Assistent, den Sie in angegeben hat die **M_strFilter** und `m_strSort` Datenmember und alle Parameter, die Sie angegeben haben. Details wie das Recordset für diese SQL-Anweisung erstellt, finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf von [öffnen](#open).  
  
##  <a name="gettablename"></a>CRecordset::GetTableName  
 Ruft den Namen der SQL-Tabelle auf der die Abfrage des Recordsets basiert.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein **const** ein Verweis auf eine `CString` , enthält die Tabelle benennen, ist das Recordset basierend auf einer Tabelle ist, andernfalls eine leere Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 `GetTableName`ist nur gültig, wenn das Recordset auf eine Tabelle, die keine Verknüpfung von mehreren Tabellen oder einer vordefinierten Abfrage (gespeicherten Prozedur) basiert. Der Name ist schreibgeschützt.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nur nach dem Aufruf von [öffnen](#open).  
  
##  <a name="isbof"></a>CRecordset::IsBOF  
 Gibt einen Wert ungleich NULL, wenn das Recordset wurde vor dem ersten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält, oder wenn Sie vor dem ersten Datensatz rückwärts gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, bevor Sie einen Bildlauf von Datensatz zu Datensatz zur Feststellung, ob Sie vor dem ersten Datensatz des Recordsets überschritten haben. Sie können auch `IsBOF` zusammen mit `IsEOF` bestimmen, ob das Recordset Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von **öffnen**, wenn das Recordset keine Datensätze enthält `IsBOF` gibt einen Wert ungleich NULL zurück. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz zum aktuellen Datensatz und `IsBOF` gibt 0 zurück.  
  
 Wenn der erste Datensatz zum aktuellen Datensatz ist, und Sie rufen `MovePrev`, `IsBOF` anschließend einen Wert ungleich NULL zurück. Wenn `IsBOF` gibt einen Wert ungleich NULL, und Sie rufen `MovePrev`, ein Fehler auftritt. Wenn `IsBOF` gibt einen Wert ungleich NULL, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert führt zu einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `IsBOF` und `IsEOF` um die Grenzen eines Recordset-Objekts zu erkennen, der Code durch das Recordset in beide Richtungen bewegt wird.  
  
 [!code-cpp[NVC_MFCDatabase&#25;](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="isdeleted"></a>CRecordset::IsDeleted  
 Bestimmt, ob der aktuelle Datensatz gelöscht wurde.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset auf einen gelöschten Datensatz positioniert ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen zu einem Datensatz Bildlauf und `IsDeleted` gibt **TRUE** (ungleich null), Sie müssen Blättern Sie zu einem anderen Datensatz Weitere Recordset-Operationen durchführen zu können.  
  
 Das Ergebnis des `IsDeleted` hängt von vielen Faktoren ab, z. B. der Typ der Datensatzgruppe, ob das Recordset aktualisierbar ist, ob der angegebene der **CRecordset:: Skipdeletedrecords** option, wenn Sie das Recordset geöffnet wird, ob die Treiber Packs Datensätze gelöscht, und ob mehrere Benutzer vorhanden sind.  
  
 Weitere Informationen zu **CRecordset:: Skipdeletedrecords** und Treiber packen, finden Sie unter der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, rufen Sie nicht `IsDeleted`. Rufen Sie stattdessen die [GetRowStatus](#getrowstatus) Member-Funktion. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="iseof"></a>CRecordset::IsEOF  
 Gibt einen Wert ungleich NULL, wenn das Recordset wurde nach dem letzten Datensatz positioniert wurde. Es gibt keinen aktuellen Datensatz.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset keine Datensätze enthält oder wenn Sie über den letzten Datensatz hinaus gescrollt haben; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, wie Sie einen Bildlauf von Datensatz zu Datensatz zur Feststellung, ob Sie den letzten Datensatz des Recordsets überschritten haben. Sie können auch `IsEOF` bestimmen, ob das Recordset Datensätze enthält oder leer ist. Unmittelbar nach dem Aufruf von **öffnen**, wenn das Recordset keine Datensätze enthält `IsEOF` gibt einen Wert ungleich NULL zurück. Beim Öffnen eines Recordsets, die mindestens ein Datensatz ist der erste Datensatz zum aktuellen Datensatz und `IsEOF` gibt 0 zurück.  
  
 Wenn der letzte Datensatz zum aktuellen Datensatz, beim Aufruf von ist `MoveNext`, `IsEOF` anschließend einen Wert ungleich NULL zurück. Wenn `IsEOF` gibt einen Wert ungleich NULL, und Sie rufen `MoveNext`, ein Fehler auftritt. Wenn `IsEOF` gibt einen Wert ungleich NULL, der aktuelle Datensatz nicht definiert ist, und alle Aktionen, die einen aktuellen Datensatz erfordert führt zu einem Fehler.  
  
### <a name="example"></a>Beispiel  
 Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="isfielddirty"></a>CRecordset::IsFieldDirty  
 Bestimmt, ob das angegebene Feld Datenelement seit geändert wurde [bearbeiten](#edit) oder [AddNew](#addnew) aufgerufen wurde.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder geändert werden.  
  
### <a name="return-value"></a>Rückgabewert  
 Ungleich NULL, wenn das angegebene Feld Datenelement, seit dem Aufrufen geändert hat `AddNew` oder **bearbeiten**; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Die Daten in alle Felddatenmember transferiert auf den Datensatz in der Datenquelle beim Aktualisieren des aktuellen Datensatzes durch einen Aufruf der [Update](#update) -Memberfunktion des `CRecordset` (nach einem Aufruf von **bearbeiten** oder `AddNew`).  
  
> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die gesammelte verwenden. Gesammelte, dann implementiert `IsFieldDirty` gibt stets **FALSE** und führt dazu, dass eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Aufrufen von `IsFieldDirty` setzt sich die Auswirkungen der vorhergehenden Aufrufen von [SetFieldDirty](#setfielddirty) seit der geänderten Status des Felds neu ausgewertet wird. In der `AddNew` Fall, wenn der aktuelle Wert des Felds aus der Pseudo-null-Wert unterscheidet sich der Feldstatus festgelegt ist fehlerhaft. In der **bearbeiten** Fall, wenn der Wert des Felds aus den zwischengespeicherten Wert unterscheidet, wird der Feldstatus geändert.  
  
 `IsFieldDirty`wird über implementiert [DoFieldExchange](#dofieldexchange).  
  
 Weitere Informationen auf das Änderungsflag finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
##  <a name="isfieldnull"></a>CRecordset::IsFieldNull  
 Gibt einen Wert ungleich NULL, wenn das angegebene Feld im aktuellen Datensatz Null ist (keinen Wert enthält).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder Null sind.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das angegebene Feld Datenelement als Null gekennzeichnet ist; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um festzustellen, ob der angegebene Felddatenmember eines Recordset-Objekts als Null gekennzeichnet ist. (In der datenbankterminologie von-Null-man "kein Wert" und ist nicht identisch mit **NULL** in C++.) Wenn Felddatenmember als Null gekennzeichnet ist, wird er als eine Spalte des aktuellen Datensatzes interpretiert kein Wert vorhanden ist.  
  
> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die gesammelte verwenden. Gesammelte, dann implementiert `IsFieldNull` gibt stets **FALSE** und führt dazu, dass eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `IsFieldNull`wird über implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isfieldnullable"></a>CRecordset::IsFieldNullable  
 Gibt einen Wert ungleich NULL, wenn das angegebene Feld des aktuellen Datensatzes auf Null festgelegt werden kann (mit kein Wert) zurück.  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Ein Zeiger auf den Felddatenmember, dessen Status Sie überprüfen möchten, oder **NULL** bestimmt, ob die Felder auf einen Null-Wert festgelegt werden kann.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob das angegebene Feld Datenelement "zulässig" ist (können auf einen Null-Wert festgelegt werden C++ **NULL** ist nicht Null, womit, in der datenbankterminologie identisch "having kein Wert").  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie nicht aufrufen `IsFieldNullable`. Rufen Sie stattdessen die [GetODBCFieldInfo](#getodbcfieldinfo) Member-Funktion, um zu bestimmen, ob ein Feld auf einen Null-Wert festgelegt werden kann. Beachten Sie, die Sie, immer aufrufen können `GetODBCFieldInfo`, unabhängig davon, ob Sie nun das gesammelte Abrufen von Zeilen implementiert haben. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Ein Feld, das nicht Null sein kann, muss einen Wert aufweisen. Wenn Sie versuchen, ein solches Feld auf Null, die beim Hinzufügen oder Aktualisieren eines Datensatzes festgelegt, lehnt die Datenquelle ab, das Hinzufügen oder aktualisieren, und [aktualisieren](#update) löst eine Ausnahme aus. Die Ausnahme tritt auf, wenn Sie aufrufen **Update**, nicht beim Aufruf von [SetFieldNull](#setfieldnull).  
  
 Mithilfe von **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder werden nicht beeinflusst.  
  
 Auf **Param** Felder, müssen Sie die tatsächliche Adresse der Person angeben **Param** , wie z. B. arbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase&#27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, Sie können nicht festgelegt, werden alle **Param** Felder **NULL**, wie **OutputColumn** Felder.  
  
 `IsFieldNullable`wird über implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="isopen"></a>CRecordset::IsOpen  
 Bestimmt, ob das Recordset bereits geöffnet ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich Null des Recordset-Objekts [öffnen](#open) oder [Requery](#requery) Memberfunktion zuvor aufgerufen wurde und das Recordset nicht geschlossen wurde, andernfalls 0.  
  
##  <a name="m_hstmt"></a>M_hstmt  
 Enthält einen Handle für die ODBC-Anweisung-Datenstruktur des Typs **Befehls beschäftigt**, die das Recordset zugeordnet.  
  
### <a name="remarks"></a>Hinweise  
 Jede Abfrage einer ODBC-Datenquelle zugeordnet ist ein **Befehls beschäftigt**.  
  
> [!CAUTION]
>  Verwenden Sie keine **M_hstmt** vor [öffnen](#open) aufgerufen wurde.  
  
 Sie ist normalerweise nicht erforderlich für den Zugriff auf die **Befehls beschäftigt** direkt, es für die direkte Ausführung von SQL-Anweisungen notwendig. Die `ExecuteSQL` -Memberfunktion der Klasse `CDatabase` enthält ein Beispiel mit **M_hstmt**.  
  
##  <a name="m_nfields"></a>CRecordset::m_nFields  
 Enthält die Anzahl der Felddatenmember der Recordset-Klasse. d. h. die Anzahl der Spalten, die durch das Recordset aus der Datenquelle ausgewählt.  
  
### <a name="remarks"></a>Hinweise  
 Der Konstruktor für die Recordset-Klasse initialisieren muss `m_nFields` mit der korrekten Anzahl. Wenn Sie von Zeilen nicht implementiert haben, schreibt der Klassen-Assistent diese Initialisierung für Sie bei Verwendung die Recordset-Klasse deklarieren. Sie können Sie auch manuell schreiben.  
  
 Das Framework verwendet diese Nummer zum Verwalten der Interaktion zwischen den Felddatenmembern und die entsprechenden Spalten des aktuellen Datensatzes in der Datenquelle.  
  
> [!CAUTION]
>  Diese Zahl muss die Spaltenanzahl "Ausgabe" in registrierten entsprechen `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit dem Parameter **CFieldExchange::outputColumn**.  
  
 Sie können Spalten dynamisch, wie im Artikel erläutert binden "Recordset: dynamisch binden von Datenspalten." Wenn Sie dies tun, müssen Sie die Anzahl die in erhöhen `m_nFields` entsprechend der Anzahl von RFX oder Bulk-RFX-Funktion aufrufen, der `DoFieldExchange` oder `DoBulkFieldExchange` Memberfunktion für die dynamisch gebundenen Spalten.  
  
 Weitere Informationen finden Sie in den Artikeln [Recordset: Dynamisches Binden von Spalten (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) und [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_nparams"></a>CRecordset::m_nParams  
 Enthält die Anzahl der Parameterdatenmember in der Recordset-Klasse. d. h., übergeben die Anzahl von Parametern mit Abfrage des Recordsets.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Recordset-Klasse Parameterdatenmember verfügt, muss der Konstruktor für die Klasse initialisieren `m_nParams` mit der korrekten Anzahl. Der Wert des `m_nParams` hat den Standardwert 0. Wenn Sie Parameterdatenmember hinzufügen (die Sie manuell ausführen müssen) müssen Sie eine Initialisierung auch manuell hinzufügen, im Konstruktor Klasse die Anzahl von Parametern an (die muss mindestens so groß wie die Anzahl der "Platzhalter in Ihre **M_strFilter** oder `m_strSort` Zeichenfolge).  
  
 Das Framework verwendet diese Zahl, wenn sie die Abfrage des Recordsets parametrisiert.  
  
> [!CAUTION]
>  Diese Zahl muss der Anzahl der "Params" in registriert entsprechen `DoFieldExchange` oder `DoBulkFieldExchange` nach einem Aufruf von [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) mit einem Parameterwert von **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, oder **CFieldExchange::inoutParam**.  
  
### <a name="example"></a>Beispiel  
  Finden Sie in den Artikeln [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) und [Datensatzfeldaustausch: Verwenden von RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="m_pdatabase"></a>CRecordset::m_pDatabase  
 Enthält einen Zeiger auf die `CDatabase` Objekt über die das Recordset mit einer Datenquelle verbunden ist.  
  
### <a name="remarks"></a>Hinweise  
 Diese Variable wird auf zwei Arten festgelegt werden. In der Regel übergeben Sie einen Zeiger auf ein bereits verbundenen `CDatabase` -Objekts bei der Konstruktion des Recordsetobjekts. Wenn Sie übergeben **NULL** stattdessen `CRecordset` erstellt ein `CDatabase` -Objekt für Sie und verbunden. In beiden Fällen `CRecordset` den Zeiger in dieser Variablen gespeichert.  
  
 Normalerweise wird nicht direkt müssen mit den gespeicherten Zeiger **M_pDatabase**. Wenn Sie Ihre eigenen Erweiterungen schreiben `CRecordset`, jedoch möglicherweise den Zeiger zu verwenden. Beispielsweise benötigen Sie möglicherweise den Mauszeiger Wenn Sie lösen eigene `CDBException`s. Oder vielleicht benötigen Sie es ggf. etwas mit dem gleichen `CDatabase` Objekt, z. B. Transaktionen, Festlegen von Timeouts, ausgeführt oder das Aufrufen der `ExecuteSQL` -Memberfunktion der Klasse `CDatabase` SQL-Anweisungen direkt ausgeführt.  
  
##  <a name="m_strfilter"></a>CRecordset:: M_strfilter  
 Nach der Konstruktion des Recordset-Objekts, jedoch vor dem Aufruf der **öffnen** Member funktioniert, verwenden Sie dieses Datenelement zum Speichern ein `CString` mit einer SQL **wobei** Klausel.  
  
### <a name="remarks"></a>Hinweise  
 Das Recordset verwendet diese Zeichenfolge zu beschränken (oder Filtern) Datensätze ausgewählt werden, während die **öffnen** oder **Requery** aufrufen. Dies ist nützlich zum Auswählen einer Teilmenge von Datensätzen, z. B. "alle Vertriebsmitarbeiter in Kalifornien basierte" ("State = CA"). Die ODBC-SQL-Syntax für eine **,** -Klausel  
  
 `WHERE search-condition`  
  
 Beachten Sie, die Sie nicht die **, in dem** Schlüsselwort in der Zeichenfolge. Das Framework stellt sie bereit.  
  
 Sie können auch der Filterzeichenfolge parametrisieren, indem platzieren '' Platzhalter, ein Parameterdatenmember in der Klasse für jeden Platzhalter deklarieren und übergeben von Parametern an das Recordset zur Laufzeit. Dadurch können Sie den Filter zur Laufzeit zu erstellen. Weitere Informationen finden Sie im Artikel [Recordset: Parametrisieren eines Recordsets (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Weitere Informationen zu SQL **,** -Klauseln finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum auswählen und Filtern von Datensätzen finden Sie im Artikel [Recordset: Filtern von Datensätzen (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#30;](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="m_strsort"></a>CRecordset::m_strSort  
 Nach der Konstruktion des Recordset-Objekts, jedoch vor dem Aufruf der **öffnen** Member funktioniert, verwenden Sie dieses Datenelement zum Speichern ein `CString` mit einer SQL **ORDER BY** Klausel.  
  
### <a name="remarks"></a>Hinweise  
 Das Recordset verwendet diese Zeichenfolge, die Datensätze sortiert ausgewählt wird, während die **öffnen** oder **Requery** aufrufen. Dieses Feature können Sie ein Recordset auf einer oder mehreren Spalten sortieren. Die ODBC-SQL-Syntax für eine **ORDER BY** -Klausel  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 wobei ist eine Sortierung, eine ganze Zahl oder ein Spaltenname. Sie können auch die aufsteigende oder absteigende Reihenfolge (die Reihenfolge ist standardmäßig aufsteigend) angeben, indem "ASC" oder "DESC" an der Spaltenliste in der Sortierzeichenfolge angehängt. Die ausgewählten Datensätze werden zunächst nach der ersten Spalte aufgeführt und anschließend die zweite usw. sortiert. Sie können z. B. ein Recordset "Kunden" nach Nachnamen und Vornamen dann bestellen. Die Anzahl der Spalten, die Sie auflisten können, hängt von der Datenquelle ab. Weitere Informationen finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Beachten Sie, die Sie nicht die **ORDER BY** Schlüsselwort in der Zeichenfolge. Das Framework stellt sie bereit.  
  
 Weitere Informationen zu SQL-Klauseln, finden Sie im Artikel [SQL](../../data/odbc/sql.md). Weitere Informationen zum Sortieren von Datensätzen finden Sie im Artikel [Recordset: Sortieren von Datensätzen (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#31;](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="move"></a>CRecordset  
 Verschiebt die Zeiger für den aktuellen Datensatz im Recordset entweder vorwärts oder rückwärts.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>Parameter  
 `nRows`  
 Die Anzahl der Zeilen vorwärts oder rückwärts verschoben. Positive Werte vorwärts, am Ende des Recordset-Objekts. Negative Werte rückwärts, an den Anfang.  
  
 `wFetchType`  
 Bestimmt das Rowset, **verschieben** abgerufen wird. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert von 0 für übergeben `nRows`, **verschieben** aktualisiert den aktuellen Datensatz; **Verschieben** endet aktuellen `AddNew` oder **bearbeiten** -Modus und der aktuelle Datensatz Wert vor dem Wiederherstellen wird `AddNew` oder **bearbeiten** aufgerufen wurde.  
  
> [!NOTE]
>  Wenn Sie ein Recordset durchlaufen, können nicht Sie gelöschte Datensätze überspringen. Finden Sie unter [CRecordset::IsDeleted](#isdeleted) Weitere Informationen. Beim Öffnen einer `CRecordset` mit der **SkipDeletedRecords** option festgelegt ist, **verschieben** bestätigt werden, wenn die `nRows` Parameter 0 ist. Dieses Verhalten verhindert, dass die Aktualisierung von Zeilen, die von anderen Clientanwendungen, die mit den gleichen Daten gelöscht werden. Finden Sie unter der `dwOption` -Parameter in [öffnen](#open) eine Beschreibung der **SkipDeletedRecords**.  
  
 **Verschieben Sie** verschiebt das Recordset nach Rowsets. Basierend auf den Werten für `nRows` und `wFetchType`, **verschieben** wird das entsprechende Rowset abgerufen und dann wird der erste Datensatz in diesem Rowset zum aktuellen Datensatz. Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, ist die Größe des Rowsets immer 1. Beim Abrufen eines Rowsets **verschieben** ruft direkt die [CheckRowsetError](#checkrowseterror) Memberfunktion zum Behandeln von Fehlern, die durch das Abrufen.  
  
 Abhängig von den Werten, die Sie übergeben, **verschieben** entspricht anderen `CRecordset` Memberfunktionen. Insbesondere wird der Wert der `wFetchType` weist möglicherweise darauf hin, eine Memberfunktion, die eine intuitivere und häufig die bevorzugte Methode zum aktuellen Datensatz.  
  
 Die folgende Tabelle enthält die möglichen Werte für `wFetchType`, das Rowset, **verschieben** abgerufen wird basierend auf `wFetchType` und `nRows`, und alle entsprechenden Member-Funktion für `wFetchType`.  
  
|wFetchType|Abgerufene rowset|Entsprechender Member-Funktion|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE`(Standardwert)|Das Rowset ab `nRows` Zeile(n) aus der ersten Zeile im aktuellen Rowset.||  
|`SQL_FETCH_NEXT`|Das nächste Rowset. `nRows` wird ignoriert.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|Das vorherige Rowset. `nRows` wird ignoriert.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|Das erste Rowset im Recordset. `nRows` wird ignoriert.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|Die letzte vollständige Rowset im Recordset. `nRows` wird ignoriert.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|Wenn `nRows` > 0, das Rowset ab `nRows` Zeilen vom Anfang des Recordset-Objekts. Wenn `nRows` < 0,="" the="" rowset="" starting=""> `nRows` Zeilen am Ende des Recordset-Objekts. Wenn `nRows` = 0 ist, wird eine Bedingung Anfang der Datei (BOF) zurückgegeben.|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|Das Rowset, das in der Zeile, dessen Lesezeichenwert entspricht beginnt `nRows`.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  Für Vorwärts-Recordsets **verschieben** ist nur gültig mit einem Wert von `SQL_FETCH_NEXT` für `wFetchType`.  
  
> [!CAUTION]
>  Aufrufen von **verschieben** löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Bestimmt, ob das Recordset alle Datensätze enthält, rufen Sie [IsBOF](#isbof) und [IsEOF](#iseof).  
  
> [!NOTE]
>  Wenn Sie nach dem Anfang oder Ende des Recordsets gescrollt haben ( `IsBOF` oder `IsEOF` gibt einen Wert ungleich null) durch das Aufrufen einer **verschieben** Funktion löst möglicherweise eine `CDBException`. Z. B. wenn `IsEOF` gibt einen Wert ungleich NULL und `IsBOF` nicht der Fall, dann `MoveNext` löst eine Ausnahme aus, aber `MovePrev` nicht.  
  
> [!NOTE]
>  Wenn Sie aufrufen **verschieben** während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Weitere Informationen finden Sie unter der ODBC-API-Funktion **SQLExtendedFetch** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#28;](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="movefirst"></a>CRecordset::MoveFirst  
 Macht dem ersten Datensatz in das erste Rowset zum aktuellen Datensatz.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Hinweise  
 Unabhängig davon, ob das gesammelte implementiert wurde wird dies immer der erste Datensatz im Recordset sein.  
  
 Sie müssen keinen Aufrufen **MoveFirst** sofort, nachdem Sie das Recordset geöffnet. Zu diesem Zeitpunkt ist der erste Datensatz (sofern vorhanden) automatisch zum aktuellen Datensatz.  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht gültig für Vorwärts-Recordsets.  
  
> [!NOTE]
>  Wenn Sie ein Recordset durchlaufen, können nicht Sie gelöschte Datensätze überspringen. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion Details.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Bestimmt, ob das Recordset alle Datensätze enthält, rufen Sie `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="movelast"></a>CRecordset::MoveLast  
 Wird der erste Datensatz im Rowset letzten Abschluss des aktuellen Datensatzes.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MoveLast` einfach wechselt zum letzten Datensatz im Recordset.  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht gültig für Vorwärts-Recordsets.  
  
> [!NOTE]
>  Wenn Sie ein Recordset durchlaufen, können nicht Sie gelöschte Datensätze überspringen. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion Details.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Bestimmt, ob das Recordset alle Datensätze enthält, rufen Sie `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="movenext"></a>CRecordset::MoveNext  
 Wird der erste Datensatz in den nächsten Rowsets des aktuellen Datensatzes.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MoveNext` einfach auf den nächsten Datensatz bewegt.  
  
> [!NOTE]
>  Wenn Sie ein Recordset durchlaufen, können nicht Sie gelöschte Datensätze überspringen. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion Details.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Bestimmt, ob das Recordset alle Datensätze enthält, rufen Sie `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie aufrufen `IsEOF` vor dem Aufruf von `MoveNext`. Beispielsweise, wenn Sie nach dem Ende des Recordsets gescrollt haben `IsEOF` gibt einen Wert ungleich Null; ein nachfolgender Aufruf von `MoveNext` eine Ausnahme auslöst.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="moveprev"></a>CRecordset::MovePrev  
 Wird der erste Datensatz im Rowset vorherigen zum aktuellen Datensatz.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie das gesammelte Abrufen von Zeilen nicht implementiert haben, hat das Recordset eine Rowsetgröße von 1, daher `MovePrev` einfach wechselt zum vorherigen Datensatz.  
  
> [!NOTE]
>  Diese Memberfunktion ist nicht gültig für Vorwärts-Recordsets.  
  
> [!NOTE]
>  Wenn Sie ein Recordset durchlaufen, können nicht Sie gelöschte Datensätze überspringen. Finden Sie unter der [IsDeleted](#isdeleted) Memberfunktion Details.  
  
> [!CAUTION]
>  Aufrufen eines der **verschieben** Funktionen löst eine Ausnahme aus, wenn das Recordset keine Datensätze aufweist. Bestimmt, ob das Recordset alle Datensätze enthält, rufen Sie `IsBOF` und `IsEOF`.  
  
> [!NOTE]
>  Es wird empfohlen, dass Sie aufrufen `IsBOF` vor dem Aufruf von `MovePrev`. Beispielsweise, wenn Sie den Anfang des Recordsets gescrollt haben `IsBOF` gibt einen Wert ungleich Null; ein nachfolgender Aufruf von `MovePrev` eine Ausnahme auslöst.  
  
> [!NOTE]
>  Wenn Sie eine Aufrufen der **verschieben** Funktionen während des aktuellen Datensatzes wird aktualisiert oder hinzugefügt, die Updates werden ohne Warnung.  
  
 Weitere Informationen zur Recordsetnavigation finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [IsBOF](#isbof).  
  
##  <a name="onsetoptions"></a>CRecordset::OnSetOptions  
 Zum Festlegen von Optionen (in der Auswahl verwendete) aufgerufen, für die angegebene ODBC-Anweisung.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Die **Befehls beschäftigt** der ODBC-Anweisung, deren Optionen festgelegt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `OnSetOptions` , Optionen (Auswahl verwendet) für die angegebene ODBC-Anweisung festlegen. Das Framework ruft diese Member-Funktion zum Festlegen der anfänglichen Optionen für das Recordset. `OnSetOptions`die Datenquelle unterstützt Scroll-Cursors und Cursorparallelität bestimmt und das Recordset-Optionen entsprechend festgelegt. (Während `OnSetOptions` wird zum Auswahlvorgänge, `OnSetUpdateOptions` für Update-Vorgänge verwendet wird.)  
  
 Überschreiben Sie `OnSetOptions` Optionen speziell für den Treiber oder die Datenquelle festgelegt. Z. B. wenn die Datenquelle unterstützt, die für den exklusiven Zugriff öffnen Sie möglicherweise außer Kraft setzen `OnSetOptions` diese Möglichkeit nutzen.  
  
 Weitere Informationen zu Cursorn finden Sie im Artikel [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions  
 Zum Festlegen von Optionen (Update) für die angegebene ODBC-Anweisung aufgerufen.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Die **Befehls beschäftigt** der ODBC-Anweisung, deren Optionen festgelegt werden sollen.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie `OnSetUpdateOptions` , Optionen (Update verwendet) für die angegebene ODBC-Anweisung festlegen. Das Framework ruft diese Member-Funktion nach dem Erstellen einer Befehls beschäftigt, um Datensätze in einem Recordset zu aktualisieren. (Während `OnSetOptions` wird zum Auswahlvorgänge, `OnSetUpdateOptions` für Update-Vorgänge verwendet wird.) `OnSetUpdateOptions` bestimmt die Datenquelle unterstützt Scroll-Cursors und Cursorparallelität und das Recordset-Optionen entsprechend festgelegt.  
  
 Überschreiben Sie `OnSetUpdateOptions` Optionen einer ODBC-Anweisung festgelegt werden, bevor diese Anweisung verwendet wird, auf die Datenbank zugreifen.  
  
 Weitere Informationen zu Cursorn finden Sie im Artikel [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="open"></a>CRecordset:: Open  
 Öffnet das Recordset, indem die Tabelle abgerufen oder die vom Recordset darstellte Abfrage durchgeführt wird.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>Parameter  
 `nOpenType`  
 Übernehmen Sie den Standardwert **AFX_DB_USE_DEFAULT_TYPE**, oder verwenden Sie einen der folgenden Werte aus der **Enum OpenType**:  
  
- **CRecordset:: Dynaset** ein Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets bestimmt. Die von anderen Benutzern an den Datenwerten vorgenommenen Änderungen sind nach einem Abrufvorgang allerdings sichtbar. Dynasets sind auch als keysetgesteuerte Recordsets bekannt.  
  
- **CRecordset:: Snapshot** ein statisches Recordset mit bidirektionalem Bildlauf. Die Mitgliedschaft und die Reihenfolge der Datensätze werden beim Öffnen des Recordsets und die Datenwerte beim Abrufen der Datensätze bestimmt. Die von anderen Benutzern vorgenommenen Änderungen sind nicht sichtbar, bis das Recordset geschlossen und erneut geöffnet wird.  
  
- **CRecordset:: Dynamic** ein Recordset mit bidirektionalem Bildlauf. Die von anderen Benutzern an der Mitgliedschaft, der Reihenfolge und den Datenwerten vorgenommen Änderungen sind nach einem Abrufvorgang sichtbar. Beachten Sie, dass dieser Recordsettyp von vielen ODBC-Treibern nicht unterstützt wird.  
  
- **CRecordset:: forwardOnly** ein schreibgeschütztes Recordset mit Bildlauf ausschließlich vorwärts.  
  
     Für `CRecordset`, der Standardwert ist **CRecordset:: Snapshot**. Mithilfe des Standardwertmechanismus kann bei Visual C++-Assistenten mit ODBC-`CRecordset` sowie DAO- `CDaoRecordset`, die über unterschiedliche Standardwerte verfügen, interagiert werden.  
  
 Weitere Informationen über diese Recordsettypen finden Sie im Artikel [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Weitere Informationen finden Sie im Artikel "Verwenden von Blocks und bildlauffähigen Cursorn" im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!CAUTION]
>  Wenn der angeforderte Typ nicht unterstützt wird, löst das Framework eine Ausnahme aus.  
  
 `lpszSQL`  
 Eine Zeichenfolge, in der eines der folgenden Elemente enthalten ist:  
  
-   Ein **NULL** Zeiger.  
  
-   Name der Tabelle  
  
-   SQL **auswählen** Anweisung (optional mit einem SQL- **,** oder **ORDER BY** Klausel).  
  
-   Ein **Aufrufen** Anweisung, die den Namen einer vordefinierten Abfrage (gespeicherten Prozedur). Achten Sie darauf, dass Sie keine Leerzeichen zwischen der geschweiften Klammer eingefügt werden und die **Aufrufen** Schlüsselwort.  
  
 Weitere Informationen zu dieser Zeichenfolge finden Sie in der Tabelle und der Diskussion über die Rolle von ClassWizard unter Hinweisen.  
  
> [!NOTE]
>  Die Reihenfolge der Spalten in einem Resultset muss die Reihenfolge der RFX- oder Bulk-RFX-Funktionsaufrufe in der [DoFieldExchange](#dofieldexchange) oder [DoBulkFieldExchange](#dobulkfieldexchange) Funktion außer Kraft setzen.  
  
 `dwOptions`  
 Eine Bitmaske, die eine Kombination der unten aufgeführten Werte angeben kann. Einige davon schließen sich einander aus. Der Standardwert ist **keine**.  
  
- **CRecordset:: None** keine Optionen festgelegt. Dieser Parameterwert und alle anderen Werte schließen einander aus. Standardmäßig kann das Recordset mit aktualisiert werden [bearbeiten](#edit) oder [löschen](#delete) und ermöglicht das Anfügen von neuer Datensätzen mit [AddNew](#addnew). Aktualisierbarkeit hängt von der Datenquelle sowie von der angegebenen `nOpenType` - Option ab. Optimierung für Massenhinzufügeaktionen ist nicht verfügbar. Das gesammelte Abrufen von Zeilen wird nicht implementiert. Gelöschte Datensätze werden während der Recordsetnavigation nicht übersprungen. Lesezeichen sind nicht verfügbar. Automatische Überprüfung fehlerhafter Felder wird implementiert.  
  
- **CRecordset:: AppendOnly** nicht zulassen **bearbeiten** oder **löschen** auf das Recordset. Lassen Sie nur `AddNew` zu. Diese Option ist gegenseitig **CRecordset:: ReadOnly**.  
  
- **CRecordset:: ReadOnly** öffnen Sie das Recordset als schreibgeschützt. Diese Option ist gegenseitig **CRecordset:: AppendOnly**.  
  
- **CRecordset:: optimizeBulkAdd** vorbereitete SQL-Anweisung verwenden, Optimieren Sie viele Datensätze auf einmal hinzufügen. Gilt nur, wenn Sie nicht die ODBC-API-Funktion verwenden **SQLSetPos** zum Aktualisieren des Recordsets. Das erste Update bestimmt die geänderten Felder. Diese Option und `CRecordset::useMultiRowFetch` schließen einander aus.  
  
- `CRecordset::useMultiRowFetch`Implementieren Sie die gesammelte damit mehrere Zeilen in einem Abrufvorgang abgerufen werden können. Das ist eine erweiterte Funktion, die zum Verbessern der Leistung entworfen wurde. Allerdings wird der Massenaustausch von Datensatzfeldern von ClassWizard nicht unterstützt. Diese Option ist gegenseitig **optimizeBulkAdd**. Beachten Sie, dass bei Angabe `CRecordset::useMultiRowFetch`, klicken Sie dann die Option **Nodirtyfieldcheck** wird automatisch aktiviert wird (doppelte Pufferung ist nicht möglich); auf Vorwärts-Recordsets wird die Option **:: Useextendedfetch** wird automatisch aktiviert. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
- **CRecordset:: Skipdeletedrecords** bei der Navigation durch das Recordset alle gelöschten Datensätze zu überspringen. Das verlangsamt in bestimmten relativen Abrufen die Leistung. Diese Option ist bei forward-only-Recordsets ungültig. Wenn Sie aufrufen [verschieben](#move) mit der `nRows` Parameter auf 0 festgelegt, und die **CRecordset:: Skipdeletedrecords** option festgelegt ist, **verschieben** bestätigt. Beachten Sie, dass **CRecordset:: Skipdeletedrecords** ähnelt dem *treiberverpackung*, d. h., die Zeilen gelöscht, die vom Recordset entfernt werden. Wenn der Treiber allerdings Datensätze verpackt, werden nur die von Ihnen gelöschten Datensätze übersprungen. Die von anderen Benutzern gelöschten Datensätze werden nicht übersprungen, solange das Recordset geöffnet ist. **CRecordset:: Skipdeletedrecords** überspringt die von anderen Benutzern gelöschten Zeilen.  
  
- **CRecordset:: useBookmarks** können Lesezeichen für das Recordset unterstützt. Lesezeichen verlangsamen den Datenabruf, verbessern aber die Leistung bei der Datennavigation. In forward-only-Recordsets ist das ungültig. Weitere Informationen finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
- **CRecordset:: Nodirtyfieldcheck** Deaktivieren der automatischen Überprüfung (doppelte Pufferung). Dadurch wird die Leistung verbessert. Sie müssen allerdings Felder manuell als geändert kennzeichnen, indem Sie die Memberfunktionen `SetFieldDirty` und `SetFieldNull` aufrufen. Beachten Sie, dass die doppelte Pufferung in der `CRecordset`-Klasse der doppelten Pufferung in der `CDaoRecordset`-Klasse ähnelt. Bei `CRecordset` können Sie die doppelte Pufferung allerdings nicht für einzelne Felder aktivieren. Sie können sie für alle Felder aktivieren oder deaktivieren. Beachten Sie, dass bei Angabe der Option `CRecordset::useMultiRowFetch`, dann **Nodirtyfieldcheck** aktiviert wird, wird automatisch; allerdings `SetFieldDirty` und `SetFieldNull` auf Recordsets, gesammelte implementieren, verwendet werden kann.  
  
- **CRecordset:: ExecuteDirect** verwenden Sie keine vorbereitete SQL-Anweisung. Zum Verbessern der Leistung Geben Sie diese Option, wenn die **Requery** Memberfunktion wird nie aufgerufen werden.  
  
- **CRecordset:: Useextendedfetch** implementieren **SQLExtendedFetch** anstelle von **SQLFetch**. Dies wurde für das Implementieren des gesammelten Abrufens von Zeilen in forward-only-Recordsets entworfen. Wenn Sie die Option `CRecordset::useMultiRowFetch` für eine Forward-only-Recordset, dann **:: Useextendedfetch** wird automatisch aktiviert.  
  
- **CRecordset:: userAllocMultiRowBuffers** der Benutzer wird für die Daten Speicherpuffer zuordnen. Verwenden Sie diese Option in Verbindung mit `CRecordset::useMultiRowFetch`, wenn Sie Ihren eigenen Speicher zuordnen möchten. Andernfalls ordnet wird der notwendigen Speicher vom Framework automatisch zugeordnet. Weitere Informationen finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Beachten Sie, dass die Angabe **CRecordset:: userAllocMultiRowBuffers** ohne `CRecordset::useMultiRowFetch` führt dazu, dass eine fehlgeschlagene Assertion.  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CRecordset` -Objekt erfolgreich geöffnet wurde; andernfalls 0, wenn [CDatabase:: Open](../../mfc/reference/cdatabase-class.md#open) (sofern aufgerufen) 0 zurück.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Memberfunktion zum Ausführen der vom Recordset definierten Abfrage aufrufen. Vor dem Aufruf von **öffnen**, müssen Sie das Recordset-Objekt erstellen.  
  
 Die Verbindung des Recordsets mit der Datenquelle hängt davon ab, wie Sie des Recordsets vor dem Aufruf von **öffnen**. Wenn Sie übergeben ein [CDatabase](../../mfc/reference/cdatabase-class.md) Objekt an den recordsetkonstruktor, der nicht mit der Datenquelle verbunden wurde diese Memberfunktion verwendet [GetDefaultConnect](#getdefaultconnect) Datenbankobjekt zu öffnen versucht. Wenn Sie übergeben **NULL** des Recordset-Konstruktors und der Konstruktor erstellt eine `CDatabase` -Objekt für Sie und **öffnen** versucht, das Datenbankobjekt, das eine Verbindung herstellen. Ausführliche Informationen zum Schließen des Recordsets und die Verbindung in diesen unterschiedlichen Situationen finden Sie unter [schließen](#close).  
  
> [!NOTE]
>  Der Zugriff auf eine Datenquelle durch ein `CRecordset`-Objekt wird immer freigegeben. Anders als die `CDaoRecordset`-Klasse können Sie kein `CRecordset`-Objekt zum Öffnen einer Datenquelle mit exklusivem Zugriff verwenden.  
  
 Beim Aufruf von **öffnen**, eine in der Regel eine SQL-Abfrage **wählen** -Anweisung wählt Datensätze basierend auf Kriterien in der folgenden Tabelle dargestellt.  
  
|Der Wert des lpszSQL-Parameters.|Die ausgewählten Datensätze werden von folgenden Aspekten bestimmt:|Beispiel|  
|------------------------------------|----------------------------------------|-------------|  
|**NULL**|Die von `GetDefaultSQL` zurückgegebene Zeichenfolge.||  
|SQL-Tabellenname|Alle Spalten der Tabellenliste in `DoFieldExchange` oder `DoBulkFieldExchange`.|`"Customer"`|  
|Der vordefinierte Name der Abfrage (gespeicherten Prozedur)|Die Spalten, zu denen die Abfrage per Definition zurückgibt.|`"{call OverDueAccts}"`|  
|**Wählen Sie** Spaltenliste **von** Tabellenliste|Die angegebenen Spalten aus den angegebenen Tabellen.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  Achten Sie darauf, dass keine zusätzlichen Leerzeichen in der SQL-Zeichenfolge eingefügt werden. Beispielsweise, wenn Sie Leerzeichen zwischen der geschweiften Klammer einfügen und die **Aufrufen** MFC-Schlüsselworts wird fälschlicherweise die SQL-Zeichenfolge als Tabellenname und bindet sie in einer **wählen** Anweisung, wodurch eine Ausnahme ausgelöst wird. Auch wenn vordefinierte Abfrage einen Output-Parameter verwendet, fügen Sie keine Leerzeichen zwischen den geschweiften Klammern und die "Symbol. Schließlich müssen Sie keine Leerzeichen vor der geschweiften Klammer in einfügen ein **Aufrufen** Anweisung oder vor der **auswählen** -Schlüsselwort in einer **wählen** Anweisung.  
  
 Die übliche Vorgehensweise ist die Übergabe **NULL** auf **öffnen**; in diesem Fall **öffnen** Aufrufe [GetDefaultSQL](#getdefaultsql). Wenn Sie eine abgeleitete arbeiten `CRecordset` -Klasse, **GetDefaultSQL** der Tabelle bzw. die Sie im Klassen-Assistenten angegeben haben. Sie können stattdessen andere Informationen im `lpszSQL`-Parameter angeben.  
  
 Jede Übergabe **öffnen** erstellt eine endgültige SQL-Anweisung für die Abfrage (Zeichenfolge möglicherweise die SQL **, in dem** und **ORDER BY** Klauseln angefügt, um die `lpszSQL` Sie übergebene Zeichenfolge) und führt dann die Abfrage. Sie können die erstellte Zeichenfolge überprüfen, durch Aufrufen von [GetSQL](#getsql) nach dem Aufruf von **öffnen**. Weitere Informationen über die Konstruktionsweise eine SQL-Anweisung erstellt und Auswahl von Datensätzen finden Sie im Artikel [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
 Die Felddatenmember der Recordset-Klasse sind an die Spalten der ausgewählten Daten gebunden. Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 Wenn Sie Optionen für das Recordset, wie z. B. einen Filter oder eine Sortierung festlegen möchten geben Sie diese nach der Konstruktion des Recordset-Objekts, aber vor dem Aufruf von **öffnen**. Wenn Sie die Datensätze im Recordset nach dem aktualisieren möchten das Recordset bereits geöffnet ist, rufen Sie [Requery](#requery).  
  
 Weitere Informationen und zusätzliche Beispiele finden Sie in den Artikeln [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset: wie Recordsets auswählen von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), und [Recordset: Erstellen und Schließen von Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Den folgenden Codebeispielen werden verschiedene Arten von der **öffnen** aufrufen.  
  
 [!code-cpp[NVC_MFCDatabase Nr.&16;](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="refreshrowset"></a>CRecordset::RefreshRowset  
 Aktualisiert die Daten und den Status für eine Zeile im aktuellen Rowset.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parameter  
 `wRow`  
 Die&1;-basierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen&0; (null), um die Größe des Rowsets liegen.  
  
 `wLockType`  
 Ein Wert, der angibt, wie die Zeile gesperrt, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen Wert von NULL für übergeben `wRow`, und klicken Sie dann jede Zeile im Rowset aktualisiert werden.  
  
 Verwenden `RefreshRowset`, Sie müssen implementiert gesammelte durch Angabe der **CRecordset::useMulitRowFetch** option der [öffnen](#open) Member-Funktion.  
  
 `RefreshRowset`Ruft die ODBC-API-Funktion **SQLSetPos**. Die `wLockType` Parameter gibt die Sperrzustand der Zeile nach dem **SQLSetPos** ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für `wLockTyp`e.  
  
|wLockType|Beschreibung|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(Standardwert)|Die Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in den gleichen Status gesperrt oder entsperrt vor dem `RefreshRowset` aufgerufen wurde.|  
|`SQL_LOCK_EXCLUSIVE`|Die Treiber oder die Datenquelle wird die Zeile exklusiv gesperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|  
|`SQL_LOCK_UNLOCK`|Die Treiber oder die Datenquelle hebt die Zeile. Nicht alle Datenquellen unterstützen diese Art von Sperre.|  
  
 Weitere Informationen zu **SQLSetPos**, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="requery"></a>CRecordset  
 Neu (aktualisiert) einem Recordset.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn das Recordset erfolgreich neu erstellt wurde; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Falls Datensätze zurückgegeben werden, wird der erste Datensatz zum aktuellen Datensatz.  
  
 In der Reihenfolge für das Recordset widerspiegeln, das Hinzufügen und löschen, die Sie oder andere Benutzer mit der Datenquelle herstellen, müssen Sie das Recordset erstellen, durch Aufruf **Requery**. Wenn das Recordset ein Dynaset ist, wird automatisch Updates, die Sie oder andere Benutzer die vorhandenen Datensätze (jedoch nicht Additions) Stellen angezeigt. Das Recordset eine Momentaufnahme ist, rufen Sie **Requery** entsprechend der Bearbeitung durch andere Benutzer als auch hinzufügen und löschen.  
  
 Rufen Sie für ein Dynaset oder eine Momentaufnahme, **Requery** jederzeit das Recordset mit eine neue filtern oder sortieren oder neue Parameterwerte neu erstellt werden soll. Legen Sie die neue Eigenschaft filtern oder sortieren durch Zuweisen neuer Werte zu **M_strFilter** und `m_strSort` vor dem Aufruf von **Requery**. Neue Parameter festlegen, indem Zuweisen neuer Werte zu Parameterdatenmember vor dem Aufruf von **Requery**. Wenn die Zeichenfolgen filtern und Sortieren unverändert sind, können Sie die Abfrage wiederverwenden wird die Leistung verbessert.  
  
 Wenn das Recordset neu erstellen fehlschlägt, wird das Recordset geschlossen. Vor dem Aufruf von **Requery**, können Sie bestimmen, ob das Recordset durch Aufrufen von erneut abgefragt werden kann die `CanRestart` -Memberfunktion. `CanRestart`garantiert nicht, dass **Requery** wird erfolgreich ausgeführt.  
  
> [!CAUTION]
>  Rufen Sie **Requery** , wenn Sie aufgerufen haben [öffnen](#open).  
  
### <a name="example"></a>Beispiel  
 In diesem Beispiel wird ein Recordset, um eine andere Sortierreihenfolge neu erstellt.  
  
 [!code-cpp[NVC_MFCDatabase&#29;](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="setabsoluteposition"></a>CRecordset:: SetAbsolutePosition auf  
 Positioniert das Recordset für den Datensatz, der angegebene Datensatz entspricht.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>Parameter  
 `nRows`  
 Der einsbasierte Position für den aktuellen Datensatz im Recordset.  
  
### <a name="remarks"></a>Hinweise  
 `SetAbsolutePosition`Verschiebt den aktuellen Datensatzzeiger basierend auf diese Position.  
  
> [!NOTE]
>  Diese Memberfunktion ist in Vorwärts Recordsets ungültig.  
  
 Für ODBC-Recordsets bezieht sich auf den ersten Datensatz im Recordset eine absolute Position-Einstellung von 1. die Einstellung 0 bezieht sich auf die Position der Anfang der Datei (BOF).  
  
 Sie können auch negative Werte übergeben `SetAbsolutePosition`. In diesem Fall wird das Recordset Position am Ende des Recordset-Objekts ausgewertet. Z. B. `SetAbsolutePosition( -1 )` bewegt den aktuellen Datensatzzeiger zum letzten Datensatz im Recordset.  
  
> [!NOTE]
>  Absolute Position dient nicht als Ersatz-Datensatznummer verwendet werden. Lesezeichen sind weiterhin die empfohlene Methode zurückzukehren, um eine bestimmte Position, da ein Datensatz Position ändert sich, wenn die vorherigen Datensätze gelöscht werden. Darüber hinaus, Sie können nicht gewährleistet werden, dass ein bestimmter Datensatz die gleiche absolute Position hat, wenn das Recordset neu erstellt wird, da die Reihenfolge der einzelnen Datensätze in einem Recordset nicht garantiert ist, es sei denn, sie mit einer SQL-Anweisung mit erstellt wird ein **ORDER BY** Klausel.  
  
 Weitere Informationen zu Recordsetnavigation und Lesezeichen, finden Sie in den Artikeln [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) und [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="setbookmark"></a>CRecordset::SetBookmark  
 Positioniert das Recordset für den Datensatz mit dem angegebenen Lesezeichen.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Parameter  
 `varBookmark`  
 Ein Verweis auf eine [CDBVariant](../../mfc/reference/cdbvariant-class.md) Objekt mit dem Lesezeichenwert "für einen bestimmten Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Um festzustellen, ob das Recordset Lesezeichen unterstützt werden, rufen Sie [CanBookmark](#canbookmark). Um Lesezeichen zur Verfügung stellen, wenn sie unterstützt werden, müssen Sie festlegen der **CRecordset:: useBookmarks** option der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
>  Wenn Lesezeichen nicht unterstützte oder nicht verfügbar sind, werden beim Aufrufen `SetBookmark` führt dazu, dass eine Ausnahme ausgelöst wird. Lesezeichen sind vorwärts-Recordsets nicht unterstützt.  
  
 Rufen Sie zuerst das Lesezeichen für den aktuellen Datensatz Aufrufen [GetBookmark](#getbookmark), dem speichert des Lesezeichen-Wertes, der ein `CDBVariant` Objekt. Sie können später zu diesem Datensatz zurückkehren, indem `SetBookmark` mit den gespeicherten Lesezeichenwert.  
  
> [!NOTE]
>  Überprüfen Sie nach bestimmten Vorgängen Recordset Lesezeichen Persistenz vor dem Aufruf von `SetBookmark`. Wenn Sie ein Lesezeichen mit abrufen, z. B. `GetBookmark` und rufen dann **Requery**, das Lesezeichen möglicherweise nicht mehr gültig. Rufen Sie [CDatabase:: GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) zu überprüfen, ob Sie sicher aufrufen können `SetBookmark`.  
  
 Weitere Informationen zu Lesezeichen und Recordsetnavigation, finden Sie in den Artikeln [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) und [Recordset: Scrollen (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="setfielddirty"></a>CRecordset::SetFieldDirty  
 Kennzeichnet einen Felddatenmember des Recordset-Objekts als geändert oder unverändert.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des Felddatenmember im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember im Recordset gekennzeichnet sind. (C++ **NULL** ist nicht identisch mit Null in der Terminologie für Datenbanken, d. h. "keinen Wert aufweisen.")  
  
 `bDirty`  
 **True,** ist der Felddatenmember als "(geändert) geändert" gekennzeichnet werden. Andernfalls **FALSE** ist der Felddatenmember als "(unverändert) bereinigen" gekennzeichnet werden.  
  
### <a name="remarks"></a>Hinweise  
 Markieren die Felder unverändert wird sichergestellt, das Feld wird nicht aktualisiert und führt zu weniger Datenverkehr SQL.  
  
> [!NOTE]
>  Diese Memberfunktion gilt nicht für Recordsets, die gesammelte verwenden. Wenn Sie gesammelte dann implementiert haben `SetFieldDirty` führt dazu, dass eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Die Framework-Markierungen geändert Felddatenmember, um sicherzustellen, dass sie auf den Datensatz in der Datenquelle von den Datensatzfeldaustausch (RFX)-Mechanismus geschrieben werden. Ändern den Wert eines Felds in der Regel das Feld modifizierte automatisch festgelegt, daher nur in seltenen Fällen Sie aufrufen müssen, `SetFieldDirty` sich jedoch möglicherweise manchmal sicherstellen möchten, dass Spalten explizit aktualisiert oder eingefügt werden, unabhängig davon, welcher Wert im Felddatenmember ist.  
  
> [!CAUTION]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mithilfe von **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder werden nicht beeinflusst.  
  
 Auf **Param** Felder, müssen Sie die tatsächliche Adresse der Person angeben **Param** , wie z. B. arbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase&#27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, Sie können nicht festgelegt, werden alle **Param** Felder **NULL**, wie **OutputColumn** Felder.  
  
##  <a name="setfieldnull"></a>CRecordset::SetFieldNull  
 Felddatenmember der Recordset als Null (insbesondere mit kein Wert) oder als nicht-Null-Flags.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `pv`  
 Enthält die Adresse des Felddatenmember im Recordset oder **NULL**. Wenn **NULL**, alle Felddatenmember im Recordset gekennzeichnet sind. (C++ **NULL** ist nicht identisch mit Null in der Terminologie für Datenbanken, d. h. "keinen Wert aufweisen.")  
  
 `bNull`  
 Wert ungleich NULL, wenn die Felddatenmember gekennzeichnet wird, dass kein Wert (Null) ist. Andernfalls 0, wenn die Felddatenmember als ungleich Null gekennzeichnet wird.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie einen neuen Datensatz zu einem Recordset hinzufügen, werden alle Felddatenmember anfänglich auf einen Nullwert festgelegt und als "(geändert) geändert" gekennzeichnet. Wenn Sie einen Datensatz aus einer Datenquelle abrufen, deren Spalten entweder bereits Werte oder NULL.  
  
> [!NOTE]
>  Rufen Sie diese Memberfunktion nicht in Recordsets, die gesammelte verwenden. Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, beim Aufrufen von `SetFieldNull` führt eine fehlgeschlagene Assertion. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Wenn Sie ein Feld des aktuellen Datensatzes zu definieren, ohne einen Wert, rufen Sie möchten `SetFieldNull` mit `bNull` festgelegt **TRUE** so kennzeichnen Sie es als Null. Wenn ein Feld war zuvor Null markiert, und jetzt Sie ihm einen Wert zuzuweisen möchten, legen Sie einfach den neuen Wert. Sie müssen nicht mit der Null-Flag entfernen `SetFieldNull`. Um zu bestimmen, ob das Feld NULL zulässig ist, rufen Sie `IsFieldNullable`.  
  
> [!CAUTION]
>  Diese Member-Funktion nur aufrufen, nachdem Sie aufgerufen haben [bearbeiten](#edit) oder [AddNew](#addnew).  
  
 Mithilfe von **NULL** für das erste Argument der Funktion nur für die Funktion angewendet wird **OutputColumn** Felder nicht **Param** Felder. Z. B. der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 wird nur festgelegt, **OutputColumn** Felder **NULL**; **Param** Felder werden nicht beeinflusst.  
  
 Auf **Param** Felder, müssen Sie die tatsächliche Adresse der Person angeben **Param** , wie z. B. arbeiten möchten:  
  
 [!code-cpp[NVC_MFCDatabase&#27;](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Dies bedeutet, Sie können nicht festgelegt, werden alle **Param** Felder **NULL**, wie **OutputColumn** Felder.  
  
> [!NOTE]
>  Beim Festlegen der Parameter NULL, einen Aufruf von `SetFieldNull` , bevor das Recordset geöffnet Ergebnisse in eine Assertion ist. In diesem Fall rufen [SetParamNull](#setparamnull).  
  
 `SetFieldNull`wird über implementiert [DoFieldExchange](#dofieldexchange).  
  
##  <a name="setlockingmode"></a>CRecordset::SetLockingMode  
 Wird das Sperrverhalten "optimistische" Sperren (Standard) oder "vollständiges" Sperren. Bestimmt, wie Datensätze gesperrt werden, nach Updates.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>Parameter  
 `nMode`  
 Enthält einen der folgenden Werte aus der **Enum LockMode**:  
  
- **vollständige** optimistische Sperren nur während des Aufrufs von aktualisierten Datensatzes **Update**.  
  
- **Eingeschränkte** pessimistische Sperren wird den Datensatz, sobald **bearbeiten** aufgerufen und bleibt gesperrt, bis die **Update** Aufruf abgeschlossen ist, oder Sie verschieben, um einen neuen Datensatz.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion auf, wenn Sie müssen angeben, welche der beiden Datensatzsperren Strategien, die das Recordset für Updates verwendet. Standardmäßig wird das Sperrverhalten von einem Recordset **optimistische**. Sie können ändern, um eine größere Vorsicht walten **pessimistische** Strategie sperren. Rufen Sie `SetLockingMode` nach dem Erstellen und öffnen Sie das Recordsetobjekt, aber vor dem Aufruf von **bearbeiten**.  
  
##  <a name="setparamnull"></a>CRecordset::SetParamNull  
 Flags-Parameter als Null (insbesondere mit kein Wert) oder als nicht-Null.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `nIndex`  
 Der nullbasierte Index des Parameters.  
  
 `bNull`  
 Wenn **TRUE** (Standardwert), wird der Parameter als Null gekennzeichnet. Andernfalls wird der Parameter als ungleich Null gekennzeichnet.  
  
### <a name="remarks"></a>Hinweise  
 Im Gegensatz zu [SetFieldNull](#setfieldnull), rufen Sie `SetParamNull` , bevor Sie das Recordset geöffnet haben.  
  
 `SetParamNull`wird i. d. r. mit vordefinierten Abfragen (gespeicherte Prozeduren) verwendet.  
  
##  <a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition  
 Verschiebt den Cursor auf eine Zeile im aktuellen Rowset.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Parameter  
 `wRow`  
 Die&1;-basierte Position einer Zeile im aktuellen Rowset. Dieser Wert kann zwischen 1 und die Größe des Rowsets liegen.  
  
 `wLockType`  
 Der Wert, der angibt, wie die Zeile gesperrt, nachdem sie aktualisiert wurde. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn gesammelte implementieren, werden die Datensätze von Rowsets abgerufen, in dem der erste Datensatz des abgerufenen Rowsets des aktuellen Datensatzes ist. Um den aktuellen Datensatz einem anderen Datensatz im Rowset zu erhalten, rufen Sie `SetRowsetCursorPosition`. Sie können z. B. kombinieren `SetRowsetCursorPosition` mit der [GetFieldValue](#getfieldvalue) Memberfunktion dynamische Abrufen von Daten aus jedem Datensatz des Recordsets.  
  
 Verwenden `SetRowsetCursorPosition`, müssen implementierten gesammelte durch Angabe der `CRecordset::useMultiRowFetch` Möglichkeit, die `dwOptions` -Parameter in der [öffnen](#open) Member-Funktion.  
  
 `SetRowsetCursorPosition`Ruft die ODBC-API-Funktion **SQLSetPos**. Die `wLockType` Parameter gibt die Sperrzustand der Zeile nach dem **SQLSetPos** ausgeführt wurde. Die folgende Tabelle beschreibt die möglichen Werte für `wLockTyp`e.  
  
|wLockType|Beschreibung|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(Standardwert)|Die Treiber oder die Datenquelle wird sichergestellt, dass die Zeile in den gleichen Status gesperrt oder entsperrt vor dem `SetRowsetCursorPosition` aufgerufen wurde.|  
|`SQL_LOCK_EXCLUSIVE`|Die Treiber oder die Datenquelle wird die Zeile exklusiv gesperrt. Nicht alle Datenquellen unterstützen diese Art von Sperre.|  
|`SQL_LOCK_UNLOCK`|Die Treiber oder die Datenquelle hebt die Zeile. Nicht alle Datenquellen unterstützen diese Art von Sperre.|  
  
 Weitere Informationen zu **SQLSetPos**, finden Sie unter der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="setrowsetsize"></a>CRecordset::SetRowsetSize  
 Gibt die Anzahl der Datensätze, während ein Abrufvorgang abgerufen werden soll.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>Parameter  
 *dwNewRowsetSize*  
 Die Anzahl der Zeilen, die während einer bestimmten Fetch abgerufen werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dieser virtuelle Memberfunktion gibt an, wie viele Zeilen, die Sie während einer einzigen Abfrage abrufen, wenn gesammelte verwenden möchten. Um gesammelte zu implementieren, müssen Sie festlegen der `CRecordset::useMultiRowFetch` option in der `dwOptions` Parameter von der [öffnen](#open) Member-Funktion.  
  
> [!NOTE]
>  Aufrufen von `SetRowsetSize` ohne Implementierung Bulk gesammelte führt dazu, dass eine fehlgeschlagene Assertion.  
  
 Rufen Sie `SetRowsetSize` vor dem Aufruf von **öffnen** zu Beginn der Rowsetgröße für das Recordset festlegen. Die Standardgröße des Rowsets bei der Implementierung gesammelte ist 25.  
  
> [!NOTE]
>  Seien Sie vorsichtig beim Aufruf von `SetRowsetSize`. Wenn Sie für die Daten manuell Speicher zuordnen (gemäß der **CRecordset:: userAllocMultiRowBuffers** -Option des DwOptions-Parameters in **öffnen**), überprüfen Sie, ob Sie müssen diese Speicherpuffer neu zuordnen, nach dem Aufruf von `SetRowsetSize`, jedoch vor dem Ausführen alle Cursor Navigation-Vorgang.  
  
 Um die aktuelle Einstellung für die Größe des Rowsets abzurufen, rufen [GetRowsetSize](#getrowsetsize).  
  
 Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="update"></a>CRecordset:: Update  
 Schließt eine `AddNew` oder **bearbeiten** Vorgang durch, indem die neuen oder bearbeiteten Daten für die Datenquelle zu speichern.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn ein Datensatz erfolgreich aktualisiert wurde; andernfalls 0, wenn keine Spalten geändert wurden. Wenn keine Datensätze aktualisiert wurden oder wenn mehr als ein Datensatz aktualisiert wurde, wird eine Ausnahme ausgelöst. Eine Ausnahme wird auch in der Datenquelle für alle anderen Fehler ausgelöst.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Memberfunktion nach einem Aufruf der [AddNew](#addnew) oder [bearbeiten](#edit) Member-Funktion. Dieser Aufruf ist erforderlich, zum Abschließen der `AddNew` oder **bearbeiten** Vorgang.  
  
> [!NOTE]
>  Wenn Sie das gesammelte Abrufen von Zeilen implementiert haben, können Sie nicht aufrufen **Update**. Dies führt zu einem Assertionsfehler. Obwohl Klasse `CRecordset` stellt keinen Mechanismus für die Aktualisierung von Datenzeilen, können Sie eigene Funktionen schreiben, mit der ODBC-API-Funktion **SQLSetPos**. Weitere Informationen über das gesammelte finden Sie im Artikel [Recordset: Abrufen von Datensätzen in einer Sammeloperation (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Beide `AddNew` und **bearbeiten** vorbereiten Bearbeitungspuffer in der die hinzugefügten oder bearbeiteten Daten platziert werden zum Speichern in der Datenquelle. **Update** speichert die Daten. Nur die Felder markiert oder als geändert erkannt werden aktualisiert.  
  
 Wenn die Datenquelle Transaktionen unterstützt, können Sie machen die **Update** aufrufen (und dem zugehörigen `AddNew` oder **bearbeiten** aufrufen) Teil einer Transaktion. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!CAUTION]
>  Wenn Sie aufrufen **Update** ohne Aufruf von `AddNew` oder **bearbeiten**, **Update** löst eine `CDBException`. Wenn Sie aufrufen `AddNew` oder **bearbeiten**, müssen Sie aufrufen **Update** vor dem Aufruf einer **verschieben** Vorgang oder vor dem Schließen des Recordsets oder die datenquellenverbindung. Andernfalls sind die Änderungen ohne Benachrichtigung.  
  
 Weitere Informationen zum Umgang mit **Update** Fehlern finden Sie im Artikel [Recordset: wie Recordsets Aktualisieren von Datensätzen (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
### <a name="example"></a>Beispiel  
 Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDatabase-Klasse](../../mfc/reference/cdatabase-class.md)   
 [CRecordView-Klasse](../../mfc/reference/crecordview-class.md)

