---
title: "CDataSource::OpenWithPromptFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource.OpenWithPromptFileName"
  - "OpenWithPromptFileName"
  - "ATL::CDataSource::OpenWithPromptFileName"
  - "ATL.CDataSource.OpenWithPromptFileName"
  - "CDataSource::OpenWithPromptFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenWithPromptFileName-Methode"
ms.assetid: 89460504-1aaf-4412-aa7b-fa5a4b39ada3
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CDataSource::OpenWithPromptFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Methode wird dem Benutzer ein Dialogfeld angezeigt und anschließend eine Datenquelle mithilfe der vom Benutzer angegebenen Datei geöffnet.  
  
## Syntax  
  
```  
  
        HRESULT OpenWithPromptFileName(   
   HWND hWnd = GetActiveWindow(   
   ),   
   DBPROMPTOPTIONS dwPromptOptions = DBPROMPTOPTIONS_NONE,   
   LPCOLESTR szInitialDirectory = NULL    
) throw( );  
```  
  
#### Parameter  
 `hWnd`  
 \[in\] Handle für das Fenster, das als das übergeordnete Element des Dialogfelds festgelegt werden soll.  
  
 `dwPromptOptions`  
 \[in\] Bestimmt den Stil des anzuzeigenden Locatordialogfelds.  Mögliche Werte sind in Msdasc.h aufgeführt.  
  
 *szInitialDirectory*  
 \[in\] Das im Locatordialogfeld anzuzeigende Ausgangsverzeichnis.  
  
## Rückgabewert  
 Ein Standard `HRESULT`\-Objekt.  
  
## Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfeatures wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  Weitere Informationen finden Sie unter „OLE DB\-Dienste“ in der OLE DB\-Programmierreferenz unter [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)