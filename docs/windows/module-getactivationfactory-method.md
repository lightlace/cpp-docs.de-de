---
title: 'Module:: getactivationfactory-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f6fda1c514b6cb3e60a55d35323bf8b116f850ac
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011867"
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory-Methode
Ruft eine aktivierungsfactory für das Modul ab.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *pActivatibleClassId*  
 Die IID der von einer Runtime-Klasse.  
  
 *ppIFactory*  
 Die "iactivationfactory" für die angegebene Runtime-Klasse.  
  
 *ServerName*  
 Der Name einer Teilmenge von Klassenfactorys im aktuellen Modul. Geben Sie den Servernamen in verwendet die [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) -Makro, oder geben Sie **"nullptr"** um den Standardnamen für den Server zu erhalten.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls der HRESULT-Wert zurückgegeben, indem GetActivationFactory.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Module-Klasse](../windows/module-class.md)  
 [ActivatableClass-Makros](../windows/activatableclass-macros.md)