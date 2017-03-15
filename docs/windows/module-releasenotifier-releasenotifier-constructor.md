---
title: "Module::ReleaseNotifier::ReleaseNotifier-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::ReleaseNotifier::ReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ReleaseNotifier, Konstruktor"
ms.assetid: 889a3c9a-2366-44a1-ba7d-a59c1885e7f3
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::ReleaseNotifier::ReleaseNotifier-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der Module::ReleaseNotifier\-Klasse.  
  
## Syntax  
  
```cpp  
ReleaseNotifier(bool release) throw();  
```  
  
#### Parameter  
 `release`  
 `true`, um diese Instanz zu löschen, wenn die Versionsmethode aufgerufen wird; `false`, um diese Instanz nicht gelöscht.  
  
## Ausnahmen  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Module::ReleaseNotifier\-Klasse](../windows/module-releasenotifier-class.md)