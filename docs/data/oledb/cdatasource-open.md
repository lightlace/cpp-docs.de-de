---
title: 'CDataSource:: Open | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CDataSource::Open
- ATL.CDataSource.Open
- CDataSource::Open
- CDataSource.Open
dev_langs: C++
helpviewer_keywords: Open method
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f76c46dbef341639dbaf0f468510b6d4cbe5a1c6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="cdatasourceopen"></a>CDataSource::Open
Öffnet eine Verbindung mit einer Datenquelle mit einem **CLSID**, **ProgID**, oder `CEnumerator` Moniker oder zeigt dem Benutzer ein locatordialogfeld.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      HRESULT Open(  
   const CLSID& clsid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CLSID& clsid,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   LPCTSTR szProgID,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   DBPROPSET* pPropSet = NULL,  
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(  
   const CEnumerator& enumerator,  
   LPCTSTR pName,  
   LPCTSTR pUserName = NULL,  
   LPCTSTR pPassword = NULL,  
   long nInitMode = 0   
) throw( );  
HRESULT Open(  
   HWND hWnd = GetActiveWindow( ),  
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_WIZARDSHEET   
) throw( );  
HRESULT Open(   
   LPCWSTR szProgID,   
   DBPROPSET* pPropSet = NULL,   
   ULONG nPropertySets = 1   
) throw( );  
HRESULT Open(   
   LPCSTR szProgID,   
   LPCTSTR pName,   
   LPCTSTR pUserName = NULL,   
   LPCTSTR pPassword = NULL,   
   long nInitMode = 0   
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 `clsid`  
 [in] Die **CLSID** des Datenanbieters.  
  
 *DBPROPSET*  
 [in] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen, die Eigenschaften und Werten festgelegt werden. Finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB Programmer's Reference* im Windows SDK.  
  
 *nPropertySets*  
 [in] Die Anzahl der [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) Strukturen zu übergeben, der *DBPROPSET* Argument.  
  
 *pName*  
 [in] Der Name der Datenbank, zu der eine Verbindung hergestellt werden soll.  
  
 *pUserName*  
 [in] Der Name des Benutzers.  
  
 *pKennwort*  
 [in] Das Benutzerkennwort.  
  
 `nInitMode`  
 [in] Initialisierungsmodus der Datenbank. Finden Sie unter [Initialisierungseigenschaften](https://msdn.microsoft.com/en-us/library/ms723127.aspx)in der *OLE DB Programmer's Reference* in das Windows SDK für eine Liste gültiger initialisierungsmodi. Wenn `nInitMode` 0 ist, ist in dem zum Herstellen der Verbindung verwendeten Eigenschaftensatz kein Initialisierungsmodus enthalten.  
  
 `szProgID`  
 [in] Ein Programmbezeichner.  
  
 `enumerator`  
 [in] Ein [CEnumerator](../../data/oledb/cenumerator-class.md) Objekt zum Abrufen eines Monikers zum Öffnen der Verbindung, wenn der Aufrufer nicht angegeben wird, verwendet eine **CLSID**.  
  
 `hWnd`  
 [in] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll. Mit der Funktionsüberladung, die den `hWnd`-Parameter verwendet, werden Dienstkomponenten automatisch aufgerufen; Informationen dazu finden Sie unter „Hinweise“.  
  
 `dwPromptOptions`  
 [in] Bestimmt den Stil des anzuzeigenden Locatordialogfelds. Mögliche Werte sind in Msdasc.h aufgeführt.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt.  
  
## <a name="remarks"></a>Hinweise  
 Die Methodenüberladung, die den `hWnd`-Parameter verwendet, öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfeatures wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw. Weitere Informationen finden Sie unter "OLE DB-Dienste" in der OLE DB Programmer's Reference am [http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Die Methodenüberladungen, die den `hWnd`-Parameter nicht verwenden, öffnen ein Datenquellenobjekt ohne die Dienstkomponenten in oledb32.dll. Ein [CDataSource](../../data/oledb/cdatasource-class.md) mit diesen funktionsüberladungen geöffnet wird in der Lage, die Funktionalität von Dienstkomponenten zu nutzen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie eine Jet 4.0-Datenquelle mit OLE DB-Vorlagen geöffnet werden kann. Die Jet-Datenquelle wird OLE DB-Datenquelle behandelt. Allerdings den Aufruf von **öffnen** zwei Eigenschaftensätze: eine für **DBPROPSET_DBINIT** und die andere für **DBPROPSET_JETOLEDB_DBINIT**, sodass Sie festlegen können  **DBPROP_JETOLEDB_DATABASEPASSWORD**.  
  
 [!code-cpp[NVC_OLEDB_Consumer#7](../../data/oledb/codesnippet/cpp/cdatasource-open_1.cpp)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDataSource-Klasse](../../data/oledb/cdatasource-class.md)