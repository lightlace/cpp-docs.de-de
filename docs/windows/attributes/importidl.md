---
title: Importidl (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.importidl
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
ms.openlocfilehash: 8d0d891f74da8df2351b0a861fb7501e72f5e2de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587169"
---
# <a name="importidl"></a>importidl

Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ importidl(idl_file) ];
```

### <a name="parameters"></a>Parameter

*idl_file*<br/>
Identifiziert den Namen der IDL-Datei, die mit der IDL-Datei, die generiert wird, und für Ihre Anwendung zusammengeführt werden sollen.

## <a name="remarks"></a>Hinweise

Die **Importidl** C++-Attribut wird im Abschnitt außerhalb des bibliotheksblocks (in *Idl_file*) in der generierten IDL-Datei des Programms und die Bibliothekabschnitt (in *Idl_file*) in die Bibliothek Teil Ihres Programms IDL-Datei generiert.

Sie verwenden möchten **Importidl**, z. B. Wenn Sie eine handcodierten IDL-Datei mit der generierten IDL-Datei verwenden möchten.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_importidl.cpp
// compile with: /LD
[module(name="MyLib")];
[importidl("import.idl")];
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

[Compilerattribute](compiler-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)<br/>
[import](import.md)<br/>
[importlib](importlib.md)<br/>
[include](include-cpp.md)<br/>
[includelib](includelib-cpp.md)