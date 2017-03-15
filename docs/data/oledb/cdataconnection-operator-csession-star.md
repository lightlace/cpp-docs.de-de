---
title: "CDataConnection::operator CSession*"
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
  - "CDataConnection.operatorCSession*"
  - "CDataConnection::operatorCSession*"
  - "operatorCSession*"
  - "CSession*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession*-Operator"
  - "Operator-CSession*"
ms.assetid: 0b0feede-5c3e-4835-be5b-03651597014d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession*
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Zeiger an das übergeordnete `CSession`\-Objekt zurück.  
  
## Syntax  
  
```  
  
operator const CSession*() throw( );  
  
```  
  
## Hinweise  
 Dieser Operator gibt einen Zeiger an das übergeordnete `CSession`\-Objekt zurück und ermöglicht es Ihnen, ein `CDataConnection`\-Objekt zu übergeben, in dem ein `CSession` Zeiger erwartet wird.  
  
## Beispiel  
 Siehe [Operator CSession &](../../data/oledb/cdataconnection-operator-csession-amp.md) für ein Verwendungsbeispiel.  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession&](../../data/oledb/cdataconnection-operator-csession-amp.md)