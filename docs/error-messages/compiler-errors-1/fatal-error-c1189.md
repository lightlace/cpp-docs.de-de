---
title: Schwerwiegender Fehler C1189 | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1189
dev_langs:
- C++
helpviewer_keywords:
- C1189
ms.assetid: 2e5c8a78-edd4-411c-b619-558a96be148a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 051b7eb965526d12311dfacaeae7a00e4fbe4e75
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33199793"
---
# <a name="fatal-error-c1189"></a>Schwerwiegender Fehler C1189

> **\#Fehler:** *benutzerdefinierte Fehlermeldung*

## <a name="remarks"></a>Hinweise

C1189 wird generiert, indem die `#error` Richtlinie. Der Entwickler, der die Direktive codes gibt den Text der Fehlermeldung. Weitere Informationen finden Sie unter [#error-Direktive (C/C++)](../../preprocessor/hash-error-directive-c-cpp.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird C1189 generiert. In diesem Beispiel gibt der Entwickler eine benutzerdefinierte Fehlermeldung, da die `_WIN32` Bezeichner ist nicht definiert:

```cpp
// C1189.cpp
#undef _WIN32
#if !defined(_WIN32)
#error _WIN32 must be defined   // C1189
#endif
```

## <a name="see-also"></a>Siehe auch

[#define-Direktive (C/C++)](../../preprocessor/hash-define-directive-c-cpp.md)