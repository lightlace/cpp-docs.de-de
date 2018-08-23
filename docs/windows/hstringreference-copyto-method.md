---
title: 'Hstringreference:: CopyTo-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: 179d9b14-1ced-4b16-b297-19ca1e92a462
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22886621760ed53649d26180877b1463ec2d3f2d
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42592163"
---
# <a name="hstringreferencecopyto-method"></a>HStringReference::CopyTo-Methode

Kopiert das aktuelle **HStringReference** Objekt zu einem HSTRING-Objekt.

## <a name="syntax"></a>Syntax

```cpp
HRESULT CopyTo(
   _Out_ HSTRING *str
   ) const throw();
```

### <a name="parameters"></a>Parameter

*str*  
Das HSTRING, das die Kopie erhält.

## <a name="remarks"></a>Hinweise

Diese Methode ruft die [WindowsDuplicateString](http://msdn.microsoft.com/library/br224634.aspx) Funktion.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HStringReference-Klasse](../windows/hstringreference-class.md)