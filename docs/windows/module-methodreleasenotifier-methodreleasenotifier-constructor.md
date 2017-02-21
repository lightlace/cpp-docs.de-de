---
title: "Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MethodReleaseNotifier, Konstruktor"
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der Module::MethodReleaseNotifier\-Klasse.  
  
## Syntax  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### Parameter  
 `object`  
 Ein Objekt, dessen Memberfunktion ein Ereignishandler ist.  
  
 `method`  
 Die Memberfunktion des `object`\-Parameters, der der Ereignishandler ist.  
  
 `release`  
 Geben Sie `true` an, um die zugrunde liegenden [Module::ReleaseNotifier::Release\(\)](../windows/module-releasenotifier-release.md)\-Methode zu aktivieren; andernfalls geben Sie `false` an.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Module::MethodReleaseNotifier\-Klasse](../windows/module-methodreleasenotifier-class.md)