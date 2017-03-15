---
title: "ComPtr::operator=-Operator"
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
  - "client/Microsoft::WRL::ComPtr::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Operator=-Operator"
ms.assetid: 1a0c2752-f7d8-4819-9443-07b88b69ef02
caps.latest.revision: 3
caps.handback.revision: "3"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::operator=-Operator
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Weist dem aktuellen ComPtr einen Wert zu.  
  
## Syntax  
  
```  
WRL_NOTHROW ComPtr& operator=(  
   decltype(__nullptr)  
);  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ T *other  
);  
template <  
   typename U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr &other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   const ComPtr<U>& other  
);  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr& operator=(  
   _Inout_ ComPtr<U>&& other  
);  
```  
  
#### Parameter  
 `U`  
 Eine Klasse.  
  
 `other`  
 Ein Zeiger, ein Verweis oder ein rvalu\-Verweis zu einem Typ oder einem anderen ComPtr.  
  
## Rückgabewert  
 Ein Verweis auf den aktuellen ComPtr.  
  
## Hinweise  
 Die erste Version dieses Operators Aufgaben im aktuellen ComPtr einen leeren Wert zu.  
  
 In der zweiten Version wenn der zuweisende Schnittstellenzeiger nicht der gleiche wie der aktuelle ComPtr\-Schnittstellenzeiger ist, dem aktuellen ComPtr wird der zweite Schnittstellenzeiger zugewiesen.  
  
 In der dritten Version dem aktuellen ComPtr wird der zuweisende Schnittstellenzeiger zugewiesen.  
  
 In der vierten Version wenn von Schnittstellenzeigern des zuweisenden Werts nicht dem aktuellen ComPtr\-Schnittstellenzeiger ist, dem aktuellen ComPtr wird der zweite Schnittstellenzeiger zugewiesen.  
  
 Die fünfte Version ist ein Kopienoperator; dem aktuellen ComPtr ein Verweis auf ein ComPtr wird zugewiesen.  
  
 Die 6. Version ist ein Kopienoperator, von Verschiebesemantik verwendet; ein rvalu\-Verweis zu einem Typ ComPtr wenn eine der statischen Umwandlung und dann zugewiesen dem aktuellen ComPtr.  
  
 Die 7. Version ist ein Kopienoperator, von Verschiebesemantik verwendet; ein rvalu\-Verweis zu einem ComPtr vom Typ `U` wird statische Umwandlung dann zugewiesen und dem aktuellen ComPtr.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)