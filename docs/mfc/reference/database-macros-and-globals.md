---
title: Datenbankmakros und globale Variablen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- AFXDB/AFX_ODBC_CALL
- AFXDB/AFX_SQL_ASYNC
- AFXDB/AFX_SQL_SYNC
- AFXDB/AfxGetHENV
dev_langs:
- C++
helpviewer_keywords:
- global database functions [MFC]
- database macros [MFC]
- database globals [MFC]
- global functions [MFC], database functions
- macros [MFC], MFC database
ms.assetid: 5b9b9e61-1cf9-4345-9f29-3807dd466488
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bcafff20ad79f68f2bb5d4195c38603da63b9d17
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="database-macros-and-globals"></a>Datenbankmakros und globale Variablen
Die Makros und Globals, die unten aufgeführten gelten für ODBC-basierten datenbankanwendungen. Sie werden nicht mit DAO-basierten Anwendungen verwendet.  
  
 Bevor MFC 4.2, die Makros `AFX_SQL_ASYNC` und `AFX_SQL_SYNC` gegeben asynchrone Vorgänge die Gelegenheit zur Zeit für andere Prozesse zu erhalten. Ab MFC 4.2, die Implementierung dieser Makros geändert, da die MFC-ODBC-Klassen nur synchrone Vorgänge verwendet. Das Makro `AFX_ODBC_CALL` wurde noch nicht mit MFC 4.2.  
  
### <a name="database-macros"></a>Datenbankmakros  
  
