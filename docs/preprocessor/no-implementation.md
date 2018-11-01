---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: d4e55d06bef823d28c5deb3467654bc530a3853e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456783"
---
# <a name="noimplementation"></a>no_implementation
**C++-spezifisch**

Unterdrückt die Generierung des TLI-Headers, der die Implementierungen der Wrappermemberfunktionen enthält.

## <a name="syntax"></a>Syntax

```
no_implementation
```

## <a name="remarks"></a>Hinweise

Wenn dieses Attribut festgelegt ist, wird der TLH-Header mit den Deklarationen zur Bereitstellung von Typbibliothekselementen ohne eine `#include`-Anweisung zur Einbindung der TLI-Headerdatei generiert.

Dieses Attribut wird verwendet, in Verbindung mit [Implementation_only](../preprocessor/implementation-only.md).

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)