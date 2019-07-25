---
title: _SCL_SECURE_NO_WARNINGS
ms.date: 11/04/2016
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
ms.openlocfilehash: d19d47fe7120301740e1431765fc6edbeaa48c60
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448190"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

Wenn eine der potenziell unsicheren Methoden in der C++ Standard Bibliothek aufgerufen wird, führt dies zu einer Compilerwarnung [(Ebene 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Um diese Warnung zu deaktivieren, definieren Sie das Makro _SCL_SECURE_NO_WARNINGS im Code:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Wenn Sie vorkompilierte Header verwenden, fügen Sie diese Direktive in die vorkompilierte Header Datei ein, bevor Sie eine C-Lauf Zeit Bibliothek oder Standard Bibliotheks Header einschließen. Wenn Sie Sie in einer einzelnen Quell Code Datei ablegen, bevor Sie die vorkompilierte Header Datei einschließen, wird Sie vom Compiler ignoriert.

## <a name="remarks"></a>Hinweise

Weitere Methoden zum Deaktivieren der Warnung C4996 sind u.a.:

- Mithilfe der Compileroption [/D (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md):

   > cl/D_SCL_SECURE_NO_WARNINGS [sonstige Compileroptionen] MyFile. cpp

- Mithilfe der Compileroption [/w](../build/reference/compiler-option-warning-level.md):

   > cl/wd4996 [sonstige Compileroptionen] MyFile. cpp

- Mithilfe der Anweisung [#pragma warning](../preprocessor/warning.md):

   ```cpp
   #pragma warning(disable:4996)
   ```

Sie können die Stufe der Warnung C4996 mit der Compileroption **/w\<l >\<n >** auch manuell ändern. Um beispielsweise die Warnung C4996 auf Stufe 4 festzulegen:

> cl/w44996 [sonstige Compileroptionen] MyFile. cpp

Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Siehe auch

[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)
