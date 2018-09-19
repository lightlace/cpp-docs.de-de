---
title: CDataSource-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.CDataSource
- ATL::CDataSource
- CDataSource
- ATL::CDataSource::Close
- ATL.CDataSource.Close
- CDataSource::Close
- CDataSource.Close
- ATL::CDataSource::GetInitializationString
- CDataSource.GetInitializationString
- GetInitializationString
- CDataSource::GetInitializationString
- ATL.CDataSource.GetInitializationString
- CDataSource::GetProperties
- ATL.CDataSource.GetProperties
- CDataSource.GetProperties
- ATL::CDataSource::GetProperties
- GetProperties
- ATL::CDataSource::GetProperty
- ATL.CDataSource.GetProperty
- CDataSource.GetProperty
- CDataSource::GetProperty
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
- CDataSource::OpenFromFileName
- ATL::CDataSource::OpenFromFileName
- OpenFromFileName
- CDataSource.OpenFromFileName
- ATL.CDataSource.OpenFromFileName
- CDataSource.OpenFromInitializationString
- OpenFromInitializationString
- CDataSource::OpenFromInitializationString
- ATL::CDataSource::OpenFromInitializationString
- ATL.CDataSource.OpenFromInitializationString
- CDataSource.OpenWithPromptFileName
- OpenWithPromptFileName
- ATL::CDataSource::OpenWithPromptFileName
- ATL.CDataSource.OpenWithPromptFileName
- CDataSource::OpenWithPromptFileName
- CDataSource::OpenWithServiceComponents
- OpenWithServiceComponents
- CDataSource.OpenWithServiceComponents
dev_langs:
- C++
helpviewer_keywords:
- CDataSource class
- Close method
- GetInitializationString method
- GetProperties method
- GetProperty method
- Open method
- OpenFromFileName method
- OpenFromInitializationString method
- OpenWithPromptFileName method
- OpenWithServiceComponents method
ms.assetid: 99bf862c-9d5c-4117-9501-aa0e2672085c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: df5a93ae8b646eb0b4f012484ef8c13d07d328da
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106310"
---
# <a name="cdatasource-class"></a>CDataSource-Klasse

Entspricht einer OLE DB-Datenquellenobjekt, das eine Verbindung über einen Anbieter mit einer Datenquelle darstellt.  
  
## <a name="syntax"></a>Syntax

```cpp
class CDataSource  
```  

## <a name="requirements"></a>Anforderungen  

