---
title: "CDataConnection::Copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.Copy"
  - "ATL.CDataConnection.Copy"
  - "ATL::CDataConnection::Copy"
  - "CDataConnection::Copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Copy-Methode"
ms.assetid: a3dbd70d-36be-49e0-a527-00e3910a7a56
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataConnection::Copy
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt eine Kopie einer Verbindung der vorhandenen Daten.  
  
## Syntax  
  
```  
  
      CDataConnection& Copy(   
   const CDataConnection & ds    
) throw( );  
```  
  
#### Parameter  
 `ds`  
 \[in\] Einen Verweis auf eine Verbindung der vorhandenen Daten für die Kopie.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)