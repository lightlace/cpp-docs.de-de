---
title: 'Hstring:: Operator = | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::operator=
dev_langs:
- C++
ms.assetid: 8e68c1ff-bc57-4526-810e-af3c284b4e30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9294650db7a1b18c2542603988952a80b3f1905d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42598544"
---
# <a name="hstringoperator-operator"></a>HString::Operator=-Operator

Verschiebt den Wert eines anderen **HString** -Objekt mit dem aktuellen **HString** Objekt.

## <a name="syntax"></a>Syntax

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>Parameter

*other*  
Eine vorhandene **HString** Objekt.

## <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen **HString** -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)