|||  
|-|-|  
|[AFX_ODBC_CALL](#afx_odbc_call)|Ruft eine ODBC-API-Funktion, die zurückgibt `SQL_STILL_EXECUTING`. `AFX_ODBC_CALL` wird wiederholt aufrufen die Funktion bis nicht mehr gibt `SQL_STILL_EXECUTING`.|  
|[AFX_SQL_ASYNC](#afx_sql_async)|Ruft `AFX_ODBC_CALL`.|  
|[AFX_SQL_SYNC](#afx_sql_sync)|Ruft eine ODBC-API-Funktion, die keinen zurückgibt `SQL_STILL_EXECUTING`.|  
  
### <a name="database-globals"></a>Datenbankenglobals  
  
|||  
|-|-| 
|[AfxDbInitModule](#afxdbinitmodule)|Fügt der datenbankunterstützung für eine reguläre MFC-DLL, die dynamisch mit MFC verknüpft wird.| 
|[AfxGetHENV](#afxgethenv)|Ruft ein Handle für die aktuell in Verwendung von MFC ODBC-Umgebung ab. Sie können dieses Handle in direkte ODBC-Aufrufe.|  


## <a name="afxdbinitmodule"></a> AfxDbInitModule
Für MFC-Datenbank (oder DAO) aus einer regulären MFC-DLL, die dynamisch mit MFC verknüpft wird unterstützen, fügen Sie einen Aufruf dieser Funktion in der regulären MFC DLL **CWinApp:: InitInstance** Datenbank Funktion initialisiert werden, die MFC-DLL.  
   
### <a name="syntax"></a>Syntax    
```
void AFXAPI AfxDbInitModule( );    
```  
   
### <a name="remarks"></a>Hinweise  
 Stellen Sie sicher, dass dieser Aufruf erfolgt vor irgendeinem Aufruf der Basisklasse oder alle hinzugefügten Code den Zugriff auf die Datenbank der MFC-DLL. Die Datenbank-MFC-DLL ist eine MFC-Erweiterungs-DLL. in der Reihenfolge für eine MFC-Erweiterungs-DLL in wired Abrufen einer **CDynLinkLibrary** Kette, müssen sie erstellen eine **CDynLinkLibrary** Objekt im Kontext von jedem Modul, das sie verwenden möchten. `AfxDbInitModule` erstellt die **CDynLinkLibrary** Objekt im Kontext der regulären MFC DLL, sodass es in wired Ruft die **CDynLinkLibrary** Kette von regulären MFC-DLL-Objekt.  
   
### <a name="requirements"></a>Anforderungen  
 **Header:** < afxdll_.h >  
   
### <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](mfc-macros-and-globals.md)
 
  

##  <a name="afx_odbc_call"></a>  AFX_ODBC_CALL  
 Verwenden Sie dieses Makro jede ODBC-API-Funktion aufrufen, die möglicherweise zurückgeben `SQL_STILL_EXECUTING`.  
  
```  
AFX_ODBC_CALL(SQLFunc)  
```  
  
### <a name="parameters"></a>Parameter  
 `SQLFunc`  
 Eine ODBC-API-Funktion. Weitere Informationen zu ODBC-API-Funktionen finden Sie im Windows-SDK.  
  
### <a name="remarks"></a>Hinweise  
 `AFX_ODBC_CALL` wiederholt Ruft die Funktion bis nicht mehr gibt `SQL_STILL_EXECUTING`.  
  
 Vor dem Aufrufen `AFX_ODBC_CALL`, müssen Sie eine Variable deklarieren `nRetCode`, des Typs **RETCODE**.  
  
 Beachten Sie, dass die MFC-ODBC-jetzt verwenden nur die synchrone Verarbeitung Klassen. Um einen asynchronen Vorgang ausführen zu können, müssen Sie die ODBC-API-Funktion aufrufen **SQLSetConnectOption**. Weitere Informationen finden Sie im Thema "Ausführen von Funktionen asynchron" im Windows SDK.  

  
### <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet `AFX_ODBC_CALL` zum Aufrufen der **SQLColumns** ODBC API-Funktion, die eine Liste der Spalten in der Tabelle mit dem Namen von zurückgibt `strTableName`. Beachten Sie die Deklaration von `nRetCode` und die Verwendung des Recordset-Datenmember können Parameter an die Funktion übergeben. Das Beispiel zeigt darüber hinaus Überprüfen der Ergebnisse des Aufrufs mit **überprüfen**, eine Memberfunktion der Klasse `CRecordset`. Die Variable `prs` ist ein Zeiger auf ein `CRecordset` Objekt, das an anderer Stelle deklariert.  
  
 [!code-cpp[NVC_MFCDatabase#39](../../mfc/codesnippet/cpp/database-macros-and-globals_1.cpp)]  

### <a name="requirements"></a>Anforderungen  
 **Header:** afxdb.h  

##  <a name="afx_sql_async"></a>  AFX_SQL_ASYNC  
 Die Implementierung dieses Makros in MFC 4.2 geändert.  
  
```   
AFX_SQL_ASYNC(prs, SQLFunc)   
```  
  
### <a name="parameters"></a>Parameter  
 `prs`  
 Ein Zeiger auf eine `CRecordset` Objekt oder ein `CDatabase` Objekt. Ab MFC 4.2, wird dieser Parameterwert ignoriert.  
  
 `SQLFunc`  
 Eine ODBC-API-Funktion. Weitere Informationen zu ODBC-API-Funktionen finden Sie im Windows-SDK.  
  
### <a name="remarks"></a>Hinweise  
 `AFX_SQL_ASYNC` Ruft einfach das Makro [AFX_ODBC_CALL](#afx_odbc_call) und ignoriert die `prs` Parameter. In den Vorgängerversionen von MFC 4.2 `AFX_SQL_ASYNC` wurde verwendet, um ODBC API-Funktionen aufzurufen, die möglicherweise zurückgeben `SQL_STILL_EXECUTING`. Wenn eine ODBC-API-Funktion zurückgab `SQL_STILL_EXECUTING`, klicken Sie dann `AFX_SQL_ASYNC` aufrufen würde `prs->OnWaitForDataSource`.  
  
> [!NOTE]
>  Die MFC-ODBC-Klassen verwenden jetzt nur die synchrone Verarbeitung. Um einen asynchronen Vorgang ausführen zu können, müssen Sie die ODBC-API-Funktion aufrufen **SQLSetConnectOption**. Weitere Informationen finden Sie im Thema "Ausführen von Funktionen asynchron" im Windows SDK.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdb.h  
  
##  <a name="afx_sql_sync"></a>  AFX_SQL_SYNC  
 Die `AFX_SQL_SYNC` -Makro ruft einfach die Funktion `SQLFunc`.  
  
```   
AFX_SQL_SYNC(SQLFunc)   
```  
  
### <a name="parameters"></a>Parameter  
 `SQLFunc`  
 Eine ODBC-API-Funktion. Weitere Informationen zu diesen Funktionen finden Sie im Windows-SDK.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie dieses Makro ODBC API-Funktionen aufrufen, die keine zurückgeben wird `SQL_STILL_EXECUTING`.  
  
 Vor dem Aufruf `AFX_SQL_SYNC`, müssen Sie eine Variable deklarieren `nRetCode`, des Typs **RETCODE**. Sehen Sie sich den Wert des `nRetCode` nach dem Makroaufruf.  
  
 Beachten Sie, dass die Implementierung von `AFX_SQL_SYNC` in MFC 4.2 geändert. Da überprüft den Status des Servers nicht mehr erforderlich ist, wurde `AFX_SQL_SYNC` einfach ein Wert zugewiesen `nRetCode`. Beispielsweise anstatt der Aufruf  
  
 [!code-cpp[NVC_MFCDatabase#40](../../mfc/codesnippet/cpp/database-macros-and-globals_2.cpp)]  
  
 Sie können einfach die Zuweisung vornehmen.  
  
 [!code-cpp[NVC_MFCDatabase#41](../../mfc/codesnippet/cpp/database-macros-and-globals_3.cpp)]  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdb.h  
  
##  <a name="afxgethenv"></a>  AfxGetHENV  
 Sie können das zurückgegebene Handle in direkte ODBC-Aufrufe verwenden, jedoch müssen Sie nicht das Handle geschlossen oder davon ausgehen, dass das Handle nach der alle vorhandenen noch gültig und verfügbar ist `CDatabase`- oder `CRecordset`-abgeleitete Objekte zerstört wurden.  
  
```   
HENV AFXAPI AfxGetHENV(); 
```  
  
### <a name="return-value"></a>Rückgabewert  
 Das Handle für die aktuell in Verwendung von MFC ODBC-Umgebung. Kann `SQL_HENV_NULL` treten keine [CDatabase](../../mfc/reference/cdatabase-class.md) -Objekt und keine [CRecordset](../../mfc/reference/crecordset-class.md) -Objekte.  
  
### <a name="requirements"></a>Anforderungen  
  **Header** afxdb.h  
    
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Variablen](../../mfc/reference/mfc-macros-and-globals.md)
