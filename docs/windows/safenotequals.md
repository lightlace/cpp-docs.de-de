---
title: "SafeNotEquals | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeNotEquals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeNotEquals-Funktion"
ms.assetid: 032e45a8-4159-4b55-b7cc-ecd27f4e4788
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# SafeNotEquals
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bestimmt, ob zwei Zahlen nicht gleich sind.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeNotEquals (  
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
 `true`, wenn `t` und `u` ungleich sind, andernfalls `false`.  
  
## Hinweise  
 Die Methode erhöht `!=`, da `SafeNotEquals` Sie ermöglicht, zwei verschiedene Typen Zahlen zu vergleichen.  
  
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
 [SafeEquals](../windows/safeequals.md)