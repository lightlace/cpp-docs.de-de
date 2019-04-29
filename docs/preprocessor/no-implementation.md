---
title: no_implementation
ms.date: 11/04/2016
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 26527ca69c66c73f5d41084dc42df5faa34481d3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62409810"
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