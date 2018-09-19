---
title: 'Hstring:: Getaddressof-Methode | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs:
- C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e327e2818903396c154be7406ec325695b6b6982
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42613364"
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf-Methode

Ruft einen Zeiger auf das zugrunde liegende HSTRING-Handle ab.

## <a name="syntax"></a>Syntax

```cpp
HSTRING* GetAddressOf() throw()  
```

## <a name="return-value"></a>Rückgabewert

Ein Zeiger auf das zugrunde liegende HSTRING-Handle.

## <a name="remarks"></a>Hinweise

Nach diesem Vorgang wird der Zeichenfolgenwert, der das zugrunde liegende HSTRING-Handle zerstört.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)