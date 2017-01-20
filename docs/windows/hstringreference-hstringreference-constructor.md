---
title: "HStringReference::HStringReference-Konstruktor"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 29f5fe11-3928-4f60-9861-f0894247bfcb
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HStringReference::HStringReference-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der HStringReference\-Klasse.  
  
## Syntax  
  
```cpp  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest]) throw();  
  
    template<unsigned int sizeDest>  
    HStringReference(wchar_t const (&str)[ sizeDest],   
unsigned int len)  
       throw();  
  
    HStringReference(HStringReference&& other) throw();  
  
```  
  
#### Parameter  
 `sizeDest`  
 Ein Vorlagenparameter, der die Größe des HStringReference\-Puffers Ziel angibt.  
  
 `str`  
 Ein Verweis auf eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge des in diesem Vorgang verwenden `str`\-Parameterpuffers.  Wenn der Parameter `len` nicht angegeben wird, wird der gesamte `str`\-Parameter verwendet.  Wenn `len` größer als `sizeDest` ist, wird `len``sizeDest` auf \-1 festgelegt.  
  
 `other`  
 Ein weiteres HStringReference\-Objekt.  
  
## Hinweise  
 Der erste Konstruktor initialisiert ein neues dieses HStringReference\-Objekt die gleiche Größe wie Parameter `str`.  
  
 Der zweite Konstruktor initialisiert ein neues dieses HStringReference\-Objekt dessen Größe specifeid durch Parameter `len`.  
  
 Der dritte Konstruktor initialisiert ein neues HStringReference\-Objekt den Wert des Parameters `other` zerstört und dann den `other`\-Parameter.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HStringReference\-Klasse](../windows/hstringreference-class.md)