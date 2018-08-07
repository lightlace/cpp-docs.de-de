---
title: GetActivationFactory-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2cbb5be3603f79a7df1cb330ca06775357666854
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570310"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory-Funktion
Ruft eine aktivierungsfactory für den durch die Template-Parameter angegebenen Typ ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
### <a name="parameters"></a>Parameter  
 *T*  
 Ein Vorlagenparameter, der angibt, welche die aktivierungsfactory.  
  
 *activatableClassId*  
 Der Name der Klasse, die die Aktivierungs-Factory erstellt werden kann.  
  
 *Factory*  
 Wenn dieser Vorgang abgeschlossen ist, einen Verweis auf die aktivierungsfactory für den Typ *T*.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; andernfalls ein Fehler HRESULT, der angibt, warum dieser Vorgang fehlgeschlagen ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Windows:: Foundation  
  
## <a name="see-also"></a>Siehe auch  
 [Windows::Foundation-Namespace](../windows/windows-foundation-namespace.md)