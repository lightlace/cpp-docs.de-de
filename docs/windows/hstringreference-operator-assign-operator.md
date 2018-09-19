---
title: 'Hstringreference:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HStringReference::operator=
dev_langs:
- C++
ms.assetid: ea100ed3-e566-4c9e-b6a8-f296088dea9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7045229cc15304a88253f97e1ad3c9f171f139a0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42597127"
---
# <a name="hstringreferenceoperator-operator"></a>HStringReference::Operator=-Operator

Verschiebt den Wert eines anderen **HStringReference** -Objekt mit dem aktuellen **HStringReference** Objekt.

## <a name="syntax"></a>Syntax

```cpp
HStringReference& operator=(HStringReference&& other) throw()  
```

### <a name="parameters"></a>Parameter

*other*  
Eine vorhandene **HStringReference** Objekt.

## <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen **HStringReference** -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HStringReference-Klasse](../windows/hstringreference-class.md)