---
title: GetModuleBase-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afa76ad23c509689dd693bb0f3e13dbb7adb4d54
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50075449"
---
# <a name="getmodulebase-function"></a>GetModuleBase-Funktion
Ruft eine [ModuleBase](../windows/modulebase-class.md) Zeiger, der inkrementiert und dekrementiert den Verweiszähler des ermöglicht eine [RuntimeClass](../windows/runtimeclass-class.md) Objekt.

## <a name="syntax"></a>Syntax

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf ein `ModuleBase` -Objekt.

## <a name="remarks"></a>Hinweise

Diese Funktion wird intern zum Inkrementieren und Dekrementieren verwendet Verweiszähler des Objekts.

Sie können diese Funktion verwenden, zum Steuern der Verweiszähler durch Aufrufen von [modulebase:: Incrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) und [modulebase:: Decrementobjectcount](../windows/modulebase-decrementobjectcount-method.md).

## <a name="requirements"></a>Anforderungen

**Header:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Siehe auch

[Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)