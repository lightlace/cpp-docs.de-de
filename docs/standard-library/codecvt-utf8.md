---
title: "codecvt_utf8"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "std.codecvt_utf8"
  - "std::codecvt_utf8"
  - "codecvt_utf8"
  - "codecvt/std::codecvt_utf8"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8-Klasse"
ms.assetid: 2a87478f-e2d4-4b8d-ad9c-00add01d1bb0
caps.latest.revision: 20
caps.handback.revision: "10"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt [Gebietsschema](../standard-library/locale-class.md) ein Aspekt, das zwischen dem Breitzeichen konvertiert, die als UCS\-2 codiert werden oder UCS\-4, und einen Bytestrom, der als UTF\-8 codiert ist dar.  
  
## Syntax  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8 : public std::codecvt<Elem, char, StateType>  
```  
  
#### Parameter  
  
|Parameter|**Beschreibung**|  
|---------------|----------------------|  
|`Elem`|Der Breitzeichenelementtyp.|  
|`Maxcode`|Die maximale Anzahl von Zeichen für das Gebietsschemafacet.|  
|`Mode`|Konfigurationsinformationen für das Gebietsschemafacet.|  
  
## Hinweise  
 Der Bytestrom kann einer Binärdatei oder in eine Textdatei geschrieben werden.  
  
## Anforderungen  
 **Header:** \<codecvt\>  
  
 **Namespace:** std