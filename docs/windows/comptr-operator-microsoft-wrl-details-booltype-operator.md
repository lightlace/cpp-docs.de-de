---
title: 'Comptr:: booltype-Operator | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: cfba6521-fb30-4fb8-afb2-cfab1cb5e0b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 135c6d851be5de8f2eb976baf015f2ef449600c0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595972"
---
# <a name="comptroperator-microsoftwrldetailsbooltype-operator"></a>ComPtr::operator Microsoft::WRL::Details::BoolType-Operator

Gibt an, ob eine **ComPtr** die Objektlebensdauer einer Schnittstelle verwaltet.

## <a name="syntax"></a>Syntax

```cpp
WRL_NOTHROW operator Microsoft::WRL::Details::BoolType() const;
```

## <a name="return-value"></a>Rückgabewert

Wenn eine Schnittstelle zugeordnet ist **ComPtr**, die Adresse der [boolstruct::](../windows/boolstruct-member-data-member.md) -Datenmember ist, andernfalls **"nullptr"**.

## <a name="requirements"></a>Anforderungen

**Header:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[ComPtr-Klasse](../windows/comptr-class.md)  
[ComPtr::Get-Methode](../windows/comptr-get-method.md)