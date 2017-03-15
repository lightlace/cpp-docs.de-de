---
title: "SafeGreaterThanEquals | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeGreaterThanEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeGreaterThanEquals-Funktion"
ms.assetid: 43312fa9-d925-4f9f-a352-a190c02b3005
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeGreaterThanEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vergleicht zwei Zahlen.  
  
## Syntax  
  
```  
template <typename T, typename U>  
inline bool SafeGreaterThanEquals (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Parameter  
 \[in\] `t`  
 Die erste zu vergleichende Zahl.  Dies muss vom Typ T sein.  
  
 \[in\] `u`  
 Die zweite zu vergleichende Zahl.  Dies muss vom Typ U sein.  
  
## Rückgabewert  
 `true`, wenn `t` größer oder gleich `u` ist; andernfalls `false`.  
  
## Hinweise  
 `SafeGreaterThanEquals` erhöht den Standardvergleichsoperator, da es Ihnen ermöglicht, zwei verschiedene Typen Zahlen zu vergleichen.  
  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und für einen einzelnen Vergleichsoperation entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn ein einzelner mathematischer Vorgang geschützt werden muss.  Wenn mehrere Operationen gibt, sollten Sie die `SafeInt`\-Klasse verwenden, anstatt, die einzelnen eigenständigen Funktionen aufzurufen.  
  
 Weitere Informationen zu von Vorlagentypen T und U, finden Sie unter [SafeInt\-Funktionen](../windows/safeint-functions.md).  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## Siehe auch  
 [SafeInt\-Funktionen](../windows/safeint-functions.md)   
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeInt\-Klasse](../windows/safeint-class.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeLessThan](../windows/safelessthan.md)