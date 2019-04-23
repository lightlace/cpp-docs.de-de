---
title: Appobject (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.appobject
helpviewer_keywords:
- appobject attribute
ms.assetid: 8ce30b73-e945-403e-a755-6bc78078a695
ms.openlocfilehash: 8219c8fdd1b1df93f92fc6c1d0324a2475d3384b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59034682"
---
# <a name="appobject"></a>appobject

Identifiziert die Co-Klasse als ein Anwendungsobjekt, die mit einer vollständigen .exe-Anwendung verknüpft und gibt an, dass die Funktionen und Eigenschaften der Co-Klasse in diesem global verfügbare [Typbibliothek](../../mfc/automation-clients-using-type-libraries.md).

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
|**Betrifft**|**class**, **struct**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|`coclass`|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)