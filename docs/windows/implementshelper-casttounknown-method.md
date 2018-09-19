---
title: 'Implementshelper:: Casttounknown-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CastToUnknown
dev_langs:
- C++
helpviewer_keywords:
- CastToUnknown method
ms.assetid: 5bcfcbaf-c75f-4d43-87b3-0d6838c838d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b786bb41e9f0667ebbb81329b2f0977525d4ba96
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598061"
---
# <a name="implementshelpercasttounknown-method"></a>ImplementsHelper::CastToUnknown-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
IUnknown* CastToUnknown();
```

## <a name="return-value"></a>Rückgabewert

Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle.

## <a name="remarks"></a>Hinweise

Ruft einen Zeiger auf die zugrunde liegende `IUnknown` Schnittstelle für den aktuellen `Implements` Struktur.

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ImplementsHelper-Struktur](../windows/implementshelper-structure.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)