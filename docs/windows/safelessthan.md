---
title: "SafeLessThan | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeLessThan"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeLessThan-Funktion"
ms.assetid: 9d85bc0d-8d94-4d59-9b72-ef3c63a120a0
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeLessThan
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob eine Zahl kleiner als andere.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeLessThan (  
   const T t,  
   const U u  
) throw ();  
```  
  
#### Parameter  
 \[in\] `t`  
 Der erste Wert.  Dies muss vom Typ T sein.  
  
 \[in\] `u`  
 Das zweite numer.  Dies muss vom Typ U sein.  
  
## Rückgabewert  
 `true`, wenn `t` kleiner als `u` ist; andernfalls `false`.  
  
## Hinweise  
 Diese Methode erhöht den Standardvergleichsoperator, da `SafeLessThan` Sie ermöglicht, zwei verschiedene Typen Zahl zu vergleichen.  
  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und für einen einzelnen Vergleichsoperation entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn ein einzelner mathematischer Vorgang geschützt werden muss.  Wenn mehrere Operationen gibt, sollten Sie die Klasse `SafeInt`, anstatt die einzelnen eigenständigen Funktionen Aufruf verwenden.  
  
 Weitere Informationen zu von Vorlagentypen T und U, finden Sie unter [SafeInt\-Funktionen](../windows/safeint-functions.md).  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## Siehe auch  
 [SafeInt\-Funktionen](../windows/safeint-functions.md)   
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeInt\-Klasse](../windows/safeint-class.md)   
 [SafeLessThanEquals](../windows/safelessthanequals.md)   
 [SafeGreaterThan](../windows/safegreaterthan.md)   
 [SafeGreaterThanEquals](../windows/safegreaterthanequals.md)