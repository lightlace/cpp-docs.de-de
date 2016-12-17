---
title: "CDataSource::Open"
ms.custom: na
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::Open"
  - "ATL.CDataSource.Open"
  - "CDataSource::Open"
  - "CDataSource.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open-Methode"
ms.assetid: a6d28bd1-799a-48ed-8993-5f82d1705b77
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CDataSource::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt eine Verbindung mit einer Datenquelle mit einem **CLSID**\-, **ProgID**\- oder `CEnumerator`\-Moniker her oder zeigt dem Benutzer ein Locatordialogfeld.  
  
## Syntax  
  
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
  
#### Parameter  
 `clsid`  
 \[in\] Die **CLSID** des Datenanbieters.  
  
 *pPropSet*  
 \[in\] Ein Zeiger auf ein Array von [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen mit festzulegenden Eigenschaften und Werten.  Weitere Informationen finden Sie unter [Eigenschaftensätze und Eigenschaftengruppen](https://msdn.microsoft.com/en-us/library/ms713696.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 *nPropertySets*  
 \[in\] Die Anzahl der im *pPropSet*\-Argument übergebenen [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx)\-Strukturen.  
  
 *pName*  
 \[in\] Der Name der Datenbank, zu der eine Verbindung hergestellt werden soll.  
  
 *pUserName*  
 \[in\] Der Name des Benutzers.  
  
 *pPassword*  
 \[in\] Das Benutzerkennwort.  
  
 `nInitMode`  
 \[in\] Initialisierungsmodus der Datenbank.  Eine Liste gültiger Initialisierungsmodi finden Sie unter [Initialisierungseigenschaften](https://msdn.microsoft.com/en-us/library/ms723127.aspx) in der *OLE DB\-Programmierreferenz* im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  Wenn `nInitMode` 0 ist, ist in dem zum Herstellen der Verbindung verwendeten Eigenschaftensatz kein Initialisierungsmodus enthalten.  
  
 `szProgID`  
 \[in\] Ein Programmbezeichner.  
  
 `enumerator`  
 \[in\] Ein [CEnumerator](../../data/oledb/cenumerator-class.md)\-Objekt, das zum Abrufen eines Monikers für die Verbindungsherstellung verwendet wird, wenn der Aufrufer keine **CLSID** angibt.  
  
 `hWnd`  
 \[in\] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll.  Mit der Funktionsüberladung, die den `hWnd`\-Parameter verwendet, werden Dienstkomponenten automatisch aufgerufen; Informationen dazu finden Sie unter „Hinweise“.  
  
 `dwPromptOptions`  
 \[in\] Bestimmt den Stil des anzuzeigenden Locatordialogfelds.  Mögliche Werte sind in Msdasc.h aufgeführt.  
  
## Rückgabewert  
 Ein Standard `HRESULT`\-Objekt.  
  
## Hinweise  
 Die Methodenüberladung, die den `hWnd`\-Parameter verwendet, öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfeatures wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  Weitere Informationen finden Sie unter „OLE DB\-Dienste“ in der OLE DB\-Programmierreferenz unter [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
 Die Methodenüberladungen, die den `hWnd`\-Parameter nicht verwenden, öffnen ein Datenquellenobjekt ohne die Dienstkomponenten in oledb32.dll.  Ein mit diesen Funktionsüberladungen geöffnetes [CDataSource](../../data/oledb/cdatasource-class.md)\-Objekt ist nicht in der Lage, die Funktionalität von Dienstkomponenten zu nutzen.  
  
## Beispiel  
 Der folgende Code zeigt, wie eine Jet 4.0\-Datenquelle mit OLE DB\-Vorlagen geöffnet werden kann.  Die Jet\-Datenquelle wird OLE DB\-Datenquelle behandelt.  Allerdings sind für den Aufruf von **Öffnen** zwei Eigenschaftensätze erforderlich: einer für **DBPROPSET\_DBINIT** und einer für **DBPROPSET\_JETOLEDB\_DBINIT**, sodass Sie **DBPROP\_JETOLEDB\_DATABASEPASSWORD** festlegen können.  
  
 [!CODE [NVC_OLEDB_Consumer#7](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#7)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)