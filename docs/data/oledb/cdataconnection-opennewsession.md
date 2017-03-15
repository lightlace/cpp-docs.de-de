---
title: "CDataConnection::OpenNewSession | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.OpenNewSession"
  - "ATL.CDataConnection.OpenNewSession"
  - "ATL::CDataConnection::OpenNewSession"
  - "OpenNewSession"
  - "CDataConnection::OpenNewSession"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OpenNewSession-Methode"
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::OpenNewSession
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Öffnet eine neue Sitzung, die die aktuelle Datenquelle des Verbindungsobjekts verwendet.  
  
## Syntax  
  
```  
  
      HRESULT OpenNewSession(   
   CSession & session    
) throw( );  
```  
  
#### Parameter  
 `session`  
 \[in\/out\] Einen Verweis auf den neuen Sitzungsobjekt.  
  
 **Hinweise**  
 Die neue Sitzung verwendet das aktuelle enthaltende Datenquellenobjekt des Verbindungsobjekts als übergeordnete und kann auf dieselben Informationen wie die Datenquelle zugreifen.  
  
## Rückgabewert  
 Standard\- `HRESULT`.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)