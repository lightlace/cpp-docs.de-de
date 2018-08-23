---
title: Importidl | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 9bb6c1bd23eaf705f6ceb57e5fc4ea3354c0ddfc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42571357"
---
# <a name="importidl"></a>importidl

Fügt die angegebenen IDL-Datei in der generierten IDL-Datei an.

## <a name="syntax"></a>Syntax

```cpp
[ importidl(
   idl_file
) ];
```

### <a name="parameters"></a>Parameter

*idl_file*  
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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
[import](../windows/import.md)  
[importlib](../windows/importlib.md)  
[include](../windows/include-cpp.md)  
[includelib](../windows/includelib-cpp.md)  