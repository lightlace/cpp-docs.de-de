---
title: embedded_idl-Attribut importieren
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: 01948b171b20ad0a3bf3e7a41047f1fe3df185b0
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216328"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl-Attribut importieren

**C++Zugeschnitten**

Gibt an, ob die Typbibliothek in die `.tlh` Datei geschrieben wird, wobei der Attribut generierte Code beibehalten wird.

## <a name="syntax"></a>Syntax

> **#Import** *Typbibliothek* **embedded_idl** [ **(** { **"Emitidl"**  | "**no_emitidl"** } **)** ]

### <a name="parameters"></a>Parameter

**Emitidl**\
Typinformationen, die aus der *Typbibliothek* importiert werden, sind in der IDL vorhanden, die für das attributierte Projekt generiert wurde. Dieses Verhalten ist die Standardeinstellung und ist wirksam, wenn Sie keinen Parameter für `embedded_idl`angeben.

**"no_emitidl"** \
Typinformationen, die aus der *Typbibliothek* importiert werden, sind nicht in der für das attributierte Projekt generierten IDL vorhanden.

## <a name="example"></a>Beispiel

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**End C++ -Specific**

## <a name="see-also"></a>Siehe auch

[#Import Attribute](../preprocessor/hash-import-attributes-cpp.md)\
[#Import-Direktive](../preprocessor/hash-import-directive-cpp.md)
