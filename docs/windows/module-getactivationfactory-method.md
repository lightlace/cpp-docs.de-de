---
title: 'Module:: getactivationfactory-Methode | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5d5c5ca4d470f52ff9dde862cc99b10a3459cd0c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="modulegetactivationfactory-method"></a>Module::GetActivationFactory-Methode
Ruft eine aktivierungsfactory für das Modul an.  
  
## <a name="syntax"></a>Syntax  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pActivatibleClassId`  
 Die IID der Common Language Runtime-Klasse.  
  
 `ppIFactory`  
 Die IActivationFactory für die angegebene Runtime-Klasse.  
  
 `serverName`  
 Der Name einer Teilmenge von Klassenfactorys im aktuellen Modul. Geben Sie den Servernamen in verwendet die [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) -Makro, oder geben Sie `nullptr` der Standardservername abgerufen.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Das HRESULT, andernfalls zurückgegebenes GetActivationFactory.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** module.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
[Module-Klasse](../windows/module-class.md) [ActivatableClass-Makros](../windows/activatableclass-macros.md)