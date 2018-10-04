---
title: Importidl (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.importidl
dev_langs:
- C++
helpviewer_keywords:
- importidl attribute
ms.assetid: 4b0a4b55-6c57-4e6e-bc7b-a12cc8063941
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d1c022a48ef5510f67355af3af1ff0a0e98ad4c4
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791310"
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