---
title: Appobject | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.appobject
dev_langs:
- C++
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fafdb99296e19318f183b6c0893d9b4e91f0cd7b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46422635"
---
# <a name="appobject"></a>appobject

Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen .exe-Anwendung verknüpft und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diesem global verfügbare [Typbibliothek](../mfc/automation-clients-using-type-libraries.md).

## <a name="syntax"></a>Syntax

```cpp
[appobject]
```

## <a name="remarks"></a>Hinweise

Die **Appobject** C++-Attribut hat die gleiche Funktionalität wie die [Appobject](/windows/desktop/Midl/appobject) MIDL-Attribut.

## <a name="example"></a>Beispiel

Der folgende Code zeigt eine einfache Klassendefinition vorangestellt wird ein Attributblock, die enthält **Appobject**:

```cpp
// cpp_attr_ref_appobject.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib", uuid="f1ce17f0-a5df-4d26-95f6-0a122197ac5b")];

[object, uuid="905de6db-7a12-45ab-9f8b-b39f5112f010"]
__interface ICustom {};

[coclass, appobject,uuid="00395340-745f-4b69-bd58-e2921452b9fc"]
class A : public ICustom {
   int i;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`coclass`|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)<br/>
[Klassenattribute](../windows/class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  