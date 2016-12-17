---
title: "HString::MakeReference-Methode"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference"
dev_langs: 
  - "C++"
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::MakeReference-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Erstellt ein HStringReference\-Objekt aus einem angegebenen Zeichenfolgenparameter.  
  
## Syntax  
  
```  
template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[ sizeDest]);  
  
    template<unsigned int sizeDest>  
    static HStringReference MakeReference(  
              wchar_t const (&str)[sizeDest],   
              unsigned int len);  
```  
  
#### Parameter  
 `sizeDest`  
 Ein Vorlagenparameter, der die Größe des HStringReference\-Puffers Ziel angibt.  
  
 `str`  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge des in diesem Vorgang verwenden `str`\-Parameterpuffers.  Wenn der Parameter `len` nicht angegeben wird, wird der gesamte `str`\-Parameter verwendet.  
  
## Rückgabewert  
 Ein HStringReference\-Objekt, dessen Wert dem `str` angegebene Parameter ist.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)