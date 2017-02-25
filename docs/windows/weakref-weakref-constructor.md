---
title: "WeakRef::WeakRef-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "client/Microsoft::WRL::WeakRef::WeakRef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WeakRef, Konstruktor"
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# WeakRef::WeakRef-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der WeakRef\-Klasse.  
  
## Syntax  
  
```  
WeakRef();  
WeakRef(  
   decltype(__nullptr)  
);  
  
WeakRef(  
   _In_opt_ IWeakReference* ptr  
);  
  
WeakRef(  
   const ComPtr<IWeakReference>& ptr  
);  
  
WeakRef(  
   const WeakRef& ptr  
);  
  
WeakRef(  
   _Inout_ WeakRef&& ptr  
);  
```  
  
#### Parameter  
 `ptr`  
 Ein Zeiger, ein Verweis oder ein rvalu\-Verweis an ein vorhandenes Objekt, die das aktuelle WeakRef\-Objekt initialisiert.  
  
## Hinweise  
 Der erste Konstruktor initialisiert ein leeres WeakRef\-Objekt.  Der zweite Konstruktor initialisiert ein WeakRef\-Objekt von einem Zeiger auf die IWeakReference\-Schnittstelle.  Der dritte Konstruktor initialisiert ein WeakRef\-Objekt von einen Verweis auf ein Objekt ComPtr \< IWeakReference\>.  Die vierten und fünften Konstruktoren initialisiert ein WeakRef\-Objekt von einem anderen WeakRef\-Objekt.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [WeakRef\-Klasse](../windows/weakref-class.md)