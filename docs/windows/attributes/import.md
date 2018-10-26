---
title: Importieren (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.import
dev_langs:
- C++
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 046a6eb0d1033efb44dd9f34806e747e1fafd700
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071114"
---
# <a name="import"></a>import

Gibt eine andere IDL, Header oder ODL-Datei enthält Definitionen, die Sie von Ihrem wichtigsten IDL verweisen möchten.

## <a name="syntax"></a>Syntax

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Parameter

*idl_file*<br/>
Der Name einer IDL-Datei, die in der Typbibliothek des aktuellen Projekts importiert werden sollen.

## <a name="remarks"></a>Hinweise

Die **importieren** C++-Attribut bewirkt, dass ein `#import` Anweisung unten platziert werden die `import "docobj.idl"` -Anweisung in der generierten IDL-Datei. Die **importieren** Attribut hat die gleiche Funktionalität wie die [importieren](/windows/desktop/Midl/import) MIDL-Attribut.

Die **importieren** Attribut wird nur die angegebene Datei in der IDL-Datei, die von Ihrem Projekt generiert wird die **importieren** Attribut ist nicht möglich, die Konstrukte in der angegebenen Datei aus dem Quellcode aufrufen in Ihrem Projekt.  Um Konstrukte in der angegebenen Datei aus dem Quellcode in Ihrem Projekt aufzurufen, verwenden Sie entweder [#import](../../preprocessor/hash-import-directive-cpp.md) und `embedded_idl` -Attribut, oder Sie können die h-Datei für enthalten die *Idl_file*, wenn eine .h-Datei vorhanden ist.

## <a name="example"></a>Beispiel

Der folgende Code

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

Der folgende Code in der generierten IDL-Datei generiert:

```
import "docobj.idl";
import "import.idl";

[ uuid(EED3644C-8488-3ECD-BA97-147DB3CDB499), version(1.0) ]
library MyLib {
   importlib("stdole2.tlb");
   importlib("olepro32.dll");
...
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)