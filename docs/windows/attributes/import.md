---
title: Import (C++ com-Attribut)
ms.date: 10/03/2018
f1_keywords:
- vc-attr.import
helpviewer_keywords:
- import attribute
ms.assetid: ebf07cae-39fb-4047-8b57-54af0a9a83de
ms.openlocfilehash: f9ed80bdcc04302c0dee85935f377c8e3dbfd37f
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514624"
---
# <a name="import"></a>import

Gibt eine andere IDL-, ODL-oder Header Datei an, die Definitionen enthält, auf die Sie von Ihrer Haupt-IDL verweisen möchten.

## <a name="syntax"></a>Syntax

```cpp
[ import(
   idl_file
) ];
```

### <a name="parameters"></a>Parameter

*idl_file*<br/>
Der Name einer IDL-Datei, die in die Typbibliothek des aktuellen Projekts importiert werden soll.

## <a name="remarks"></a>Hinweise

Das **Import** C++ -Attribut bewirkt `#import` , dass eine-Anweisung unterhalb `import "docobj.idl"` der-Anweisung in der generierten IDL-Datei platziert wird. Das **Import** -Attribut verfügt über die gleiche Funktionalität wie das [Import](/windows/win32/Midl/import) -Attribut von "Mittel l".

Mit dem **Import** -Attribut wird die angegebene Datei nur in die IDL-Datei eingefügt, die vom Projekt generiert wird. mit dem **Import** -Attribut können Sie Konstrukte in der angegebenen Datei nicht aus dem Quellcode in Ihrem Projekt abrufen.  Verwenden Sie [#import](../../preprocessor/hash-import-directive-cpp.md) und das `embedded_idl`-Attribut, oder fügen Sie die H-Datei für *idl_file* (falls vorhanden) ein, um Konstrukte in der angegebenen Datei über den Quellcode in Ihrem Projekt aufzurufen.

## <a name="example"></a>Beispiel

Der folgende Code

```cpp
// cpp_attr_ref_import.cpp
// compile with: /LD
[module(name="MyLib")];
[import(import.idl)];
```

erzeugt den folgenden Code in der generierten IDL-Datei:

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
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[importidl](importidl.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)