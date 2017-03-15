---
title: "ComPtr::Detach-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::Detach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Detach-Methode"
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# ComPtr::Detach-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Hebt dieses `ComPtr`\-Objekts von der Schnittstelle die Zuordnung die sie darstellt.  
  
## Syntax  
  
```  
T* Detach();  
```  
  
## Rückgabewert  
 Ein Zeiger auf die Schnittstelle, die von diesem `ComPtr`\-Objekt dargestellt wird.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)