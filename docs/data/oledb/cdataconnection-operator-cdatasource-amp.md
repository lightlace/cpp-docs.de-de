---
title: "CDataConnection::operator CDataSource&amp;"
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
  - "CDataSource&"
  - "CDataConnection.operatorCDataSource&"
  - "operatorCDataSource&"
  - "CDataConnection::operatorCDataSource&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataSource&-Operator"
  - "Operator & (CDataSource)"
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CDataConnection::operator CDataSource&amp;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Gibt einen Verweis auf das enthaltende `CDataSource`\-Objekt zurück.  
  
## Syntax  
  
```  
  
operator const CDataSource&() throw( );  
  
```  
  
## Hinweise  
 Dieser Operator gibt einen Verweis auf das enthaltende `CDataSource`\-Objekt zurück und ermöglicht es Ihnen, ein `CDataConnection`\-Objekt zu übergeben, in dem ein `CDataSource` Verweis erwartet wird.  
  
## Beispiel  
 Wenn Sie eine Funktion haben \(wie `func` \) unten dass `CDataSource` einen Verweis erfordert, können Sie **CDataSource &** verwenden, um ein `CDataConnection`\-Objekt stattdessen zu übergeben.  
  
 [!CODE [NVC_OLEDB_Consumer#3](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#3)]  
  
 [!CODE [NVC_OLEDB_Consumer#4](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#4)]  
  
## Anforderungen  
 **Header:** atldbcli.h  
  
## Siehe auch  
 [CDataConnection\-Klasse](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource\*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)