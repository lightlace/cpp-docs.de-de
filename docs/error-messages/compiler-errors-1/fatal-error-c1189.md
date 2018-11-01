---
title: Schwerwiegender Fehler C1189
ms.date: 04/27/2018
f1_keywords:
- C1189
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
ms.openlocfilehash: 06d42316a0109ac063bba43cefebd9aab71c2e72
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565528"
---
# <a name="fatal-error-c1189"></a>Schwerwiegender Fehler C1189

> **\#Fehler:** *benutzerdefinierte Fehlermeldung*

## <a name="remarks"></a>Hinweise

C1189 wird generiert, indem die `#error` Richtlinie. Der Entwickler, der die Direktive codes gibt den Text der Fehlermeldung an. Weitere Informationen finden Sie unter [#error-Direktive (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Beispiel

Im folgende Beispiel wird die C1189 generiert. In diesem Beispiel gibt der Entwickler eine benutzerdefinierte Fehlermeldung, da die `_WIN32` Bezeichner ist nicht definiert:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Siehe auch

[#define-Direktive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)