**Header:** atldbcli.h 
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[Schließen](#close)|Schließt die Verbindung.|  
|[GetInitializationString](#getinitializationstring)|Ruft die Initialisierungszeichenfolge der Datenquelle, die derzeit geöffnet ist.|  
|[GetProperties](#getproperties)|Ruft die Werte der Eigenschaften, die derzeit für die verbundene Datenquelle festgelegt.|  
|[GetProperty](#getproperty)|Ruft den Wert einer einzelnen Eigenschaft, die derzeit für die verbundene Datenquelle festgelegt.|  
|[Öffnen](#open)|Erstellt eine Verbindung zu einem Anbieter (Datenquelle) entweder eine `CLSID`, `ProgID`, oder ein `CEnumerator` Moniker, die vom Aufrufer bereitgestellt wird.|  
|[OpenFromFileName](#openfromfilename)|Öffnet eine Datenquelle aus einer Datei, die durch den vom Benutzer bereitgestellten Dateinamen angegeben wird.|  
|[OpenFromInitializationString](#openfrominitializationstring)|Öffnet die Datenquelle, die von einer Initialisierungszeichenfolge angegeben.|  
|[OpenWithPromptFileName](#openwithpromptfilename)|Ermöglicht dem Benutzer, wählen Sie eine zuvor erstellte Data Link-Datei, um den entsprechenden Datenquellentyp zu öffnen.|  
|[OpenWithServiceComponents](#openwithservicecomponents)|Öffnet ein Datenquellenobjekt, das mit dem Data Link-Dialogfeld.|  
  
## <a name="remarks"></a>Hinweise  

Mindestens eine Datenbank-ereignissitzungen können für eine einzelne Verbindung erstellt werden. Diese Sitzungen werden durch dargestellt `CSession`. Rufen Sie [CDataSource:: Open](../../data/oledb/cdatasource-open.md) zum Öffnen der Verbindung vor dem Erstellen einer Sitzungs mit `CSession::Open`.  
  
Ein Beispiel zur Verwendung für `CDataSource`, finden Sie unter den [CatDB](../../visual-cpp-samples.md) Beispiel.  

## <a name="close"></a> CDataSource:: Close

Schließt die Verbindung durch die Freigabe der `m_spInit` Zeiger.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void Close() throw();  
``` 

## <a name="getinitializationstring"></a> CDataSource:: Getinitializationstring

Ruft die Initialisierungszeichenfolge für die Datenquelle, die derzeit geöffnet ist.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetInitializationString(BSTR* pInitializationString,   
   bool bIncludePassword = false) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*pInitializationString*<br/>
[out] Ein Zeiger auf die Initialisierungszeichenfolge.  
  
*bIncludePassword*<br/>
[in] **"true"** Wenn Zeichenfolge enthält, ein Kennwort ein; andernfalls **"false"**.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Die resultierende Initialisierungszeichenfolge kann verwendet werden, um diese datenquellenverbindung später erneut zu öffnen. 
 
## <a name="getproperties"></a> CDataSource:: GetProperties

Gibt Informationen über die Eigenschaft für das verbundene Objekt angefordert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetProperties(ULONG ulPropIDSets,   
   constDBPROPIDSET* pPropIDSet,   
   ULONG* pulPropertySets,   
   DBPROPSET** ppPropsets) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

Finden Sie unter [IDBProperties:: GetProperties](/previous-versions/windows/desktop/ms714344\(v=vs.85\)) in die *OLE DB-Programmierreferenz* in das Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Verwenden Sie zum Abrufen einer einzelnen Eigenschaft [GetProperty](../../data/oledb/cdatasource-getproperty.md).

## <a name="getproperty"></a> CDataSource:: GetProperty

Gibt den Wert einer angegebenen Eigenschaft für das verbundene Objekt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT GetProperty(const GUID& guid,   
   DBPROPID propid,   
   VARIANT* pVariant) const throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*GUID*<br/>
[in] Eine GUID zum Identifizieren des Eigenschaftensatzes für die Eigenschaft zurückgegeben werden sollen.  
  
*PROPID*<br/>
[in] Eigenschafts-ID für die Eigenschaft zurückgegeben.  
  
*pVariant*<br/>
[out] Ein Zeiger auf die Variante, in denen `GetProperty` gibt den Wert der Eigenschaft zurück.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Rufen Sie mehrere Eigenschaften mit [GetProperties](../../data/oledb/cdatasource-getproperties.md).

## <a name="open"></a> CDataSource:: Open

Öffnet eine Verbindung mit einer Datenquelle mithilfe einer `CLSID`, `ProgID`, oder `CEnumerator` Moniker oder zeigt dem Benutzer ein locatordialogfeld.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT Open(const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  


HRESULT Open(const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();HRESULT Open(LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();HRESULT Open(LPCTSTR szProgID,  
   LPCTSTR pName,  LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1) throw();  

HRESULT Open(const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0) throw();  

HRESULT Open(HWND hWnd = GetActiveWindow(),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET) throw();

HRESULT Open(LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1) throw();

HRESULT Open(LPCSTR szProgID,   
   LPCTSTR pName,LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*clsid*<br/>
[in] Die `CLSID` des Datenanbieters.  
  
*pPropSet*<br/>
[in] Ein Zeiger auf ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen, die Eigenschaften und Werte festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](/previous-versions/windows/desktop/ms713696\(v=vs.85\)) in die *OLE DB-Programmierreferenz* in das Windows SDK.  
  
*nPropertySets*<br/>
[in] Die Anzahl der [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen zu übergeben, der *DBPROPSET* Argument.  
  
*pName*<br/>
[in] Der Name der Datenbank, zu der eine Verbindung hergestellt werden soll.  
  
*pUserName*<br/>
[in] Der Name des Benutzers.  
  
*pPassword*<br/>
[in] Das Benutzerkennwort.  
  
*nInitMode*<br/>
[in] Initialisierungsmodus der Datenbank. Finden Sie unter [Eigenschaften zur Datenquelleninitialisierung](/previous-versions/windows/desktop/ms723127\(v=vs.85\))in die *OLE DB-Programmierreferenz* im Windows SDK für eine Liste gültiger initialisierungsmodi. Wenn *nInitMode* ist 0 (null), ohne Initialisierung Modus ist in der zum Öffnen der Verbindung verwendeten Eigenschaftensatz enthalten.  
  
*szProgID*<br/>
[in] Ein Programmbezeichner.  
  
*enumerator*<br/>
[in] Ein [CEnumerator](../../data/oledb/cenumerator-class.md) Objekt zum Abrufen eines Monikers zum Öffnen der Verbindung, wenn der Aufrufer nicht angegeben ist, verwendet eine `CLSID`.  
  
*hWnd*<br/>
[in] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll. Mit der funktionsüberladung, die verwendet die *hWnd* Parameter werden Dienstkomponenten automatisch aufgerufen; Siehe Hinweise für Details.  
  
*dwPromptOptions*<br/>
[in] Bestimmt den Stil des anzuzeigenden Locatordialogfelds. Mögliche Werte sind in Msdasc.h aufgeführt.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Die methodenüberladung, die verwendet die *hWnd* Parameter öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; diese DLL enthält die Implementierung von dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Eintragung von Transaktionen und So weiter. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference unter [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
Die methodenüberladungen, die keine verwenden die *hWnd* Parameter öffnen ein Datenquellenobjekt ohne mit den Dienstkomponenten im oledb32.dll. Ein [CDataSource](../../data/oledb/cdatasource-class.md) -Objekt, mit diesen funktionsüberladungen geöffnet wird in der Lage, die Funktionalität von Dienstkomponenten zu nutzen.  
  
### <a name="example"></a>Beispiel  

Der folgende Code zeigt, wie eine Jet 4.0-Datenquelle mit OLE DB-Vorlagen geöffnet werden kann. Die Jet-Datenquelle wird OLE DB-Datenquelle behandelt. Allerdings den Aufruf von `Open` zwei Eigenschaftensätze: für DBPROPSET_DBINIT und die andere für DBPROPSET_JETOLEDB_DBINIT, sodass Sie DBPROP_JETOLEDB_DATABASEPASSWORD festlegen können.  
  
[!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  

## <a name="openfromfilename"></a> CDataSource:: Openfromfilename

Öffnet eine Datenquelle aus einer Datei, die durch den vom Benutzer bereitgestellten Dateinamen angegeben wird.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenFromFileName(LPCOLESTR szFileName) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*szFileName*<br/>
[in] Der Name einer Datei, in der Regel eine Datenquellenverbindungsdatei (UDL-Datei).  
  
Weitere Informationen zu Datenverknüpfungsdateien (UDL-Dateien), finden Sie unter [Data Link-API – Übersicht](/previous-versions/windows/desktop/ms718102\(v=vs.85\)) im Windows SDK.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference unter [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  

## <a name="openfrominitializationstring"></a> CDataSource:: OpenFromInitializationString

Öffnet eine Datenquelle, die vom Benutzer bereitgestellten Initialisierungszeichenfolge angegeben.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenFromInitializationString(LPCOLESTR szInitializationString,   
   bool fPromptForInfo= false) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*szInitializationString*<br/>
[in] Die Initialisierungszeichenfolge.  
  
*fPromptForInfo*<br/>
[in] Wenn dieses Argument, um festgelegt wird **"true"**, klicken Sie dann `OpenFromInitializationString` wird, legen Sie die DBPROP_INIT_PROMPT-Eigenschaft auf DBPROMPT_COMPLETEREQUIRED, der angibt, dass der Benutzer aufgefordert werden, nur, wenn Sie weitere Informationen benötigt werden. Dies eignet sich für Situationen, in denen Initialisierungszeichenfolge eine Datenbank angibt, die ein Kennwort erforderlich ist, aber die Zeichenfolge enthält nicht das Kennwort. Der Benutzer wird aufgefordert werden, für ein Kennwort (oder die fehlenden Informationen) beim Versuch, mit der Datenbank herstellen.  
  
Der Standardwert ist **"false"**, der angibt, dass der Benutzer niemals aufgefordert (Gruppen DBPROP_INIT_PROMPT auf DBPROMPT_NOPROMPT) sein.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  

## <a name="openwithpromptfilename"></a> CDataSource:: Openwithpromptfilename

Mit dieser Methode wird dem Benutzer ein Dialogfeld angezeigt und anschließend eine Datenquelle mithilfe der vom Benutzer angegebenen Datei geöffnet.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenWithPromptFileName(HWND hWnd = GetActiveWindow(   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL) throw();  
```  
  
#### <a name="parameters"></a>Parameter  

*hWnd*<br/>
[in] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll.  
  
*dwPromptOptions*<br/>
[in] Bestimmt den Stil des anzuzeigenden Locatordialogfelds. Mögliche Werte sind in Msdasc.h aufgeführt.  
  
*szInitialDirectory*<br/>
[in] Das im Locatordialogfeld anzuzeigende Ausgangsverzeichnis.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference unter [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).

## <a name="openwithservicecomponents"></a> CDataSource:: Openwithservicecomponents

Öffnet ein Datenquellenobjekt mithilfe der Dienstkomponenten in „oledb32.dll“.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT OpenWithServiceComponents (const CLSID clsid,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  

HRESULT OpenWithServiceComponents (LPCSTR szProgID,  
   DBPROPSET* pPropset = NULL,  
   ULONG ulPropSets = 1);  
```  
  
#### <a name="parameters"></a>Parameter  

*clsid*<br/>
[in] Die `CLSID` eines Datenanbieters.  
  
*szProgID*<br/>
[in] Programm-ID eines Datenanbieters.  
  
*DBPROPSET*<br/>
[in] Ein Zeiger auf ein Array von [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen, die Eigenschaften und Werte festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](/previous-versions/windows/desktop/ms713696\(v=vs.85\)) in die *OLE DB-Programmierreferenz* in das Windows SDK. Wenn das Datenquellenobjekt initialisiert wird, müssen die Eigenschaften zur Eigenschaftsquelle „Datenquelle“ gehören. Wenn die gleiche Eigenschaft in mehr als einmal angegeben ist *DBPROPSET*, dann ist der anbieterspezifischen welcher Wert verwendet wird. Wenn *UlPropSets* 0 (null), ist dieser Parameter wird ignoriert.  
  
*ulPropSets*<br/>
[in] Die Anzahl der [DBPROPSET](/previous-versions/windows/desktop/ms714367\(v=vs.85\)) Strukturen zu übergeben, der *DBPROPSET* Argument. Wenn dies 0 (null) ist, ignoriert der Anbieter *DBPROPSET*.  
  
### <a name="return-value"></a>Rückgabewert  

Ein standard-HRESULT.  
  
### <a name="remarks"></a>Hinweise  

Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfunktionen wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference unter [ https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true ](https://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).    

## <a name="see-also"></a>Siehe auch  

[OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[Referenz der OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)