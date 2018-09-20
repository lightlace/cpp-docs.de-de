---
title: Includelib (C++) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.includelib
dev_langs:
- C++
helpviewer_keywords:
- includelib attribute
ms.assetid: cd90ea6e-5ae8-4f11-b8d1-662db95412b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f15fcefe1a18156e4cbe8180138d7b6c1d944e2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398585"
---
# <a name="includelib-c"></a>includelib (C++)

Bewirkt, dass eine IDL- oder h-Datei, die in der generierten IDL-Datei eingeschlossen werden.

## <a name="syntax"></a>Syntax

```cpp
[ includelib(
   name.idl
) ];
```

### <a name="parameters"></a>Parameter

*Name.idl*<br/>
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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Eigenständige Attribute](../windows/stand-alone-attributes.md)<br/>
[import](../windows/import.md)<br/>
[importidl](../windows/importidl.md)<br/>
[include](../windows/include-cpp.md)<br/>
[importlib](../windows/importlib.md)  