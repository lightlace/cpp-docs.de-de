---
title: "SafeCast"
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
  - "SafeCast"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SafeCast-Funktion"
ms.assetid: 55316729-8456-403a-9f96-59d4038f67af
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "ghogen"
manager: "ghogen"
---
# SafeCast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Typumwandlungen ein Typ Zahl einem anderen Typ.  
  
## Syntax  
  
```  
template<typename T, typename U>  
inline bool SafeCast (  
   const T From,  
   U& To  
);  
```  
  
#### Parameter  
 \[in\] `From`  
 Die Quellzahl zu konvertieren.  Dies muss vom Typ T sein.  
  
 \[out\] `To`  
 Ein Verweis zum neuen Zahlentyp.  Dies muss vom Typ U sein.  
  
## Rückgabewert  
 `true`, wenn kein Fehler auftritt; `false`, wenn ein Fehler auftritt.  
  
## Hinweise  
 Diese Methode ist ein Teil von [SafeInt\-Bibliothek](../windows/safeint-library.md) und für einen einzelnen Umwandlungsvorgang entworfen, ohne Instanz [SafeInt\-Klasse](../windows/safeint-class.md).  
  
> [!NOTE]
>  Diese Methode sollte nur verwendet werden, wenn ein einzelner Vorgang geschützt werden muss.  Wenn mehrere Operationen gibt, sollten Sie die `SafeInt`\-Klasse verwenden, anstatt, die einzelnen eigenständigen Funktionen aufzurufen.  
  
 Weitere Informationen zu von Vorlagentypen T und U, finden Sie unter [SafeInt\-Funktionen](../windows/safeint-functions.md).  
  
## Anforderungen  
 **Header:** safeint.h  
  
 **Namespace:** Microsoft::Utilities  
  
## Siehe auch  
 [SafeInt\-Funktionen](../windows/safeint-functions.md)   
 [SafeInt\-Bibliothek](../windows/safeint-library.md)   
 [SafeInt\-Klasse](../windows/safeint-class.md)