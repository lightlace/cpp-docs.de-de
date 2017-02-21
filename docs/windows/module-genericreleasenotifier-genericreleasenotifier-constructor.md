---
title: "Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GenericReleaseNotifier-Klasse"
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Initialisiert eine neue Instanz der Module::GenericReleaseNotifier\-Klasse.  
  
## Syntax  
  
```  
GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### Parameter  
 `callback`  
 Das Lambda, ein Funktionselement oder ein Zeiger\-zuFunktionsereignishandler, der mit dem Klammerfunktionsoperator \(`()`\) aufgerufen werden kann.  
  
 `release`  
 Geben Sie `true` an, um die zugrunde liegenden [Module::ReleaseNotifier::Release\(\)](../windows/module-releasenotifier-release.md)\-Methode zu aktivieren; andernfalls geben Sie `false` an.  
  
## Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## Siehe auch  
 [Module::GenericReleaseNotifier\-Klasse](../windows/module-genericreleasenotifier-class.md)