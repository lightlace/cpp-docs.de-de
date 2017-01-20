---
title: "ComPtr::ReleaseAndGetAddressOf-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::ComPtr::ReleaseAndGetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseAndGetAddressOf-Methode"
ms.assetid: 3751dcb4-d50e-432c-89e4-e736be34d434
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ReleaseAndGetAddressOf-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Schnittstelle frei, die diesem ComPtr zugeordnet wird und dann die Adresse des [ptr\_](../windows/comptr-ptr-data-member.md) Datenmembers ab, der einen Zeiger zur Schnittstelle enthält, die freigegeben wurde.  
  
## Syntax  
  
```  
T** ReleaseAndGetAddressOf();  
```  
  
## Rückgabewert  
 Die Adresse des [ptr\_](../windows/comptr-ptr-data-member.md) Datenmembers von diesem ComPtr.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)   
 [ComPtr::ptr\_\-Datenmember](../windows/comptr-ptr-data-member.md)