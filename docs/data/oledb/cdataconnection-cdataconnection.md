---
title: "CDataConnection::CDataConnection | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
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
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
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