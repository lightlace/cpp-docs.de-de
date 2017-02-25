---
title: "ComPtr::GetAddressOf-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAddressOf-Methode"
ms.assetid: 972a41d0-c2ef-4ae3-b2cd-77cc45156ac9
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::GetAddressOf-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft die Adresse des [ptr\_](../windows/comptr-ptr-data-member.md) Datenmembers ab, der einen Zeiger zur Schnittstelle enthält, die durch dieses ComPtr dargestellt wird.  
  
## Syntax  
  
```  
T* const* GetAddressOf() const;  
T** GetAddressOf();  
```  
  
## Rückgabewert  
 Die Adresse einer Variablen.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)