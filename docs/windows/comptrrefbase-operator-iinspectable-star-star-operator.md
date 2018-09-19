---
title: 'Comptrrefbase:: Operator IInspectable ** | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IInspectable**
dev_langs:
- C++
helpviewer_keywords:
- operator IInspectable** operator
ms.assetid: 06ac1051-606c-449b-a566-cac78ca53762
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f711a9d1f5fe92e5f35bf333fc0b3473fc0eebf4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604405"
---
# <a name="comptrrefbaseoperator-iinspectable-operator"></a>Comptrrefbase:: "iinspectable"\* \* Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
operator IInspectable**() const;
```

## <a name="remarks"></a>Hinweise

Wandelt das aktuelle [Ptr_](../windows/comptrrefbase-ptr-data-member.md) Datenmembers, der einen Zeiger an eine-Zeiger-an die `IInspectable` Schnittstelle.

Ein Fehler wird ausgegeben, wenn die aktuelle **ComPtrRefBase** nicht abgeleitet `IInspectable`.

Diese Umwandlung ist verfügbar nur, wenn `__WRL_CLASSIC_COM__` definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)  
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)