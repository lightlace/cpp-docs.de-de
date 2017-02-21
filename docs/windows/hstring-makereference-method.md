---
title: "HString::MakeReference-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::MakeReference"
dev_langs: 
  - "C++"
ms.assetid: 9e1fd2b2-66ad-4a50-b647-a20ab10e522f
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
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