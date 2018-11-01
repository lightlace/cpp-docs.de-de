---
title: Das Embedded_idl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- embedded_idl
dev_langs:
- C++
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7337595111b01ceeec53cc97f11ec2f35a081c5
ms.sourcegitcommit: 0164af5615389ffb1452ccc432eb55f6dc931047
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2018
ms.locfileid: "49808341"
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

- **Emitidl**: Typinformationen, die von Typelib importiert werden in der IDL-Datei für das attributierte Projekt generiert vorhanden sein.  Dies ist die Standardeinstellung, die aktiv ist, wenn Sie keinen Parameter für `embedded_idl` angeben.

- **No_emitidl**: Typinformationen, die von Typelib importiert werden nicht in der IDL-Datei für das attributierte Projekt generiert vorhanden sein.

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