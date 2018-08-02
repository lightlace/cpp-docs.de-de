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
ms.openlocfilehash: 19e04f5415f9f7a736371c888dff7559df6c6c66
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462335"
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

Diese Umwandlung ist verfügbar nur, wenn **&#95; &#95;WRL_CLASSIC_COM&#95; &#95;** definiert ist.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch
[ComPtrRefBase-Klasse](../windows/comptrrefbase-class.md)   
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)