---
title: "CloakedIid-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::CloakedIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CloakedIid-Struktur"
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CloakedIid-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt zu Vorlagen RuntimeClass, der implementiert und ChainInterfaces an, die die angegebene Schnittstelle nicht in der IID\-Liste zugänglich ist.  
  
## Syntax  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### Parameter  
 `T`  
 Die Schnittstelle, die ausgeblendet wird \(verdeckt\).  
  
## Hinweise  
 Nachfolgend ist ein Beispiel dafür, wie CloakedIid verwendet wird: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## Vererbungshierarchie  
 `T`  
  
 `CloakedIid`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Microsoft::WRL\-Namespace](../windows/microsoft-wrl-namespace.md)