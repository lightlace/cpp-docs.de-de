---
title: "CDataConnection::operator CDataSource*"
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
  - "CDataSource*"
  - "CDataConnection::operatorCDataSource*"
  - "CDataConnection.operatorCDataSource*"
  - "operatorCDataSource*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource*-Operator"
  - "Operator * (CDataSource)"
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CDataSource*
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Zeiger an das übergeordnete `CDataSource`\-Objekt zurück.  
  
## Syntax  
  
```  
  
operator const CDataSource*() throw( );  
  
```  
  
## Hinweise  
 Dieser Operator gibt einen Zeiger an das übergeordnete `CDataSource`\-Objekt zurück und ermöglicht es Ihnen, ein `CDataConnection`\-Objekt zu übergeben, in dem ein `CDataSource` Zeiger erwartet wird.  
  
 Siehe [Operator CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) für ein Verwendungsbeispiel.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)