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
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70740466"
---
# <a name="uuid-c"></a>uuid (C++)

**Microsoft-spezifisch**

Der Compiler fügt eine GUID an eine Klasse oder Struktur an, die deklariert oder definiert wurde (nur vollständige COM-Objekt Definitionen) mit dem **UUID** -Attribut.

## <a name="syntax"></a>Syntax

```
__declspec( uuid("ComObjectGUID") ) declarator
```

## <a name="remarks"></a>Hinweise

Das **UUID** -Attribut nimmt eine Zeichenfolge als Argument an. Diese Zeichenfolge benennt eine GUID im normalen Registrierungs Format mit oder ohne **{}** -Trennzeichen. Beispiel:

```cpp
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;
```

Dieses Attribut kann in einer Neudeklaration angewendet werden. Dadurch können die System Header die Definitionen der Schnittstellen wie `IUnknown`und die Neudeklaration in einem anderen Header ( \<z. b. comdef. h >) bereitstellen, um die GUID bereitzustellen.

Das Schlüsselwort [__uuidof](../cpp/uuidof-operator.md) kann angewendet werden, um die Konstante GUID abzurufen, die an einen benutzerdefinierten Typ angefügt ist.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[__declspec](../cpp/declspec.md)<br/>
[Schlüsselwörter](../cpp/keywords-cpp.md)