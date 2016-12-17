---
title: "CDataConnection::operator CSession&amp;"
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
  - "CSession&"
  - "CDataConnection::operatorCSession&"
  - "CDataConnection.operatorCSession&"
  - "operatorCSession&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSession&-Operator"
  - "Operator-CSession&"
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CSession&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Verweis auf das enthaltende `CSession`\-Objekt zurück.  
  
## Syntax  
  
```  
  
operator const CSession&();  
  
```  
  
## Hinweise  
 Dieser Operator gibt einen Verweis auf das enthaltende `CSession`\-Objekt zurück und ermöglicht es Ihnen, ein `CDataConnection`\-Objekt zu übergeben, in dem ein `CSession` Verweis erwartet wird.  
  
## Beispiel  
 Wenn Sie eine Funktion haben \(wie `func` \) unten dass `CSession` einen Verweis erfordert, können Sie **CSession &** verwenden, um ein `CDataConnection`\-Objekt stattdessen zu übergeben.  
  
 [!CODE [NVC_OLEDB_Consumer#5](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#5)]  
  
 [!CODE [NVC_OLEDB_Consumer#6](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#6)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession\*](../../data/oledb/cdataconnection-operator-csession-star.md)