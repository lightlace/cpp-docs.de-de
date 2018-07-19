---
title: _SCL_SECURE_NO_WARNINGS | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
dev_langs:
- C++
helpviewer_keywords:
- _SCL_SECURE_NO_DEPRECATE
- _SCL_SECURE_NO_WARNINGS
ms.assetid: ef0ddea9-7c62-4b53-8b64-5f4fd369776f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b24012825b883550de6f58e6ce2d53b826f746ca
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965499"
---
# <a name="sclsecurenowarnings"></a>_SCL_SECURE_NO_WARNINGS

Aufruf einer der potenziell unsicheren Methoden in der C++-Standardbibliothek führt zu [Compilerwarnung (Stufe 3) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Um diese Warnung zu deaktivieren, definieren Sie das Makro _SCL_SECURE_NO_WARNINGS in Ihrem Code ein:

```cpp
#define _SCL_SECURE_NO_WARNINGS
```

Bei Verwendung vorkompilierter Header fügen Sie diese Richtlinie in der vorkompilierten Headerdatei ein, bevor Sie alle C-Laufzeitbibliothek oder standard-Bibliothek-Header einfügen. Wenn Sie es in einer einzelnen Quellcodedatei, setzen bevor Sie die vorkompilierte Headerdatei einschließen, wird es vom Compiler ignoriert.

## <a name="remarks"></a>Hinweise

Weitere Methoden zum Deaktivieren der Warnung C4996 sind u.a.:

- Mithilfe der Compileroption [/D (Präprozessordefinitionen)](../build/reference/d-preprocessor-definitions.md):

   > CL /D_SCL_SECURE_NO_WARNINGS [andere Compileroptionen] myfile.cpp

- Mithilfe der Compileroption [/w](../build/reference/compiler-option-warning-level.md):

   > CL-/wd4996 [andere Compileroptionen] myfile.cpp

- Mithilfe der Anweisung [#pragma warning](../preprocessor/warning.md):

   ```cpp
   #pragma warning(disable:4996)
   ```

Sie können die Stufe der Warnung C4996 mit der Compileroption **/w\<l >\<n >** auch manuell ändern. Um beispielsweise die Warnung C4996 auf Stufe 4 festzulegen:

> CL-/w44996 [andere Compileroptionen] myfile.cpp

Weitere Informationen finden Sie unter [/w, /W0, /W1, /W2, /W3, /W4, /w1, /w2, /w3, /w4, /Wall, /wd, /we, /wo, /Wv, /WX (Warnstufe)](../build/reference/compiler-option-warning-level.md).

## <a name="see-also"></a>Siehe auch

[Sichere Bibliotheken: C++-Standardbibliothek](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
