---
title: "ComPtr::ComPtr-Konstruktor"
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
  - "client/Microsoft::WRL::ComPtr::ComPtr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ComPtr, Konstruktor"
ms.assetid: eaf70907-beac-458f-a503-2e5e27b0c196
caps.latest.revision: 4
caps.handback.revision: "4"
ms.author: "mblome"
manager: "ghogen"
---
# ComPtr::ComPtr-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der ComPtr\-Klasse.  Überladungen bereitstellen Standard, kopieren, werden verschoben und Konvertierungskonstruktoren.  
  
## Syntax  
  
```  
WRL_NOTHROW ComPtr();  
WRL_NOTHROW ComPtr(  
   decltype(__nullptr)  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _In_opt_ U *other  
);  
WRL_NOTHROW ComPtr(  
   const ComPtr& other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   const ComPtr<U> &other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr &&other  
);  
template<  
   class U  
>  
WRL_NOTHROW ComPtr(  
   _Inout_ ComPtr<U>&& other,  
   typename ENABLE_IF<__is_convertible_to(U*,  
   T*),  
   void *>;  
```  
  
#### Parameter  
 `U`  
 Der Typ des `other`\-Parameters.  
  
 `other`  
 Ein Objekt vom Typ `U`.  
  
## Rückgabewert  
  
## Hinweise  
 Der erste Konstruktor ist der Standardkonstruktor, der implictly ein leeres Objekt erstellt.  Der zweite Konstruktor gibt [\_\_nullptr\-Schlüsselwort](../windows/nullptr-cpp-component-extensions.md), der explizit ein leeres Objekt erstellt.  
  
 Der dritte Konstruktor erstellt ein Objekt aus dem Objekt, das von einem Zeiger angegeben wird.  
  
 Die vierten und fünften Konstruktoren sind Kopierkonstruktoren.  Im fünften Konstruktor kopiert ein Objekt, wenn es an den aktuellen Typ konvertierbar ist.  
  
 Die 6. und 7. Konstruktoren sind Verschiebungskonstruktoren.  Der 7. Konstruktor verschiebt ein Objekt, wenn es an den aktuellen Typ konvertierbar ist.  
  
## Anforderungen  
 **Header:**  client.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [ComPtr\-Klasse](../windows/comptr-class.md)