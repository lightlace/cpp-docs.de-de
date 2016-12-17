---
title: "codecvt_utf16"
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
  - "codecvt/std::codecvt_utf16"
  - "std::codecvt_utf16"
  - "std.codecvt_utf16"
  - "codecvt_utf16"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_utf16-Klasse"
ms.assetid: a9897f98-f84d-4db6-90ad-858b2727570c
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "corob"
manager: "ghogen"
---
# codecvt_utf16
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Stellt eine [Gebietsschema](../standard-library/locale-class.md) Facette, die zwischen Breitzeichen als UCS\-2 oder UCS\-4 codiert und einem Bytestream codiert als UTF\-16LE oder UTF\-16BE konvertiert.  
  
## Syntax  
  
```  
template<  
    class Elem,  
    unsigned long Maxcode = 0x10ffff,  
    codecvt_mode Mode = (codecvt_mode)0  
>  
class codecvt_utf16 : public std::codecvt<Elem, char, StateType>  
```  
  
#### Parameter  
  
|Parameter|Beschreibung|  
|---------------|------------------|  
|`Elem`|Der Breitzeichen\-Elementtyp.|  
|`Maxcode`|Die maximale Anzahl von Zeichen für das gebietsschemafacet.|  
|`Mode`|Konfigurationsinformationen für das gebietsschemafacet.|  
  
## Hinweise  
 Diese Vorlagenklasse zwischen Breitzeichen als UCS\-2 oder UCS\-4 codiert und einem Bytestream codiert als UTF\-16LE konvertiert, wenn `Mode & little_endian`, oder andernfalls UTF\-16BE.  
  
 Bytestream sollte in eine binäre Datei geschrieben werden. Sie können beschädigt werden, wenn in eine Textdatei geschrieben.  
  
## Anforderungen  
 **Header:** \< Codecvt \>  
  
 **Namespace:** std