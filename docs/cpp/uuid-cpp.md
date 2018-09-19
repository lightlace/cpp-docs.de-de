---
title: UUID (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- uuid_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44799b507fb9c27cb1d9f166e86228ed6003a0d8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46086186"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft-spezifisch**

Der Compiler Fügt eine GUID an eine Klasse oder Struktur deklariert oder definiert (vollständige COM-Objekt nur Definitionen) mit der **Uuid** Attribut.

## <a name="syntax"></a>Syntax

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Hinweise

Die **Uuid** Attribut nimmt eine Zeichenfolge als Argument. Diese Zeichenfolge gibt eine GUID im normalen Registrierungsformat mit oder ohne die **{}** Trennzeichen. Zum Beispiel:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Dieses Attribut kann in einer Neudeklaration angewendet werden. Dadurch können die Systemheader die Definitionen von Schnittstellen bereitstellen, wie `IUnknown`, und die Neudeklaration in einem anderen Header (z. B. \<comdef.h >) zum Angeben der GUID.

Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) angewendet werden, um die Konstante abrufen, GUID, die an einen benutzerdefinierten Typ angefügt.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)