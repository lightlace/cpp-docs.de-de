---
title: "CDataConnection::CDataConnection"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "CDataConnection.CDataConnection"
  - "ATL.CDataConnection.CDataConnection"
  - "CDataConnection::CDataConnection"
  - "ATL::CDataConnection::CDataConnection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataConnection-Klasse, Konstruktor"
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::CDataConnection
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instanziiert und initialisiert ein `CDataConnection`\-Objekt.  
  
## Syntax  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### Parameter  
 `ds`  
 \[in\] Einen Verweis auf eine Verbindung der vorhandenen Daten.  
  
## Hinweise  
 Die erste Überschreibung erstellt ein neues `CDataConnection`\-Objekt mit Standardeinstellungen.  
  
 Die zweiten Überschreiben erstellt ein neues `CDataConnection`\-Objekt mit den Einstellungen, die z Datenverbindungsobjekt entsprechen, das Sie angeben.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)