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
ms.openlocfilehash: 8e528bed14f3f6f3b35270975833bdd17fd777db
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422648"
---
# <a name="hstringoperator-operator"></a>HString::Operator=-Operator

Verschiebt den Wert eines anderen **HString** -Objekt mit dem aktuellen **HString** Objekt.

## <a name="syntax"></a>Syntax

```cpp
HString& operator=(HString&& other) throw()  
```

### <a name="parameters"></a>Parameter

*other*<br/>
Eine vorhandene **HString** Objekt.

## <a name="remarks"></a>Hinweise

Der Wert des vorhandenen *andere* Objekt kopiert wird, mit dem aktuellen **HString** -Objekt, und klicken Sie dann die *andere* -Objekt zerstört wird.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)