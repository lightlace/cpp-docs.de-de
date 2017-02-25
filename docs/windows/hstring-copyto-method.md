---
title: "HString::CopyTo-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: a1fd2ef0-e175-4c18-927b-550e02a89e43
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# HString::CopyTo-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Kopiert das aktuelle HString\-Objekt zu einem HSTRING\-Objekt.  
  
## Syntax  
  
```  
  
HRESULT CopyTo(  
   _Out_ HSTRING *str  
   ) const throw();  
```  
  
#### Parameter  
 `str`  
 Das HSTRING, das die Kopie erhält.  
  
## Hinweise  
 Diese Methode ruft die [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx)\-Funktion auf.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)