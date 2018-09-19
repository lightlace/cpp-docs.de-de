---
title: 'Runtimeclassbaset:: Getimplementediids-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 907a249090ec58d6379cb58f3d63e15826c1f6ad
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610359"
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>RuntimeClassBaseT::GetImplementedIIDS-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
template<typename T>
__forceinline static HRESULT GetImplementedIIDS(
   _In_ T* implements,
   _Out_ ULONG *iidCount,
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids
);
```

### <a name="parameters"></a>Parameter

*T*  
Der Typ des der *implementiert* Parameter.

*Implementiert*  
Zeiger auf den vom Parameter angegebenen Typ *T*.

*iidCount*  
Die maximale Anzahl von Schnittstellen-IDs abrufen.

*IIDs*  
Wenn dieser Vorgang erfolgreich abgeschlossen, ein Array von die Schnittstellen-IDs, die vom Typ implementiert wird *T*.

## <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler beschreibt.

## <a name="remarks"></a>Hinweise

Ruft ein Array von Schnittstellen-IDs, die von einem angegebenen Typ implementiert werden.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[RuntimeClassBaseT-Struktur](../windows/runtimeclassbaset-structure.md)