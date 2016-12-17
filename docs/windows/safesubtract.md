---
title: "SafeSubtract"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "SafeSubtract"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeSubtract-Funktion"
ms.assetid: c2712ddc-173f-46a1-b09c-e7ebbd9e68b2
caps.latest.revision: 5
caps.handback.revision: "5"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeSubtract
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Subtrahiert zwei Zahlen auf eine Weise, die anhand Überlauf schützt.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeSubtract (  
   T t,  
   U u,  
   T& result  
) throw ();  
```  
  
#### Parameter  
 \[in\] `t`  
 Die erste Zahl in der Subtraktion.  Dies muss vom Typ T sein.  
  
 \[in\] `u`  
 Die von `t` zu subtrahierende Zahl.  Dies muss vom Typ U sein.  
  
 \[out\] `result`  
 Der Parameter, wobei `SafeSubtract` das Ergebnis gespeichert wird.  
  
## Rückgabewert  
 `true`, wenn kein Fehler auftritt; `false`, wenn ein Fehler auftritt.  
  
## Hinweise  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und ist für eine einzelne Subtraktion entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
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
 [SafeAdd](../windows/safeadd.md)