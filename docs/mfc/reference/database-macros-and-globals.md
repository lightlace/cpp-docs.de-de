---
title: Datenbankmakros und globale Variablen
ms.date: 11/04/2016
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
ms.openlocfilehash: 47a1bb434801c24ab8eee048d9ef8f93793101cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62323189"
---
# <a name="database-macros-and-globals"></a>Datenbankmakros und globale Variablen

Die Makros und Globals, die unten aufgeführten gelten für die mit ODBC-basierten datenbankanwendungen. Sie sind nicht mit DAO-basierten Anwendungen verwendet werden.

Bevor MFC-Makros 4.2 `AFX_SQL_ASYNC` und `AFX_SQL_SYNC` hat asynchrone Vorgänge Möglichkeit, Zeit für andere Prozesse zu erhalten. Ab MFC 4.2 ermöglichen die Implementierung dieser Makros, die geändert, da die MFC-ODBC-Klassen nur synchrone Vorgänge verwendet. Das Makro `AFX_ODBC_CALL` wurde noch nicht mit MFC 4.2.

### <a name="database-macros"></a>Datenbankmakros

|||
|-|-|
|[AFX_ODBC_CALL](#afx_odbc_call)|Ruft eine ODBC-API-Funktion, die zurückgibt `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL` wird wiederholt aufrufen die Funktion bis nicht mehr gibt `SQL_STILL_EXECUTING`.|
|[AFX_SQL_ASYNC](#afx_sql_async)|Ruft `AFX_ODBC_CALL`.|
|[AFX_SQL_SYNC](#afx_sql_sync)|Ruft eine ODBC-API-Funktion, die keinen zurückgibt `SQL_STILL_EXECUTING`.|

### <a name="database-globals"></a>Datenbankenglobals

|||
|-|-|
|[AfxDbInitModule](#afxdbinitmodule)|Fügt Unterstützung von Datenbanken für eine reguläre MFC-DLL, die dynamisch mit MFC verknüpft wird.|
|[AfxGetHENV](#afxgethenv)|Ruft ein Handle für die derzeit in der Verwendung von MFC ODBC-Umgebung ab. Sie können dieses Handle in direkte ODBC-Aufrufe verwenden.|

## <a name="afxdbinitmodule"></a> AfxDbInitModule

Für MFC-Datenbank (oder DAO) aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird unterstützen, fügen Sie einen Aufruf dieser Funktion in Ihre regulären MFC DLL des `CWinApp::InitInstance` Datenbank DLL-Funktion, die die MFC-Bibliothek zu initialisieren.

### <a name="syntax"></a>Syntax

```
void AFXAPI AfxDbInitModule( );
```

### <a name="remarks"></a>Hinweise

Stellen Sie sicher, dass dieser Aufruf erfolgt vor dem Aufruf Basisklasse oder einem der hinzugefügten Code, der Zugriff auf die Datenbank der MFC-DLL. Die Datenbank-MFC-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired erhalten eine `CDynLinkLibrary` Kette, müssen sie erstellen eine `CDynLinkLibrary` Objekt im Kontext von jedem Modul, die sie verwenden möchten. `AfxDbInitModule` erstellt die `CDynLinkLibrary` Objekts in Ihre regulären MFC DLL Kontext, sodass es in wired Ruft die `CDynLinkLibrary` Objekt Kette von der regulären MFC-DLL.

### <a name="requirements"></a>Anforderungen

**Header:** \<afxdll_.h>

##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL

Verwenden Sie dieses Makro alle ODBC-API-Funktion aufrufen, die möglicherweise zurückgeben `SQL_STILL_EXECUTING`.

```
AFX_ODBC_CALL(SQLFunc)
```

### <a name="parameters"></a>Parameter

*SQLFunc*<br/>
Eine ODBC-API-Funktion. Weitere Informationen zu ODBC API-Funktionen finden Sie im Windows-SDK.

### <a name="remarks"></a>Hinweise

`AFX_ODBC_CALL` Ruft wiederholt die Funktion bis nicht mehr gibt `SQL_STILL_EXECUTING`.

Vor dem Aufrufen `AFX_ODBC_CALL`, müssen Sie eine Variable deklarieren `nRetCode`, vom Typ "RETCODE".

Beachten Sie, dass die MFC-ODBC-jetzt verwenden nur synchrone Verarbeitung Klassen. Um einen asynchronen Vorgang ausführen zu können, müssen Sie die ODBC-API-Funktion aufrufen `SQLSetConnectOption`. Weitere Informationen finden Sie im Thema "Ausführen von Funktionen asynchron" im Windows SDK.

### <a name="example"></a>Beispiel

Dieses Beispiel verwendet `AFX_ODBC_CALL` zum Aufrufen der `SQLColumns` ODBC API-Funktion, die eine Liste der Spalten in der Tabelle durch zurückgibt `strTableName`. Beachten Sie die Deklaration der `nRetCode` und die Verwendung der Datenmember zum Übergeben von Parametern an die Funktion des Recordsets. Das Beispiel zeigt auch, überprüfen die Ergebnisse des Aufrufs mit `Check`, eine Memberfunktion der Klasse `CRecordset`. Die Variable `prs` ist ein Zeiger auf eine `CRecordset` Objekt, das an anderer Stelle deklariert.

[!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]

### <a name="requirements"></a>Anforderungen

**Header:** afxdb.h

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC

Die Implementierung dieses Makros in MFC 4.2 geändert.

```
AFX_SQL_ASYNC(prs, SQLFunc)
```

### <a name="parameters"></a>Parameter

*Pull Requests*<br/>
Ein Zeiger auf eine `CRecordset` Objekt oder ein `CDatabase` Objekt. Ab MFC 4.2 wird Wert dieses Parameters ignoriert.

*SQLFunc*<br/>
Eine ODBC-API-Funktion. Weitere Informationen zu ODBC API-Funktionen finden Sie im Windows-SDK.

### <a name="remarks"></a>Hinweise

`AFX_SQL_ASYNC` Ruft das Makro [AFX_ODBC_CALL](#afx_odbc_call) und ignoriert die *Prs* Parameter. In den Vorgängerversionen von MFC 4.2 `AFX_SQL_ASYNC` wurde verwendet, um die ODBC-API-Funktionen aufrufen, die möglicherweise zurückgeben `SQL_STILL_EXECUTING`. Wenn eine ODBC-API-Funktion zurückgegeben hat `SQL_STILL_EXECUTING`, klicken Sie dann `AFX_SQL_ASYNC` aufrufen würde `prs->OnWaitForDataSource`.

> [!NOTE]
>  Die MFC-ODBC-Klassen verwenden jetzt nur die synchrone Verarbeitung. Um einen asynchronen Vorgang ausführen zu können, müssen Sie die ODBC-API-Funktion aufrufen `SQLSetConnectOption`. Weitere Informationen finden Sie im Thema "Ausführen von Funktionen asynchron" im Windows SDK.

### <a name="requirements"></a>Anforderungen

  **Header** afxdb.h

##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC

Die `AFX_SQL_SYNC` -Makro ruft einfach die Funktion `SQLFunc`.

```
AFX_SQL_SYNC(SQLFunc)
```

### <a name="parameters"></a>Parameter

*SQLFunc*<br/>
Eine ODBC-API-Funktion. Weitere Informationen zu diesen Funktionen finden Sie im Windows-SDK.

### <a name="remarks"></a>Hinweise

Verwenden Sie dieses Makro ODBC API-Funktionen aufrufen, die keine zurück `SQL_STILL_EXECUTING`.

Vor dem Aufruf `AFX_SQL_SYNC`, müssen Sie eine Variable deklarieren `nRetCode`, vom Typ "RETCODE". Sehen Sie den Wert der `nRetCode` nach dem Makroaufruf.

Beachten Sie, dass die Implementierung der `AFX_SQL_SYNC` in MFC 4.2 geändert. Da überprüft den Status des Servers nicht mehr erforderlich ist, war `AFX_SQL_SYNC` einfach ein Wert zugewiesen `nRetCode`. Beispiel: anstelle von dem Aufruf

[!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]

Sie können einfach über die Zuweisung machen.

[!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]

### <a name="requirements"></a>Anforderungen

  **Header** afxdb.h

##  <a name="afxgethenv"></a>  AfxGetHENV

Sie können das zurückgegebene Handle in direkte ODBC-Aufrufe verwenden, aber Sie müssen nicht das Handle geschlossen oder davon ausgehen, dass das Handle nach der alle vorhandenen noch gültig und verfügbar ist `CDatabase`- oder `CRecordset`-abgeleitete Objekte zerstört wurden.

```
HENV AFXAPI AfxGetHENV();
```

### <a name="return-value"></a>Rückgabewert

Das Handle für die derzeit in der Verwendung von MFC ODBC-Umgebung. Kann `SQL_HENV_NULL` treten keine [CDatabase](../../mfc/reference/cdatabase-class.md) Objekte und keine [CRecordset](../../mfc/reference/crecordset-class.md) verwendeten Objekten.

### <a name="requirements"></a>Anforderungen

  **Header** afxdb.h

## <a name="see-also"></a>Siehe auch

[Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
