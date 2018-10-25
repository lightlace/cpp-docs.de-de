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
ms.openlocfilehash: 763ee9c6ad165ad06016a730e218d6aa36777997
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50065121"
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