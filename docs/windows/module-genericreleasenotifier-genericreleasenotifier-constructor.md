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
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f5f6f656ff1908dc215efb1fc322b348618a236d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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