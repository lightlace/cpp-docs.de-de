---
title: "HString::HString-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::HString"
dev_langs: 
  - "C++"
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
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