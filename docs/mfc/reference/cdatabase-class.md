---
title: CDatabase-Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDatabase
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], ODBC
- MFC [C++], ODBC
- ODBC [C++], CDatabase class
- ODBC database class
- database connections [C++], CDatabase class
- CDatabase class
ms.assetid: bd0de70a-e3c3-4441-bcaa-bbf434426ca8
caps.latest.revision: 24
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
ms.openlocfilehash: a14025d712f09bef2b6b749d46cac1b1371fd4e3
ms.lasthandoff: 02/24/2017

---
# <a name="cdatabase-class"></a>CDatabase-Klasse
Stellt eine Verbindung mit einer Datenquelle dar, über welche die Datenquelle bearbeitet werden kann.  
  
## <a name="syntax"></a>Syntax  
  
```  
class CDatabase : public CObject  
```  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-constructors"></a>Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDatabase::CDatabase](#cdatabase)|Erstellt ein `CDatabase`-Objekt. Initialisieren Sie das Objekt durch Aufrufen von `OpenEx` oder **öffnen**.|  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDatabase::BeginTrans](#begintrans)|Startet "Transaction" â €"eine Reihe von umkehrbare Aufrufe an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen der Klasse `CRecordset` â €" auf der verbundenen Datenquelle. Die Datenquelle muss unterstützt Transaktionen für **BeginTrans** wirksam.|  
|[CDatabase::BindParameters](#bindparameters)|Ermöglicht das Binden von Parametern vor dem Aufruf von `CDatabase::ExecuteSQL`.|  
|[CDatabase::Cancel](#cancel)|Bricht einen asynchronen Vorgang oder einen Prozess von einem zweiten Thread ab.|  
|[CDatabase::CanTransact](#cantransact)|Gibt einen Wert ungleich NULL, wenn die Datenquelle Transaktionen unterstützt.|  
|[CDatabase::CanUpdate](#canupdate)|Gibt einen Wert ungleich NULL, wenn die `CDatabase` Objekt ist aktualisierbar (schreibgeschützt).|  
|[CDatabase::Close](#close)|Schließt die datenquellenverbindung.|  
|[CDatabase:: CommitTrans](#committrans)|Schließt eine Transaktion, die vom begonnen **BeginTrans**. Befehle in der Transaktion, die die Datenquelle ändern, werden durchgeführt.|  
|[CDatabase:: ExecuteSQL](#executesql)|Führt eine SQL­Anweisung. Es werden keine Datensätze zurückgegeben.|  
|[CDatabase:: GetBookmarkPersistence](#getbookmarkpersistence)|Identifiziert die Vorgänge, mit denen Lesezeichen auf Recordset-Objekte beibehalten.|  
|[CDatabase:: Getconnect](#getconnect)|Gibt die ODBC-Verbindungszeichenfolge zur Verbindung der `CDatabase` Objekt an eine Datenquelle.|  
|[GetCursorCommitBehavior](#getcursorcommitbehavior)|Identifiziert die Auswirkung der Commit einer Transaktion in einem geöffneten Recordset-Objekt.|  
|[Rollback](#getcursorrollbackbehavior)|Identifiziert die Auswirkung von Rollback einer Transaktion in einem geöffneten Recordset-Objekt.|  
|[CDatabase::GetDatabaseName](#getdatabasename)|Gibt den Namen der Datenbank, die derzeit in Verwendung zurück.|  
|[CDatabase::IsOpen](#isopen)|Gibt einen Wert ungleich NULL, wenn die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.|  
|[CDatabase::OnSetOptions](#onsetoptions)|Vom Framework aufgerufen standard Verbindungsoptionen festlegen. Die standardmäßige Implementierung legt den Timeoutwert für Abfragen. Sie können diese Optionen im Voraus einrichten, durch Aufrufen von `SetQueryTimeout`.|  
|[CDatabase:: Open](#open)|Stellt eine Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|  
|[CDatabase:: OpenEx](#openex)|Stellt eine Verbindung mit einer Datenquelle (über einen ODBC-Treiber).|  
|[CDatabase](#rollback)|Kehrt die aktuelle Transaktion vorgenommene Änderungen. Gibt die Datenquelle in den vorherigen Zustand zur definiert die **BeginTrans** Aufruf unverändert.|  
|[CDatabase::SetLoginTimeout](#setlogintimeout)|Legt die Anzahl der Sekunden, nach denen ein Data Source-Verbindungsversuch tritt ein Timeout, fest.|  
|[CDatabase::SetQueryTimeout](#setquerytimeout)|Legt die Anzahl der Sekunden an, nach welcher Datenbank Vorgänge abgefragt werden. Wirkt sich auf alle nachfolgenden Recordset **öffnen**, `AddNew`, **bearbeiten**, und **löschen** aufrufen.|  
  
### <a name="public-data-members"></a>Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CDatabase:: M_hdbc](#m_hdbc)|Verbindungshandle für Open Database Connectivity (ODBC) an eine Datenquelle. Typ **HDBC**.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Datenquelle ist eine bestimmte Instanz der Daten, die von einigen Datenbank-Managementsystem (DBMS) gehostet wird. Beispiele: Microsoft SQL Server, Microsoft Access, Borland dBASE und xBASE. Sie können eine oder mehrere `CDatabase` Objekte in Ihrer Anwendung aktivieren.  
  
> [!NOTE]
>  Wenn Sie mit den Klassen Datenzugriffsobjekte (DAO) statt der Open Database Connectivity (ODBC)-Klassen arbeiten, verwenden Sie die Klasse [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) stattdessen. Weitere Informationen finden Sie im Artikel [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
 Mit `CDatabase`, erstellen eine `CDatabase` Objekt, und rufen die `OpenEx` Member-Funktion. Dadurch wird eine Verbindung geöffnet. Wenn Sie erstellen dann `CRecordset` Objekte auf die verbundene Datenquelle übergeben dem Recordset-Konstruktor einen Zeiger auf die `CDatabase` Objekt. Rufen Sie abschließend die Verbindung mit der **schließen** Member-Funktion und Zerstören der `CDatabase` Objekt. **Schließen** schließt alle Recordsets, die Sie zuvor nicht geschlossen.  
  
 Weitere Informationen zu `CDatabase`, finden Sie in den Artikeln [Datenquelle (ODBC)](../../data/odbc/data-source-odbc.md) und [Übersicht: Datenbank-Programmierung](../../data/data-access-programming-mfc-atl.md).  
  
## <a name="inheritance-hierarchy"></a>Vererbungshierarchie  
 [Von CObject](../../mfc/reference/cobject-class.md)  
  
 `CDatabase`  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  
  
##  <a name="a-namebegintransa--cdatabasebegintrans"></a><a name="begintrans"></a>CDatabase::BeginTrans  
 Rufen Sie diese Memberfunktion zum Starten einer Transaktions mit der verbundenen Datenquelle.  
  
```  
BOOL BeginTrans();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn der Aufruf erfolgreich war und Änderungen manuell nur ein Commit ausgeführt sind; andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einem oder mehreren Aufrufen an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen von einem `CRecordset` Objekt. Vor Beginn einer Transaktions, die `CDatabase` Objekt muss bereits angeschlossen wurden mit der Datenquelle durch Aufrufen seiner `OpenEx` oder **öffnen** Member-Funktion. Um die Transaktion zu beenden, rufen [CommitTrans](#committrans) akzeptieren alle Änderungen an der Datenquelle (und diese ausführen) oder rufen Sie [Rollback](#rollback) auf die gesamte Transaktion abgebrochen. Rufen Sie **BeginTrans** Nachdem Sie alle an der Transaktion beteiligten Recordsets öffnen und als nahe an den tatsächlichen update-Vorgänge wie möglich.  
  
> [!CAUTION]
>  Je nach ODBC-Treibers zum Öffnen eines Recordsets vor dem Aufruf von **BeginTrans** kann zu Problemen führen, wenn der Aufruf von **Rollback**. Überprüfen Sie die Treiber, den Sie verwenden. Beispielsweise müssen bei Verwendung den Microsoft Access-Treiber in der Microsoft ODBC Desktop Driver Pack 3.0 enthalten Sie die Jet-Datenbankmodul-Anforderung berücksichtigen, dass Sie eine Transaktion für jede Datenbank beginnen soll, die einen geöffneten Cursor. In den MFC-Datenbankklassen bedeutet ein geöffneten Cursor ein offenes `CRecordset` Objekt. Weitere Informationen finden Sie unter [Technische Hinweis 68](../../mfc/tn068-performing-transactions-with-the-microsoft-access-7-odbc-driver.md).  
  
 **BeginTrans** Datensätze auf dem Server, abhängig von der angeforderten Parallelität und die Funktionen der Datenquelle möglicherweise auch sperren. Informationen zum Sperren von Daten finden Sie im Artikel [Recordset: Sperren von Datensätzen (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
 Transaktionen werden in diesem Artikel erläutert [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
 **BeginTrans** richtet den Zustand, der die Reihenfolge der Transaktionen zurückgesetzt werden kann (storniert). Übernehmen Sie alle aktuellen Transaktionen, um einen neuen Zustand für Rollbacks herzustellen, rufen Sie dann **BeginTrans** erneut.  
  
> [!CAUTION]
>  Aufrufen von **BeginTrans** erneut ohne Aufruf von **CommitTrans** oder **Rollback** ist ein Fehler.  
  
 Rufen Sie die [CanTransact](#cantransact) Member-Funktion, um festzustellen, ob der Treiber Transaktionen für eine bestimmte Datenbank unterstützt. Sie sollten auch aufrufen [GetCursorCommitBehavior](#getcursorcommitbehavior) und [GetCursorRollbackBehavior](#getcursorrollbackbehavior) um die Unterstützung für die Beibehaltung der Cursor zu bestimmen.  
  
 Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="a-namebindparametersa--cdatabasebindparameters"></a><a name="bindparameters"></a>CDatabase::BindParameters  
 Überschreiben Sie `BindParameters` müssen Sie vor dem Aufruf von Parameter binden [CDatabase:: ExecuteSQL](#executesql).  
  
```  
virtual void BindParameters(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Das Handle der ODBC-Anweisung für das Parameter gebunden werden soll.  
  
### <a name="remarks"></a>Hinweise  
 Dieser Ansatz ist hilfreich, wenn Sie nicht, das Ergebnis benötigen aus einer gespeicherten Prozedur festgelegt.  
  
 Rufen Sie in der Überschreibung **SQLBindParameters** und verwandten ODBC-Funktionen, die Parameter binden. MFC ruft die Überschreibung vor Ihrem Aufruf an `ExecuteSQL`. Sie müssen nicht aufrufen, **SQLPrepare**; `ExecuteSQL` Aufrufe **SQLExecDirect** und zerstört der **Befehls beschäftigt**, die nur einmal verwendet wird.  
  
##  <a name="a-namecancela--cdatabasecancel"></a><a name="cancel"></a>CDatabase::Cancel  
 Rufen Sie diese Memberfunktion, um anzufordern, dass die Datenquelle ein asynchroner Vorgang ausgeführt wird oder ein Prozess von einem zweiten Thread abzubrechen.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Hinweise  
 Beachten Sie, dass die MFC-ODBC-Klassen die asynchronen Verarbeitung nicht mehr verwenden. Um eine asynchrone Operation auszuführen, müssen Sie direkt die ODBC-API-Funktion aufrufen [SQLSetConnectOption](https://msdn.microsoft.com/library/ms713564.aspx). Weitere Informationen finden Sie unter [asynchrone Ausführung](https://msdn.microsoft.com/library/ms713563.aspx) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namecantransacta--cdatabasecantransact"></a><a name="cantransact"></a>CDatabase::CanTransact  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die Datenbank Transaktionen zulässt.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich NULL Recordsets, die mit diesem `CDatabase` Transaktionen werden kann, andernfalls 0.  
  
### <a name="remarks"></a>Hinweise  
 Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="a-namecanupdatea--cdatabasecanupdate"></a><a name="canupdate"></a>CDatabase::CanUpdate  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` Objekt kann Updates.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDatabase` Objekt kann Updates; andernfalls 0, entweder, den Sie die Übergabe **TRUE** in `bReadOnly` Sie beim Öffnen der `CDatabase` Objekt oder die Datenquelle selbst ist schreibgeschützt. Die Datenquelle ist schreibgeschützt, wenn ein Aufruf der ODBC-API-Funktion **SQLGetInfo** für **SQL_DATASOURCE_READ_ONLY** gibt "y".  
  
### <a name="remarks"></a>Hinweise  
 Nicht alle Treiber unterstützt Updates.  
  
##  <a name="a-namecdatabasea--cdatabasecdatabase"></a><a name="cdatabase"></a>CDatabase::CDatabase  
 Erstellt ein `CDatabase`-Objekt.  
  
```  
CDatabase();
```  
  
### <a name="remarks"></a>Hinweise  
 Nach dem Erstellen des Objekts, rufen Sie seine `OpenEx` oder **öffnen** Memberfunktion, die eine Verbindung mit einer angegebenen Datenquelle herzustellen.  
  
 Es können bequem Einbetten der `CDatabase` Objekt in der Dokumentklasse.  
  
### <a name="example"></a>Beispiel  
 Dieses Beispiel veranschaulicht die Verwendung `CDatabase` in einer `CDocument`-Klasse.  
  
 [!code-cpp[NVC_MFCDatabase&#9;](../../mfc/codesnippet/cpp/cdatabase-class_1.h)]  
  
 [!code-cpp[NVC_MFCDatabase&#10;](../../mfc/codesnippet/cpp/cdatabase-class_2.cpp)]  
  
##  <a name="a-nameclosea--cdatabaseclose"></a><a name="close"></a>CDatabase::Close  
 Rufen Sie diese Memberfunktion auf, wenn Sie aus einer Datenquelle trennen möchten.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen alle zugeordneten Recordsets schließen die `CDatabase` -Objekt, bevor Sie diese Memberfunktion aufrufen. Da **schließen** zerstört nicht das `CDatabase` -Objekt, Sie können das Objekt wiederverwenden, indem Sie eine neue Verbindung mit der gleichen Datenquelle oder eine andere Datenquelle zu öffnen.  
  
 Alle ausstehenden `AddNew` oder **bearbeiten** -Anweisungen des Recordsets mit der Datenbank abgebrochen, und alle ausstehenden Transaktionen ein Rollback. Alle Recordsets, die abhängig von der `CDatabase` Objekt bleiben in einem nicht definierten Zustand.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#12;](../../mfc/codesnippet/cpp/cdatabase-class_3.cpp)]  
  
##  <a name="a-namecommittransa--cdatabasecommittrans"></a><a name="committrans"></a>CDatabase:: CommitTrans  
 Rufen Sie diese Memberfunktion nach Abschluss von Transaktionen.  
  
```  
BOOL CommitTrans();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Updates erfolgreich ein Commit ausgeführt wurde; andernfalls 0. Wenn **CommitTrans** Fehler auftreten wird, der Status der Datenquelle ist nicht definiert. Überprüfen Sie die Daten, um den Status zu bestimmen.  
  
### <a name="remarks"></a>Hinweise  
 Eine Transaktion besteht aus einer Reihe von Aufrufen an die `AddNew`, **bearbeiten**, **löschen**, und **Update** Memberfunktionen von einer `CRecordset` -Objekt, das mit einem Aufruf von Beginn der [BeginTrans](#begintrans) Member-Funktion. **CommitTrans** führt einen Commit der Transaktion. Standardmäßig werden Updates sofort ein Commit ausgeführt; Aufrufen von **BeginTrans** bewirkt, dass Engagement von Updates bis verzögert **CommitTrans** aufgerufen wird.  
  
 Bis zum Aufruf von **CommitTrans** um eine Transaktion zu beenden, rufen Sie die [Rollback](#rollback) Memberfunktion, die Transaktion abzubrechen und die Datenquelle in seinem ursprünglichen Zustand belassen. Rufen Sie zunächst eine neue Transaktion **BeginTrans** erneut.  
  
 Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="a-nameexecutesqla--cdatabaseexecutesql"></a><a name="executesql"></a>CDatabase:: ExecuteSQL  
 Rufen Sie diese Memberfunktion auf, wenn Sie direkt einen SQL-Befehl ausführen müssen.  
  
```  
void ExecuteSQL(LPCTSTR lpszSQL);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszSQL`  
 Zeiger auf eine Null-terminierte Zeichenfolge mit einer gültigen SQL-Befehl ausführen. Sie können übergeben einer [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Hinweise  
 Erstellen Sie mit dem Befehl als eine auf Null endende Zeichenfolge. `ExecuteSQL`gibt keine Datensätze zurück. Wenn Sie Datensätze verarbeiten möchten, verwenden Sie stattdessen ein Recordset-Objekt.  
  
 Recordset-Objekte, die Befehle unterstützen, für die Daten auswählen, Einfügen von neuen Datensätzen, Löschen von Datensätzen und Bearbeiten von Datensätzen, werden die meisten Befehle für eine Datenquelle ausgegeben. Nicht alle ODBC-Funktionen wird jedoch direkt unterstützt von den Datenbankklassen, daher müssen Sie möglicherweise gelegentlich einen direkten SQL Aufruf mit `ExecuteSQL`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#13;](../../mfc/codesnippet/cpp/cdatabase-class_4.cpp)]  
  
##  <a name="a-namegetbookmarkpersistencea--cdatabasegetbookmarkpersistence"></a><a name="getbookmarkpersistence"></a>CDatabase:: GetBookmarkPersistence  
 Rufen Sie diese Member-Funktion auf, um die Beibehaltung von Lesezeichen auf einem recordset-Objekt nach bestimmten Vorgängen festzulegen.  
  
```  
DWORD GetBookmarkPersistence() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Eine Bitmaske, die die Vorgänge identifiziert, mit denen Lesezeichen auf einem recordset-Objekt beibehalten werden. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie beispielsweise `CRecordset::GetBookmark` und dann `CRecordset::Requery` aufrufen, ist das Lesezeichen von `GetBookmark` womöglich nicht mehr gültig. Sie sollten `GetBookmarkPersistence` vor `CRecordset::SetBookmark` aufrufen.  
  
 Die folgende Tabelle enthält die Bitmaskenwerten, die für den Rückgabewert von `GetBookmarkPersistence` kombiniert werden können.  
  
|Bitmaskenwert|Lesezeichenbeibehaltung|  
|-------------------|--------------------------|  
|`SQL_BP_CLOSE`|Lesezeichen sind gültig, nachdem ein **Requery** Vorgang.|  
|`SQL_BP_DELETE`|Das Lesezeichen für eine Zeile ist gültig, nachdem ein **löschen** -Vorgang in dieser Zeile.|  
|`SQL_BP_DROP`|Lesezeichen sind gültig, nachdem ein **schließen** Vorgang.|  
|`SQL_BP_SCROLL`|Lesezeichen sind nach jedem gültigen **verschieben** Vorgang. Damit wird mühelos identifiziert, ob Lesezeichen im Datensatz unterstützt werden, wie von `CRecordset::CanBookmark` zurückgegeben.|  
|`SQL_BP_TRANSACTION`|Lesezeichen sind gültig, nachdem eine Transaktion übernommen oder zurückgesetzt wurde.|  
|`SQL_BP_UPDATE`|Das Lesezeichen für eine Zeile ist gültig, nachdem ein **Update** -Vorgang in dieser Zeile.|  
|`SQL_BP_OTHER_HSTMT`|Lesezeichen, die mit einem recordset-Objekt verbunden sind, sind in einem zweiten Datensatz gültig.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen zu Lesezeichen finden Sie im Artikel [Recordset: Lesezeichen und Absolute Positionen (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="a-namegetconnecta--cdatabasegetconnect"></a><a name="getconnect"></a>CDatabase:: Getconnect  
 Rufen Sie diese Memberfunktion auf, um die während des Aufrufs von `OpenEx` oder `Open` verwendete Verbindungszeichenfolge abzurufen, die das `CDatabase`-Objekt mit einer Datenquelle verbunden hat.  
  
```  
const CString GetConnect() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein `const` [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält die Verbindungszeichenfolge, wenn `OpenEx` oder `Open` aufgerufen wurde; andernfalls eine leere Zeichenfolge.  
  
### <a name="remarks"></a>Hinweise  
 Finden Sie unter [CDatabase:: Open](#open) eine Beschreibung wie die Verbindungszeichenfolge erstellt wird.  
  
##  <a name="a-namegetcursorcommitbehaviora--cdatabasegetcursorcommitbehavior"></a><a name="getcursorcommitbehavior"></a>GetCursorCommitBehavior  
 Rufen Sie diese Memberfunktion bestimmt wie eine [CommitTrans](#committrans) Vorgang wirkt sich auf die Cursor bei einem geöffneten Recordset-Objekte.  
  
```  
int GetCursorCommitBehavior() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, der Auswirkung von Transaktionen auf geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Rückgabewerte für `GetCursorCommitBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.  
  
|Rückgabewert|Auswirkung auf CRecordset-Objekte|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Rufen Sie `CRecordset::Requery` unmittelbar nach Commit der Transaktion.|  
|`SQL_CB_DELETE`|Rufen Sie `CRecordset::Close` unmittelbar nach Commit der Transaktion.|  
|`SQL_CB_PRESERVE`|Normal fort, `CRecordset` Vorgänge.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="a-namegetcursorrollbackbehaviora--cdatabasegetcursorrollbackbehavior"></a><a name="getcursorrollbackbehavior"></a>Rollback  
 Rufen Sie diese Memberfunktion bestimmt wie eine [Rollback](#rollback) Vorgang wirkt sich auf die Cursor bei einem geöffneten Recordset-Objekte.  
  
```  
int GetCursorRollbackBehavior() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Wert, der angibt, der Auswirkung von Transaktionen auf geöffneten Recordset-Objekte. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Die folgende Tabelle enthält die möglichen Rückgabewerte für `GetCursorRollbackBehavior` und die entsprechenden Auswirkungen auf das Recordset geöffnet.  
  
|Rückgabewert|Auswirkung auf CRecordset-Objekte|  
|------------------|----------------------------------|  
|`SQL_CB_CLOSE`|Rufen Sie `CRecordset::Requery` unmittelbar nach dem Transaktionsrollback.|  
|`SQL_CB_DELETE`|Rufen Sie `CRecordset::Close` unmittelbar nach dem Transaktionsrollback.|  
|`SQL_CB_PRESERVE`|Normal fort, `CRecordset` Vorgänge.|  
  
 Weitere Informationen zu diesem Rückgabewert finden Sie unter der ODBC-API-Funktion **SQLGetInfo** in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Weitere Informationen über Transaktionen finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="a-namegetdatabasenamea--cdatabasegetdatabasename"></a><a name="getdatabasename"></a>CDatabase::GetDatabaseName  
 Rufen Sie diese Memberfunktion um den Namen der derzeit verbundenen Datenbank abzurufen (vorausgesetzt, dass die Datenquelle ein benanntes Objekt mit dem Namen "Datenbank" definiert).  
  
```  
CString GetDatabaseName() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Ein [CString](../../atl-mfc-shared/reference/cstringt-class.md) , enthält der Name der Datenbank, wenn erfolgreich, andernfalls, wird ein leeres `CString`.  
  
### <a name="remarks"></a>Hinweise  
 Dies ist nicht identisch mit der Datenquellenname (DSN) gemäß der `OpenEx` oder **öffnen** aufrufen. Was `GetDatabaseName` gibt abhängig von ODBC. Im Allgemeinen ist eine Datenbank, eine Auflistung von Tabellen. Wenn diese Entität einen Namen hat, `GetDatabaseName` wird zurückgegeben.  
  
 Möglicherweise möchten Sie z. B. diesen Namen in einer Überschrift anzuzeigen. Tritt ein Fehler beim Abrufen des Namens von ODBC, `GetDatabaseName` gibt ein leeres **Cstring**.  
  
##  <a name="a-nameisopena--cdatabaseisopen"></a><a name="isopen"></a>CDatabase::IsOpen  
 Rufen Sie diese Memberfunktion, um zu bestimmen, ob die `CDatabase` -Objekt aktuell mit einer Datenquelle verbunden ist.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Rückgabewert  
 Einen Wert ungleich null der `CDatabase` Objekt derzeit verbunden ist, andernfalls 0.  
  
##  <a name="a-namemhdbca--cdatabasemhdbc"></a><a name="m_hdbc"></a>CDatabase:: M_hdbc  
 Enthält einen öffentlichen Handle für die Verbindung eine ODBC-Datenquelle â €"ein"Verbindungshandle".  
  
### <a name="remarks"></a>Hinweise  
 In der Regel müssen Sie nicht erforderlich, diese Membervariable direkt zugreifen. Stattdessen das Framework das Handle reserviert beim Aufruf von `OpenEx` oder **öffnen**. Das Framework das Handle freigegeben, beim Aufrufen der **löschen** Operator auf das `CDatabase` Objekt. Beachten Sie, dass die **schließen** Memberfunktion nicht das Handle freizugeben.  
  
 Unter bestimmten Umständen jedoch müssen Sie das Handle direkt verwenden. Wenn Sie ODBC-API-Funktionen direkt und nicht über Klasse aufrufen müssen z. B. `CDatabase`, möglicherweise ein Verbindungshandle als Parameter übergeben. Finden Sie im folgenden Codebeispiel wird ein.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#15;](../../mfc/codesnippet/cpp/cdatabase-class_5.cpp)]  
  
##  <a name="a-nameonsetoptionsa--cdatabaseonsetoptions"></a><a name="onsetoptions"></a>CDatabase::OnSetOptions  
 Das Framework ruft diese Memberfunktion auf, wenn mit eine SQL-Anweisung direkt Ausführen der `ExecuteSQL` Member-Funktion.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Parameter  
 `hstmt`  
 Das Handle der ODBC-Anweisung für das Optionen festgelegt werden.  
  
### <a name="remarks"></a>Hinweise  
 `CRecordset::OnSetOptions`auch aufruft diese Memberfunktion.  
  
 `OnSetOptions`Legt den Wert für das Anmeldungstimeout fest. Wenn frühere Aufrufe wurden die `SetQueryTimeout` und Memberfunktion `OnSetOptions` gibt die aktuellen Werte; andernfalls, legt Standardwerte fest.  
  
> [!NOTE]
>  Vor MFC 4.2 `OnSetOptions` Verarbeitungsmodus auch festlegen, um entweder Snychronous oder asynchron. Ab MFC 4.2, sind alle Vorgänge synchron. Um einen asynchronen Vorgang auszuführen, müssen Sie einen direkten Aufruf der ODBC-API-Funktion, **SQLSetPos**.  
  
 Sie müssen nicht außer Kraft setzen `OnSetOptions` so ändern Sie den Timeoutwert. Um den Wert für das Abfragetimeout anzupassen, rufen Sie stattdessen `SetQueryTimeout` vor dem Erstellen einer Datensatzgruppe; `OnSetOptions` wird der neue Wert verwendet. Die festgelegten Werte gelten für nachfolgende Vorgänge auf alle Recordsets oder direkte SQL-Aufrufe.  
  
 Überschreiben Sie `OnSetOptions` , wenn Sie zusätzliche Optionen festlegen möchten. Überschreiben der Basisklasse aufrufen sollten `OnSetOptions` entweder vor oder nach dem Aufrufen der ODBC-API-Funktion **SQLSetStmtOption**. Führen Sie die Methode in der Implementierung des Frameworks standardmäßig der dargestellten `OnSetOptions`.  
  
##  <a name="a-nameopena--cdatabaseopen"></a><a name="open"></a>CDatabase:: Open  
 Rufen Sie diese Memberfunktion zum Initialisieren einer neu erstellten `CDatabase` Objekt.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszDSN,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T("ODBC;"),  
    BOOL bUseCursorLib = TRUE);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDSN`  
 Gibt eine Datenquelle benennen â €"einen Namen, die mit ODBC registriert ist, über das ODBC-Administratorprogramm. Wenn ein DSN-Wert, in angegeben wird `lpszConnect` (in der Form "DSN =\<Datenquelle >"), muss nicht erneut angegeben werden `lpszDSN`. In diesem Fall `lpszDSN` sollte **NULL**. Andernfalls können Sie übergeben **NULL** Wunsch den Benutzer das Dialogfeld Datenquelle vorhanden, in dem der Benutzer eine Datenquelle auswählen kann. Weitere Informationen finden Sie unter "Hinweise".  
  
 `bExclusive`  
 In dieser Version der Klassenbibliothek unterstützt nicht. Derzeit eine Assertion fehlschlägt, wenn dieser Parameter **TRUE**. Die Datenquelle ist immer geöffnet, wie (nicht exklusiv) freigegeben.  
  
 `bReadOnly`  
 **"True"** Wenn Sie die Verbindung schreibgeschützt sein und Updates für die Datenquelle nicht zulassen möchten. Alle abhängigen Recordsets erben dieses Attribut. Der Standardwert ist **FALSE**.  
  
 `lpszConnect`  
 Gibt eine Verbindungszeichenfolge an. Die Verbindungszeichenfolge verkettet Informationen möglicherweise auch einen Datenquellennamen, eine Benutzer-ID gültig auf die Datenquelle, die eine Authentifizierung Benutzerzeichenfolge (das Kennwort, falls die Datenquelle erfordert) und andere Informationen. Die gesamte Verbindungszeichenfolge muss durch die Zeichenfolge "ODBC;" vorangestellt werden. (Groß- oder Kleinbuchstaben). Die "ODBC"; String wird verwendet, um anzugeben, dass die Verbindung mit einer ODBC-Datenquelle; Dies ist für die Aufwärtskompatibilität, wenn zukünftige Versionen der Klassenbibliothek-ODBC-Datenquellen unterstützen können.  
  
 `bUseCursorLib`  
 **True,** , wenn Sie die ODBC Cursor Library-DLL geladen werden soll. Die Cursorbibliothek maskiert Teil der Funktionalität des zugrunde liegenden ODBC-Treiber effektiv verhindert, dass der Dynasets (wenn der Treiber unterstützt). Nur unterstützt, wenn die Cursorbibliothek geladen ist Cursor sind statische Snapshots und Vorwärtscursor. Der Standardwert ist **TRUE**. Wenn Sie planen, erstellen Sie ein Recordset-Objekt direkt vom `CRecordset` ohne abgeleitet wird, sollten Sie nicht die Cursorbibliothek geladen.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; Abbrechen andernfalls 0, wenn der Benutzer auf, wenn ein Dialogfeld Weitere Verbindungsinformationen angefordert werden angezeigt. In allen anderen Fällen löst das Framework eine Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
 Ihr Database-Objekt muss initialisiert werden, bevor Sie sie verwenden können, um ein Recordset-Objekt zu erstellen.  
  
> [!NOTE]
>  Aufrufen der [OpenEx](#openex) Member-Funktion ist die bevorzugte Methode zum Verbinden mit einer Datenquelle und Initialisieren des Datenbankobjekts.  
  
 Wenn die Parameter in der **öffnen** Aufruf enthalten genügend Informationen zum Herstellen die Verbindung, die der ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer zu erhalten. Beim Aufruf von **öffnen**, die Verbindungszeichenfolge `lpszConnect`, privat in gespeichert ist die `CDatabase` -Objekt und das Aufrufen der [GetConnect](#getconnect) Member-Funktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf von **öffnen** zum Abrufen von Informationen vom Benutzer, z. B. ein Kennwort in die Verbindungszeichenfolge, die Sie, um übergeben diese Informationen dann hinzuzufügen **öffnen**. Oder möglicherweise möchten Sie die Verbindungszeichenfolge, die Sie übergeben, sodass Sie es das nächste wiederverwenden können ruft Ihre Anwendung, Zeit zu sparen **öffnen** auf ein `CDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen des Login-Autorisierung (jeweils ein anderes `CDatabase` Objekt) oder andere Daten spezifischen Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 5 in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Es ist möglich, für eine Verbindung zu einem Timeout, wenn z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, **öffnen** löst eine `CDBException`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&14;](../../mfc/codesnippet/cpp/cdatabase-class_6.cpp)]  
  
##  <a name="a-nameopenexa--cdatabaseopenex"></a><a name="openex"></a>CDatabase:: OpenEx  
 Rufen Sie diese Memberfunktion zum Initialisieren einer neu erstellten `CDatabase` Objekt.  
  
```  
virtual BOOL OpenEx(
    LPCTSTR lpszConnectString,  
    DWORD dwOptions = 0);
```  
  
### <a name="parameters"></a>Parameter  
 `lpszConnectString`  
 Gibt eine ODBC-Verbindungszeichenfolge an. Dies umfasst den Namen der Datenquelle sowie andere optionale Informationen, wie Benutzer-ID und Kennwort. Z. B. "DSN = SQLServer_Source; UID = SA; PWD = "abc123" "ist eine mögliche Verbindungszeichenfolge. Beachten Sie, dass, wenn Sie übergeben **NULL** für `lpszConnectString`, ein Dialogfeld Datenquelle fordert den Benutzer zum Auswählen einer Datenquelle.  
  
 `dwOptions`  
 Eine Bitmaske, die eine Kombination der folgenden Werte angeben. Der Standardwert ist 0, was bedeutet, dass die Datenbank als geöffnet wird, mit Schreibzugriff freigegeben, die ODBC Cursor Library-DLL nicht geladen, und das Dialogfeld ODBC-Verbindung wird nur angezeigt, wenn es nicht genügend Informationen zum Herstellen die Verbindung sind.  
  
- **CDatabase::openExclusive** in dieser Version der Klassenbibliothek nicht unterstützt. Eine Datenquelle ist immer geöffnet, wie (nicht exklusiv) freigegeben. Momentan kann eine Assertion, wenn Sie diese Option angeben.  
  
- **CDatabase::openReadOnly** die Datenquelle als schreibgeschützt zu öffnen.  
  
- **DwOptions** die ODBC-Cursorbibliothek DLL zu laden. Die Cursorbibliothek maskiert Teil der Funktionalität des zugrunde liegenden ODBC-Treiber effektiv verhindert, dass der Dynasets (wenn der Treiber unterstützt). Nur unterstützt, wenn die Cursorbibliothek geladen ist Cursor sind statische Snapshots und Vorwärtscursor. Wenn Sie planen, erstellen Sie ein Recordset-Objekt direkt vom `CRecordset` ohne abgeleitet wird, sollten Sie nicht die Cursorbibliothek geladen.  
  
- **CDatabase::noOdbcDialog** nicht anzeigen klicken Sie im Dialogfeld ODBC-Verbindung unabhängig davon, ob genügend Informationen zur Verbindung bereitgestellt wird.  
  
- **CDatabase::forceOdbcDialog** immer zeigt das Dialogfeld ODBC-Verbindung.  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Verbindung erfolgreich hergestellt wird; Abbrechen andernfalls 0, wenn der Benutzer auf, wenn ein Dialogfeld Weitere Verbindungsinformationen angefordert werden angezeigt. In allen anderen Fällen löst das Framework eine Ausnahme aus.  
  
### <a name="remarks"></a>Hinweise  
 Ihr Database-Objekt muss initialisiert werden, bevor Sie sie verwenden können, um ein Recordset-Objekt zu erstellen.  
  
 Wenn die `lpszConnectString` -Parameter in der `OpenEx` Aufruf enthält nicht genügend Informationen zum Herstellen einer Verbindung, der ODBC-Treiber öffnet ein Dialogfeld, um die erforderlichen Informationen vom Benutzer, zu erhalten, sofern Sie nicht festgelegt haben **CDatabase::noOdbcDialog** oder **CDatabase::forceOdbcDialog** in der `dwOptions` Parameter. Beim Aufruf von `OpenEx`, die Verbindungszeichenfolge `lpszConnectString`, privat in gespeichert ist die `CDatabase` -Objekt und das Aufrufen der [GetConnect](#getconnect) Member-Funktion.  
  
 Wenn Sie möchten, können Sie ein eigenes Dialogfeld öffnen, vor dem Aufruf von `OpenEx` zum Abrufen von Informationen vom Benutzer, z. B. ein Kennwort und die Verbindungszeichenfolge, die Sie, um übergeben diese Information hinzufügen `OpenEx`. Oder möglicherweise möchten Sie die Verbindungszeichenfolge, die Sie übergeben, sodass Sie es das nächste wiederverwenden können ruft Ihre Anwendung, Zeit zu sparen `OpenEx` auf ein `CDatabase` Objekt.  
  
 Sie können auch die Verbindungszeichenfolge für mehrere Ebenen des Login-Autorisierung (jeweils ein anderes `CDatabase` Objekt) oder andere Daten spezifischen Informationen vermitteln. Weitere Informationen zu Verbindungszeichenfolgen finden Sie in Kapitel 6 in der *ODBC Programmer's Reference*.  
  
 Es ist möglich, für eine Verbindung zu einem Timeout, wenn z. B. der DBMS-Host nicht verfügbar ist. Wenn der Verbindungsversuch fehlschlägt, `OpenEx` löst eine `CDBException`.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_MFCDatabase&#11;](../../mfc/codesnippet/cpp/cdatabase-class_7.cpp)]  
  
##  <a name="a-namerollbacka--cdatabaserollback"></a><a name="rollback"></a>CDatabase  
 Rufen Sie diese Memberfunktion, um die während einer Transaktion vorgenommenen Änderungen umzukehren.  
  
```  
BOOL Rollback();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Wert ungleich NULL, wenn die Transaktion erfolgreich umgekehrt wurde; andernfalls 0. Wenn ein **Rollback** Aufruf fehlschlägt, ist die Datenquelle und die Transaktion Zustände sind nicht definiert. Wenn **Rollback** gibt 0 zurück, Sie müssen überprüfen, dass die Datenquelle, um den Status zu bestimmen.  
  
### <a name="remarks"></a>Hinweise  
 Alle `CRecordset``AddNew`, **bearbeiten**, **löschen**, und **Update** seit der letzten ausgeführten [BeginTrans](#begintrans) Rollback in den Zustand, die zum Zeitpunkt dieses Aufrufs vorhanden waren.  
  
 Nach einem Aufruf von **Rollback**, die Transaktion-müssen Sie aufrufen, **BeginTrans** für eine andere Transaktion. Der Datensatz, die vor dem Aufrufen **BeginTrans** wird zum aktuellen Datensatz erneut nach **Rollback**.  
  
 Nach einem Rollback bleibt der Datensatz, der vor dem Rollback war aktuelle. Weitere Informationen über den Zustand des Recordsets und der Datenquelle nach einem Rollback finden Sie im Artikel [Transaktion (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Beispiel  
  Finden Sie im Artikel [Transaktion: Ausführen einer Transaktion in einem Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="a-namesetlogintimeouta--cdatabasesetlogintimeout"></a><a name="setlogintimeout"></a>CDatabase::SetLoginTimeout  
 Rufen Sie diese Funktion Â €"vor dem Aufruf von `OpenEx` oder **öffnen** Â €", überschreiben die Standardanzahl von Sekunden zulässig sind, bevor Sie Daten in einem versuchten quellverbindung ein Timeout auftritt.  
  
```  
void SetLoginTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSeconds`  
 Die Anzahl der Sekunden, bevor ein Verbindungsversuch ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Ein Verbindungsversuch ein Timeout auftreten, wenn Sie z. B. das DBMS nicht verfügbar ist. Rufen Sie **SetLoginTimeout** Nachdem Sie den nicht initialisierten konstruiert `CDatabase` -Objekt, jedoch bevor Sie anrufen `OpenEx` oder **öffnen**.  
  
 Der Standardwert für die Anmeldung Timeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Wert für das Anmeldungstimeout anzugeben. Wenn die Datenquelle Timeout nicht unterstützt, erhalten Sie Ablaufverfolgungsausgabe jedoch keine Ausnahme. Der Wert 0 bedeutet "infinite".  
  
##  <a name="a-namesetquerytimeouta--cdatabasesetquerytimeout"></a><a name="setquerytimeout"></a>CDatabase::SetQueryTimeout  
 Rufen Sie diese Memberfunktion, um die Standardanzahl von Sekunden, bevor nachfolgende Vorgänge auf die verbundene Datenquelle-Timeout zu überschreiben.  
  
```  
void SetQueryTimeout(DWORD dwSeconds);
```  
  
### <a name="parameters"></a>Parameter  
 `dwSeconds`  
 Die Anzahl der Sekunden, bevor der Versuch einer Abfrage ist ein Timeout aufgetreten.  
  
### <a name="remarks"></a>Hinweise  
 Ein Vorgang kann aufgrund von Netzwerkproblemen Zugriff, übermäßige Abfrage Verarbeitungszeit usw. Timeout. Rufen Sie `SetQueryTimeout` vor dem Öffnen des Recordsets oder vor dem Aufrufen des Recordsets `AddNew`, **Update** oder **löschen** Memberfunktionen, wenn Sie den Timeoutwert für Abfragen ändern möchten. Die Einstellung wirkt sich auf alle nachfolgenden **öffnen**, `AddNew`, **Update**, und **löschen** Aufrufe an alle zugeordneten Recordsets `CDatabase` Objekt. Ändern den Timeoutwert für Abfragen für ein Recordset nach öffnen, wird der Wert für das Recordset nicht geändert. Beispielsweise wird bei nachfolgenden **verschieben** Vorgänge verwenden Sie den neuen Wert nicht.  
  
 Der Standardwert für Abfragetimeouts beträgt 15 Sekunden. Nicht alle Datenquellen unterstützen die Möglichkeit, einen Timeoutwert für Abfragen festzulegen. Wenn Sie einen Abfrage-Timeoutwert von 0 festlegen, tritt kein Timeout. die Kommunikation mit der Datenquelle reagiert. Dieses Verhalten kann während der Entwicklung hilfreich sein. Wenn die Datenquelle Timeout nicht unterstützt, erhalten Sie Ablaufverfolgungsausgabe jedoch keine Ausnahme.  
  
## <a name="see-also"></a>Siehe auch  
 [CObject-Klasse](../../mfc/reference/cobject-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CRecordset-Klasse](../../mfc/reference/crecordset-class.md)

