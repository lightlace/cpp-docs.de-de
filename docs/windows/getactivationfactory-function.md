---
title: GetActivationFactory-Funktion | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd269b8c2e1c671944305d385064d60e8bf9b8a1
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="getactivationfactory-function"></a>GetActivationFactory-Funktion
Ruft eine aktivierungsfactory für den durch den Vorlagenparameter angegebenen Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Ein Vorlagenparameter, der den Typ der aktivierungsfactory angibt.  
  
 `activatableClassId`  
 Der Name der Klasse, die die aktivierungsfactory erstellt werden kann.  
  
 `factory`  
 Wenn dieser Vorgang abgeschlossen wird, einen Verweis auf die aktivierungsfactory für Typ `T`.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, das angibt, warum diese Operation fehlgeschlagen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Windows:: Foundation  
  
## <a name="see-also"></a>Siehe auch  
 [Windows::Foundation-Namespace](../windows/windows-foundation-namespace.md)