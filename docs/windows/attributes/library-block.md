---
title: Library_block (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.library_block
dev_langs:
- C++
helpviewer_keywords:
- library_block attribute
ms.assetid: ae7a7ebe-5e1a-4eda-a058-11bbd058ece8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf4bcdd9290817bb77eeb20f1a014bd537d15d8b
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791718"
---
# <a name="libraryblock"></a>library_block

Fügt ein Konstrukt in den bibliotheksblock IDL.

## <a name="syntax"></a>Syntax

```cpp
[library_block]
```

## <a name="remarks"></a>Hinweise

Wenn Sie ein Konstrukt in den bibliotheksblock platzieren, stellen Sie sicher, dass er übergeben wird in der Typbibliothek, unabhängig davon, ob die Funktion verwiesen wird. Standardmäßig nur Konstrukte geändert, indem die [Co-Klasse](coclass.md), [Dispinterface](dispinterface.md), und [Idl_module](idl-module.md) Attribute in den bibliotheksblock platziert werden.

## <a name="example"></a>Beispiel

Im folgenden Code wird eine benutzerdefinierte Schnittstelle in den bibliotheksblock platziert.

```cpp
// cpp_attr_ref_library_block.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib")];
[object, library_block, uuid("9E66A290-4365-11D2-A997-00C04FA37DDB")]
__interface IMyInterface {
   HRESULT f1();
};
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
[Eigenständige Attribute](stand-alone-attributes.md)  