---
title: 'Hstring:: Hstring-Konstruktor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HString::HString
dev_langs:
- C++
ms.assetid: 6da12785-ed01-4720-a004-667db60298f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80af8f463d6cd1af631c6cb37c0239e7a9e85c3f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42595884"
---
# <a name="hstringhstring-constructor"></a>HString::HString-Konstruktor

Initialisiert eine neue Instanz der dem **HString** Klasse.

## <a name="syntax"></a>Syntax

```cpp
HString(HSTRING hstr = nullptr) throw();
HString(HString&& other) throw();
```

#### <a name="parameters"></a>Parameter

*HSTR*  
Ein HSTRING-Handle.

*other*  
Eine vorhandene **HString** Objekt.

## <a name="remarks"></a>Hinweise

Der erste Konstruktor initialisiert eine neue **HString** -Objekt, das leer ist.

Der zweite Konstruktor initialisiert eine neue **HString** Objekt, das den Wert des vorhandenen *andere* Parameter, und klicken Sie dann zerstört die *andere* Parameter.

## <a name="requirements"></a>Anforderungen

**Header:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>Siehe auch

[HString-Klasse](../windows/hstring-class.md)