---
title: "ComPtr::operator&amp;-Operator"
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
  - "client/Microsoft::WRL::ComPtr::operator&"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator&-Operator"
ms.assetid: 2d77fda6-f4b2-45c1-8a0e-fbc355013531
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator&amp;-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt die Schnittstelle frei, die diesem `ComPtr`\-Objekt zugeordnet wird und dann die Adresse des Objekts `ComPtr` ab.  
  
## Syntax  
  
```cpp  
Details::ComPtrRef<WeakRef> operator&()  
  
const Details::ComPtrRef<const WeakRef> operator&() const  
```  
  
## Rückgabewert  
 Ein schwacher Verweis auf den aktuellen `ComPtr`.  
  
## Hinweise  
 Diese Methode weicht von [ComPtr::GetAddressOf](../windows/comptr-getaddressof-method.md), da diese Methode einen Verweis auf das von Schnittstellenzeigern freigibt.  Verwenden Sie `ComPtr::GetAddressOf`, wenn die Adresse des Schnittstellenzeigers benötigen, aber möchten diese Schnittstelle nicht freigeben.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)