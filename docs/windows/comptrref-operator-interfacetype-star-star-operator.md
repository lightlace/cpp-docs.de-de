---
title: 'Comptrref:: Operator InterfaceType ** | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRef::operator InterfaceType**
dev_langs:
- C++
helpviewer_keywords:
- operator InterfaceType** operator
ms.assetid: b32e3240-a4f0-4998-a55f-d4e35dc9a15a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 73e1f975aa0d9a03ffb0025573ec20615825b5b6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46390235"
---
# <a name="comptrrefoperator-interfacetype-operator"></a>ComPtrRef::operator InterfaceType**-Operator

Unterstützt die Infrastruktur von WRL und nicht direkt aus Ihrem Code verwendet werden soll.

## <a name="syntax"></a>Syntax

```cpp
operator InterfaceType**();
```

## <a name="remarks"></a>Hinweise

Löscht die aktuelle **ComPtrRef** Objekt und gibt einen Zeiger-auf-ein-Zeiger auf die Schnittstelle, die durch dargestellt wurde die **ComPtrRef** Objekt.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>Siehe auch

[ComPtrRef-Klasse](../windows/comptrref-class.md)<br/>
[Microsoft::WRL::Details-Namespace](../windows/microsoft-wrl-details-namespace.md)