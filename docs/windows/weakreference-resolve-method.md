---
title: 'WeakReference:: Resolve-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59e748ef68d78f9cb77eb335f5c5cd44e058f0d4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601155"
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
STDMETHOD(Resolve)  
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parameter

*riid*  
Eine Schnittstellen-ID.

*ppvObject*  
Wenn dieser Vorgang abgeschlossen ist, eine Kopie der aktuellen starken Verweis, wenn die Anzahl der starken Verweis ungleich NULL ist.

## <a name="return-value"></a>Rückgabewert

- S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist 0 (null). Die *PpvObject* Parametersatz zu **"nullptr"**.

- S_OK, wenn dieser Vorgang erfolgreich ist und die Anzahl der starken Verweis ist ungleich NULL. Die *PpvObject* Parameter auf der starke Verweis festgelegt ist.

- Andernfalls Fehler ein HRESULT, das den Grund angibt, diesen Vorgang.

## <a name="remarks"></a>Hinweise

Legt den angegebenen Zeiger auf den aktuellen Wert der starken Verweis fest, wenn die Anzahl der starken Verweis ungleich NULL ist.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[WeakReference-Klasse](../windows/weakreference-class1.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)