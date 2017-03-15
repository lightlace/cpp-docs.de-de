---
title: "SafeMultiply | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeMultiply"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeMultiply-Funktion"
ms.assetid: 81d988a5-fac7-4930-8c37-c24fa8e2c853
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeMultiply
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Multipliziert zwei Zahlen zusammen auf eine Weise, die anhand Überlauf schützt.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeMultiply (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Parameter  
 \[in\] `t`  
 Die erste zu multiplizierende Zahl.  Dies muss vom Typ T sein.  
  
 \[in\] `u`  
 Die zweite zu multiplizierende Zahl.  Dies muss vom Typ U sein.  
  
 \[out\] `result`  
 Der Parameter, wobei `SafeMultiply` das Ergebnis gespeichert wird.  
  
## Rückgabewert  
 `true`, wenn kein Fehler auftritt; `false`, wenn ein Fehler auftritt.  
  
## Hinweise  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und für einen einzelnen Multiplikationsvorgang entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
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
 [SafeDivide](../windows/safedivide.md)