---
title: include (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.include
helpviewer_keywords:
- include attribute
ms.assetid: d23f8b91-fe5b-48fa-9371-8bd73af7b8e3
ms.openlocfilehash: ece88ebd7b5d9d81beb871427b58a72b2cf02022
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514550"
---
# <a name="include-c"></a>include (C++)

Gibt eine oder mehrere Header Dateien an, die in die generierte IDL-Datei eingeschlossen werden sollen.

## <a name="syntax"></a>Syntax

```cpp
[ include(header_file) ];
```

### <a name="parameters"></a>Parameter

*header_file*<br/>
Der Name einer Datei, die in die generierte IDL-Datei eingefügt werden soll.

## <a name="remarks"></a>Hinweise

Das **include** C++ -Attribut bewirkt `#include` , dass eine-Anweisung unterhalb `import "docobj.idl"` der-Anweisung in der generierten IDL-Datei platziert wird.

Das **include** C++ -Attribut verfügt über die gleiche Funktionalität wie das [include](/windows/win32/Midl/include) -Attribut "Mittel l".

## <a name="example"></a>Beispiel

Der folgende Code zeigt ein Beispiel für die Verwendung von **include**. In diesem Beispiel enthält die Datei include. h nur eine `#include` -Anweisung.

```cpp
// cpp_attr_ref_include.cpp
// compile with: /LD
[module(name="MyLib")];
[include(cpp_attr_ref_include.h)];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[includelib](includelib-cpp.md)<br/>
[importlib](importlib.md)