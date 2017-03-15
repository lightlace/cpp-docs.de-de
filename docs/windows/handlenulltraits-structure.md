---
title: "HANDLENullTraits-Struktur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "HANDLENullTraits-Struktur"
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
caps.latest.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# HANDLENullTraits-Struktur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Definiert allgemeine Eigenschaften eines nicht initialisierten Handles.  
  
## Syntax  
  
```  
struct HANDLENullTraits;  
```  
  
## Member  
  
### Öffentliche Typedefs  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|`Type`|Ein Synonym für HANDLE.|  
  
### Öffentliche Methoden  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[HANDLENullTraits::Close\-Methode](../windows/handlenulltraits-close-method.md)|Schließt das angegebene Handle.|  
|[HANDLENullTraits::GetInvalidValue\-Methode](../windows/handlenulltraits-getinvalidvalue-method.md)|Stellt ein ungültiges Handle dar.|  
  
## Vererbungshierarchie  
 `HANDLENullTraits`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:**  Microsoft::WRL::Wrappers::HandleTraits  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers::HandleTraits\-Namespace](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)