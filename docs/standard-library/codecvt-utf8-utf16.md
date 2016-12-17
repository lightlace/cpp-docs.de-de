---
title: "codecvt_utf8_utf16"
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
  - "codecvt_utf8_utf16"
  - "codecvt/std::cvt_utf8_utf16"
  - "std::codecvt_utf8_utf16"
  - "std.codecvt_utf8_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf8_utf16-Klasse"
ms.assetid: 4c12c881-5dba-4e39-b338-0b9caff5af29
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf8_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt ein Aspekt [Gebietsschema](../standard-library/locale-class.md) dar, das zwischen den Breitzeichen konvertiert, die als UTF\-16 codiert und einem Bytestrom, der als UTF\-8 codiert ist.  
  
## Syntax  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf8_utf16 : public _STD codecvt<Elem, char, StateType>  
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