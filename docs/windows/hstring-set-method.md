---
title: "HString::Set-Methode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HString::Set"
dev_langs: 
  - "C++"
ms.assetid: c9b3d613-95c4-48b0-999d-f5baf0804faf
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# HString::Set-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Legt den Wert des aktuellen HString\-Objekts auf die angegebene Zeichenfolge mit Breitzeichen oder den angegebenen HString\-Parameter fest.  
  
## Syntax  
  
```  
  
HRESULT Set(  
          const wchar_t* str) throw();  
HRESULT Set(   
          const wchar_t* str,   
          unsigned int len  
           ) throw();  
HRESULT Set(  
          const HSTRING& hstr  
           ) throw();  
```  
  
#### Parameter  
 `str`  
 Eine Zeichenfolge mit Breitzeichen.  
  
 `len`  
 Die maximale Länge des Parameters `str`, der dem aktuellen HString\-Objekt zugewiesen wird.  
  
 `hstr`  
 Ein vorhandenes HString\-Objekt.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)