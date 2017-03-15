---
title: "RoInitializeWrapper-Klasse | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper"
dev_langs: 
  - "C++"
ms.assetid: 4055fbe0-63a7-4c06-b5a0-414fda5640e5
caps.latest.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 2
---
# RoInitializeWrapper-Klasse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert das [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
## Syntax  
  
```  
class RoInitializeWrapper  
```  
  
## Hinweise  
 RoInitializeWrapper halber ist eine [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], die initialisiert und gibt ein HRESULT zurück, das angibt, dass der Vorgang erfolgreich war.  
  
## Member  
  
### Öffentliche Konstruktoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[RoInitializeWrapper::RoInitializeWrapper\-Konstruktor](../windows/roinitializewrapper-roinitializewrapper-constructor.md)|Initialisiert eine neue Instanz der RoInitializeWrapper\-Klasse.|  
|[RoInitializeWrapper::~RoInitializeWrapper\-Destruktor](../windows/roinitializewrapper-tilde-roinitializewrapper-destructor.md)|Zerstört die aktuelle Instanz der RoInitializeWrapper\-Klasse.|  
  
### Öffentliche Operatoren  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[RoInitializeWrapper::HRESULT\(\)\-Operator](../windows/roinitializewrapper-hresult-parens-operator.md)|Ruft das HRESULT ab, das vom RoInitializeWrapper\-Konstruktor erzeugt wird.|  
  
## Vererbungshierarchie  
 `RoInitializeWrapper`  
  
## Anforderungen  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## Siehe auch  
 [Microsoft::WRL::Wrappers\-Namespace](../windows/microsoft-wrl-wrappers-namespace.md)