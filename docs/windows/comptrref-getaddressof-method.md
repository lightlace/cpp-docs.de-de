---
title: 'Comptrref:: Getaddressof-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::GetAddressOf
dev_langs:
- C++
helpviewer_keywords:
- GetAddressOf method
ms.assetid: 797df323-a2fa-412b-ab60-32cce3721096
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b1ef298dbc8c15dddafedd74c83476663328d42f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42602659"
---
# <a name="comptrrefgetaddressof-method"></a>ComPtrRef::GetAddressOf-Methode

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
InterfaceType* const * GetAddressOf() const;
```

## <a name="return-value"></a>Rückgabewert

Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen **ComPtrRef** Objekt.

## <a name="remarks"></a>Hinweise

Ruft die Adresse eines Zeigers auf die Schnittstelle, die vom aktuellen **ComPtrRef** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRef-Klasse](../windows/comptrref-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)