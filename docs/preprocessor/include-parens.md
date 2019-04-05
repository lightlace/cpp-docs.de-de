---
title: include()
ms.date: 10/18/2018
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: 1208f14a9f6b3724dd5353df57213baa3910d07f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040926"
---
# <a name="include"></a>include()

**C++-spezifisch**

Deaktiviert den automatische Ausschluss.

## <a name="syntax"></a>Syntax

```
include("Name1"[,"Name2", ...])
```

### <a name="parameters"></a>Parameter

*Name1*<br/>
Das erste Element, dessen Aufnahme erzwungen wird.

*Name2*<br/>
Das zweite Element, dessen Aufnahme erzwungen wird (falls erforderlich).

## <a name="remarks"></a>Hinweise

Typbibliotheken können Definitionen der Elemente enthalten, die in Systemheadern oder anderen Typbibliotheken definiert sind. `#import` versucht, mehrfache definitionsfehler zu vermeiden, indem Sie solche Elemente automatisch ausgeschlossen. Wenn Elemente ausgeschlossen wurden durch, [Compilerwarnung (Stufe 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md), und es sollten keine wurden, dieses Attribut kann verwendet werden, um den automatischen Ausschluss zu deaktivieren. Dieses Attribut kann eine beliebige Anzahl von Argumenten akzeptieren, die jeweils der Name des einzuschließenden Typbibliothekelements sind.

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)