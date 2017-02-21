---
title: "CreatorMap::factoryCreator-Datenmember | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap::factoryCreator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "factoryCreator-Datenmember"
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreatorMap::factoryCreator-Datenmember
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Unterstützt die WRL\-Infrastruktur und nicht beabsichtigt, direkt im Code verwendet werden.  
  
## Syntax  
  
```  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
## Parameter  
 `currentflags`  
 Einer der [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) Enumeratoren.  
  
 `entry`  
 Ein CreatorMap.  
  
 `iidClassFactory`  
 Die die Schnittstellen\-ID einer Klassenfactorys.  
  
 `factory`  
 Wenn der Vorgang abgeschlossen ist, die Adresse einer Klassenfactorys.  
  
## Rückgabewert  
 S\_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.  
  
## Hinweise  
 Stellt eine Factory für das angegebene CreatorMap erstellt.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:**  Microsoft::WRL::Details  
  
## Siehe auch  
 [CreatorMap\-Struktur](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details\-Namespace](../windows/microsoft-wrl-details-namespace.md)