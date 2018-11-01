---
title: uuid (C++)
ms.date: 11/04/2016
f1_keywords:
- uuid_cpp
helpviewer_keywords:
- __declspec keyword [C++], uuid
- uuid __declspec keyword
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
ms.openlocfilehash: c121ad99dfbe0021a263f324ccdb9a95441bba33
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511656"
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