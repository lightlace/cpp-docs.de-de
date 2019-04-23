---
title: embedded_idl
ms.date: 10/18/2018
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: c46924d2757d01a934c21a70f23e6556f6a10fd3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034088"
---
# <a name="embeddedidl"></a>embedded_idl

**C++-spezifisch**

Gibt an, dass die Typbibliothek in die TLH-Datei geschrieben wird und der vom Attribut generierte Code beibehalten wird.

## <a name="syntax"></a>Syntax

```
embedded_idl[("param")]
```

### <a name="parameters"></a>Parameter

*param*<br/>
Kann einer von zwei Werten sein:

- **emitidl**: Typinformationen, die von Typelib importiert werden in der IDL-Datei für das attributierte Projekt generiert vorhanden sein.  Dies ist die Standardeinstellung, die aktiv ist, wenn Sie keinen Parameter für `embedded_idl` angeben.

- **no_emitidl**: Typinformationen, die von Typelib importiert werden nicht in der IDL-Datei für das attributierte Projekt generiert vorhanden sein.

## <a name="example"></a>Beispiel

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

## <a name="remarks"></a>Hinweise

**Ende C++-spezifisch**

## <a name="see-also"></a>Siehe auch

[#import-Attribute](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import-Anweisung](../preprocessor/hash-import-directive-cpp.md)