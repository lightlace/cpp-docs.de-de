---
title: stdext-Namespace
ms.date: 09/06/2017
f1_keywords:
- stdext
helpviewer_keywords:
- _DEFINE_DEPRECATED_HASH_CLASSES symbol
- stdext namespace
ms.assetid: 3e94fc89-0584-424f-bc09-081b73379545
ms.openlocfilehash: aeba486393e6b45481108f967f3de8eb73a0adea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468483"
---
# <a name="stdext-namespace"></a>stdext-Namespace

Mitglieder der [ \<Hash_map >](../standard-library/hash-map.md) und [ \<Hash_set >](../standard-library/hash-set.md) -Headerdateien sind nicht Teil des ISO C++-Standards. Daher wurden diese Typen und Member aus dem `std` -Namespace in den `stdext`-Namespace verschoben, um dem C++-Standard zu entsprechen.

Beim Kompilieren mit [/Ze](../build/reference/za-ze-disable-language-extensions.md), dies ist die Standardeinstellung, der Compiler eine Warnung aus, für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien. Verwenden Sie das [warning](../preprocessor/warning.md) -Pragma, um die Warnung zu deaktivieren.

Damit den Compiler generiert einen Fehler für die Verwendung von `std` für Mitglieder der \<Hash_map > und \<Hash_set > Headerdateien mit **/Ze**, fügen Sie die folgende Anweisung vor der `#include` beliebiger Headerdateien der C++-Standardbibliothek.

```cpp
#define _DEFINE_DEPRECATED_HASH_CLASSES 0
```

Beim Kompilieren mit **/Za**, generiert der Compiler einen Fehler.

## <a name="see-also"></a>Siehe auch

[Überblick über die C++-Standardbibliothek](../standard-library/cpp-standard-library-overview.md)

