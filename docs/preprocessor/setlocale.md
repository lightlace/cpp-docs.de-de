---
title: setlocale-Pragma
ms.date: 08/29/2019
f1_keywords:
- setlocale_CPP
- vc-pragma.setlocale
helpviewer_keywords:
- pragmas, setlocale
- setlocale pragma
ms.assetid: e60b43d9-fbdf-4c4e-ac85-805523a13b86
ms.openlocfilehash: 219354595e5c63b2f13211d43bfa517d97413251
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218175"
---
# <a name="setlocale-pragma"></a>setlocale-Pragma

Definiert dasGebiets Schema, das Land, die Region und die Sprache, die beim Übersetzen von breit Zeichen Konstanten und Zeichenfolgenliteralen verwendet werden.

## <a name="syntax"></a>Syntax

> **#pragma setlocale ("** [ *locale-String* ] **")**

## <a name="remarks"></a>Hinweise

Da der Algorithmus zum Umrechnen von Multibytezeichen in breit Zeichen je nach Gebiets Schema variieren kann, oder die Kompilierung in einem anderen Gebiets Schema stattfinden kann, in dem eine ausführbare Datei ausgeführt wird, bietet dieses Pragma eine Möglichkeit, das Ziel Gebiets Schema zur Kompilierzeit anzugeben. Sie gewährleistet, dass breit Zeichen-Zeichen folgen im richtigen Format gespeichert werden.

Die standardmäßige Gebiets Schema *Zeichenfolge* ist "".

Mit dem Gebiets Schema "C" wird jedes Zeichen in der Zeichenfolge dem Wert als **wchar_t**zugeordnet. Weitere gültige Werte für `setlocale` sind die Einträge, die in der Liste der [Sprachen](../c-runtime-library/language-strings.md) Zeichenfolgen gefunden werden. Beispielsweise können Sie Folgendes angeben:

```cpp
#pragma setlocale("dutch")
```

Die Möglichkeit, eine Sprachen Zeichenfolge anzugeben, hängt von der Codepage und der Sprach-ID auf dem Computer ab.

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
