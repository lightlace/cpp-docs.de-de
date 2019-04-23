---
title: Includelib (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.includelib
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
ms.openlocfilehash: 57f039eeae527dd03884b12e7d9eb424d87f597f
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029999"
---
# <a name="includelib-c"></a>includelib (C++)

Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.

## <a name="syntax"></a>Syntax

```cpp
[ includelib(name.idl) ];
```

### <a name="parameters"></a>Parameter

*name.idl*<br/>
Der Name der IDL-Datei, die als Teil der generierten IDL-Datei enthalten sein sollen.

## <a name="remarks"></a>Hinweise

Die **Includelib** C++-Attribut bewirkt, dass eine IDL- oder h-Datei in der generierten IDL-Datei eingeschlossen werden, nach der `importlib` Anweisung.

## <a name="example"></a>Beispiel

Der folgende Code wird in einer CPP-Datei dargestellt:

```cpp
// cpp_attr_ref_includelib.cpp
// compile with: /LD
[module(name="MyLib")];
[includelib("includelib.idl")];
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importidl](importidl.md)<br/>
[include](include-cpp.md)<br/>
[importlib](importlib.md)