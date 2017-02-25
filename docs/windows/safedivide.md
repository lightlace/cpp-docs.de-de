---
title: "SafeDivide | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "SafeDivide"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeDivide-Funktion"
ms.assetid: b5b27484-ad6e-46b1-ba9f-1c7120dd103b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# SafeDivide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dividiert zwei Zahlen auf eine Weise, die gegen Division durch null schützt.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeDivide (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Parameter  
 \[in\] `t`  
 Der Divisor.  Dies muss vom Typ T sein.  
  
 \[in\] `u`  
 Der Dividend.  Dies muss vom Typ U sein.  
  
 \[out\] `result`  
 Der Parameter, wobei `SafeDivide` das Ergebnis gespeichert wird.  
  
## Rückgabewert  
 `true`, wenn kein Fehler auftritt; `false`, wenn ein Fehler auftritt.  
  
## Hinweise  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und ist für eine einzelne Division entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
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
 [SafeModulus](../windows/safemodulus.md)   
 [SafeMultiply](../windows/safemultiply.md)