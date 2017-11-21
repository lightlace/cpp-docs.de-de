---
title: Module::GenericReleaseNotifier::GenericReleaseNotifier Konstruktor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::GenericReleaseNotifier::GenericReleaseNotifier
dev_langs: C++
helpviewer_keywords: GenericReleaseNotifier, constructor
ms.assetid: feb5b687-a4b0-4809-9022-8f292181b7a1
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: f0309040b64614280d2314daa83c5919514b3fb6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="modulegenericreleasenotifiergenericreleasenotifier-constructor"></a>Module::GenericReleaseNotifier::GenericReleaseNotifier-Konstruktor
Initialisiert eine neue Instanz der genericreleasenotifier-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      GenericReleaseNotifier(  
   T callback,   
   bool release  
) throw() : ReleaseNotifier(release), callback_(callback);  
```  
  
#### <a name="parameters"></a>Parameter  
 `callback`  
 Ein Lambda, Funktionselement oder Zeiger auf Funktion Ereignishandler, die mit der Funktion klammeroperator aufgerufen werden können (`()`).  
  
 `release`  
 Geben Sie `true` So aktivieren Sie das zugrunde liegende Aufrufen [Modul:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) Methode; andernfalls geben `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Module::GenericReleaseNotifier-Klasse](../windows/module-genericreleasenotifier-class.md)