---
title: Module::MethodReleaseNotifier::MethodReleaseNotifier Konstruktor | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 045dd8dd0dbee58c0feea33bc7ce4f6cea30e591
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor
Initialisiert eine neue Instanz der methodreleasenotifier-Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
#### <a name="parameters"></a>Parameter  
 `object`  
 Ein Objekt, dessen Memberfunktion ein Ereignishandler ist.  
  
 `method`  
 Die Memberfunktion des Parameters `object` also den Ereignishandler.  
  
 `release`  
 Geben Sie `true` So aktivieren Sie das zugrunde liegende Aufrufen [Modul:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) Methode; andernfalls geben `false`.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Module::MethodReleaseNotifier-Klasse](../windows/module-methodreleasenotifier-class.md)