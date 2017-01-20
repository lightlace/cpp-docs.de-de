---
title: "HString::GetAddressOf-Methode"
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
  - "corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf"
dev_langs: 
  - "C++"
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: 2
caps.handback.revision: "2"
ms.author: "mblome"
manager: "ghogen"
---
# HString::GetAddressOf-Methode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ruft einen Zeiger auf das zugrunde liegende HSTRING\-Handle ab.  
  
## Syntax  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## Rückgabewert  
 Ein Zeiger auf das zugrunde liegenden HSTRING\-Handle.  
  
## Hinweise  
 Nach diesem Vorgang wird der Zeichenfolgenwert des zugrunde liegenden HSTRING\-Handles zerstört.  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [HString\-Klasse](../windows/hstring-class.md)