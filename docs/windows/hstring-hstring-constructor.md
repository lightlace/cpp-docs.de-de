---
title: "HString::HString-Konstruktor"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::HString"
dev_langs: 
  - "C++"
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::HString-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der HString\-Klasse.  
  
## Syntax  
  
```cpp  
  
HString(HSTRING hstr = nullptr) throw();  
HString(HString&& other) throw();  
```  
  
#### Parameter  
 `hstr`  
 Ein HSTRING\-Handle.  
  
 `other`  
 Ein vorhandenes HString\-Objekt.  
  
## Hinweise  
 Der erste Konstruktor initialisiert ein neues HString\-Objekt, das leer ist.  
  
 Der zweite Konstruktor initialisiert ein neues HString\-Objekt zum Wert des vorhandenen `other`\-Parameters und zerstört dann den `other`\-Parameter.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)