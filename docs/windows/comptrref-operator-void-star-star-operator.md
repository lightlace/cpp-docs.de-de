---
title: 'Comptrref:: Operator Void **-Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator void**
dev_langs:
- C++
helpviewer_keywords:
- operator void** operator
ms.assetid: f020045c-9de4-4392-8783-73f0fc0761c6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 977e04b923a99cab3eb42544de99c4fcee974e82
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408868"
---
# <a name="comptrrefoperator-void-operator"></a>Comptrref:: "void"\* \* Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
operator void**() const;
```

## <a name="remarks"></a>Hinweise

Löscht die aktuelle **ComPtrRef** Objekt, wandelt der Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** -Objekt als eine Zeiger-auf-Zeiger-auf **"void"**, und klicken Sie dann Gibt die Cast-Zeiger zurück.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRef-Klasse](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)