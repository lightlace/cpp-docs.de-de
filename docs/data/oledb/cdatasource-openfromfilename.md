---
title: "CDataSource::OpenFromFileName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataSource::OpenFromFileName"
  - "ATL::CDataSource::OpenFromFileName"
  - "OpenFromFileName"
  - "CDataSource.OpenFromFileName"
  - "ATL.CDataSource.OpenFromFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenFromFileName-Methode"
ms.assetid: c4226de6-59da-4368-9c15-c5afab86f68b
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# CDataSource::OpenFromFileName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine Datenquelle aus einer Datei, die durch den vom Benutzer bereitgestellten Dateinamen angegeben wird.  
  
## Syntax  
  
```  
  
        HRESULT OpenFromFileName(   
   LPCOLESTR szFileName    
) throw( );  
```  
  
#### Parameter  
 `szFileName`  
 \[in\] Der Name einer Datei, in der Regel eine Datenquellenverbindungsdatei \(UDL\-Datei\).  
  
 Weitere Informationen zu Datenverknüpfungsdateien \(UDL\-Dateien\) finden Sie in der [Übersicht zur Data Link\-API](https://msdn.microsoft.com/en-us/library/ms718102.aspx) im [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Rückgabewert  
 Ein standardmäßiges `HRESULT`\-Element.  
  
## Hinweise  
 Diese Methode öffnet ein Datenquellenobjekt mit den Dienstkomponenten im oledb32.dll; Diese DLL enthält die Implementierung von Dienstkomponentenfeatures wie z. B. Ressourcenpooling, automatische Transaktionseintragung usw.  Weitere Informationen finden Sie unter „OLE DB\-Dienste“ in der OLE DB\-Programmierreferenz unter [http:\/\/msdn.microsoft.com\/library\/default.asp?url\=\/library\/oledb\/htm\/oledbole\_db\_services.asp?frame\=true](http://msdn.microsoft.com/library/default.asp?url=/library/oledb/htm/oledbole_db_services.asp?frame=true).  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataSource\-Klasse](../../data/oledb/cdatasource-class.md)