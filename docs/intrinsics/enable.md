---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: e1ece6d6f4040b81b55d8400407d46f165b56b53
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349029"
---
# <a name="enable"></a>_enable

**Microsoft-spezifisch**

Ermöglicht Unterbrechungen.

## <a name="syntax"></a>Syntax

```
void _enable(void);
```

## <a name="requirements"></a>Anforderungen

|Systemintern|Architektur|
|---------------|------------------|
|`_enable`|x86, ARM, x64|

**Headerdatei** \<intrin.h >

## <a name="remarks"></a>Hinweise

`_enable` weist den Prozessor an, das Interrupt-Flag festzulegen. Unter x86-Systemen erzeugt diese Funktion die Anweisung für das Set Interrupt Flag (`sti`).

Diese Funktion ist nur im Kernelmodus verfügbar. Wenn sie im Benutzermodus verwendet wird, wird eine privilegierte Anweisungsausnahme ausgelöst.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Intrinsische Compilerfunktionen](../intrinsics/compiler-intrinsics.md)