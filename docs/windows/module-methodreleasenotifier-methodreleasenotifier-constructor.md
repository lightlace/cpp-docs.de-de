---
title: Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::MethodReleaseNotifier::MethodReleaseNotifier
dev_langs:
- C++
helpviewer_keywords:
- MethodReleaseNotifier, constructor
ms.assetid: 762e2ca4-0a92-49de-9ff5-d3efa0f067c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8e48b6f8ec4a985bfa7fa5b8d0069e472df86e8
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605989"
---
# <a name="modulemethodreleasenotifiermethodreleasenotifier-constructor"></a>Module::MethodReleaseNotifier::MethodReleaseNotifier-Konstruktor
Initialisiert eine neue Instanz der dem **methodreleasenotifier** Klasse.  
  
## <a name="syntax"></a>Syntax  
  
```  
MethodReleaseNotifier(  
   _In_ T* object,   
   _In_ void (T::* method)(),   
   bool release) throw() :  
            ReleaseNotifier(release), object_(object),   
            method_(method);  
```  
  
### <a name="parameters"></a>Parameter  
 *object*  
 Ein Objekt, dessen Memberfunktion ein Ereignishandler ist.  
  
 *Methode*  
 Die Member-Funktion des Parameters *Objekt* , den Ereignishandler.  
  
 *release*  
 Geben Sie **"true"** aktivieren aufrufen, die zugrunde liegende [Modul:: ReleaseNotifier::Release()](../windows/module-releasenotifier-release.md) Methode geben Sie andernfalls **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Module::MethodReleaseNotifier-Klasse](../windows/module-methodreleasenotifier-class.md)