---
title: 'Comptrref:: Releaseandgetaddressof-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::ReleaseAndGetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- ReleaseAndGetAddressOf method
ms.assetid: 004aac42-e135-41ce-8d1d-4c5969d55004
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 03f709feddb1c0e9c82cf80a4bd5f24e531414d3
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611218"
---
# <a name="comptrrefreleaseandgetaddressof-method"></a>ComPtrRef::ReleaseAndGetAddressOf-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
InterfaceType** ReleaseAndGetAddressOf();
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die Schnittstelle, die dargestellt wird, wurde von der gelöschten **ComPtrRef** Objekt.

## <a name="remarks"></a>Hinweise

Löscht die aktuelle **ComPtrRef** Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRef-Klasse](../windows/comptrref-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)