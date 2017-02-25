---
title: "DontUseNewUseMake-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DontUseNewUseMake-Klasse"
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# DontUseNewUseMake-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
class DontUseNewUseMake;  
```  
  
## Hinweise  
 Verhindert Anwendung des Operators `new` in RuntimeClass.  Folglich müssen Sie stattdessen die [Machen Sie die Funktion](../windows/make-function.md) verwenden.  
  
## Member  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[DontUseNewUseMake::operator new\-Operator](../windows/dontusenewusemake-operator-new-operator.md)|Überlädt Operator `new` und durch ihn in RuntimeClass verwendet werden.|  
  
## Vererbungshierarchie  
 `DontUseNewUseMake`  
  
## Anforderungen  
 **Header:** implements.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make\-Funktion](../windows/make-function.md)