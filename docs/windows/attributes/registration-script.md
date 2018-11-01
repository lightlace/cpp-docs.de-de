---
title: Registration_script (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.registration_script
dev_langs:
- C++
helpviewer_keywords:
- registration_script attribute
ms.assetid: 786f8072-9187-4163-a979-7a604dd4c888
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 78d108dfda75147e4147e94544ddddcdfa04481d
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50062859"
---
# <a name="registrationscript"></a>registration_script

Führt den angegebenen benutzerdefinierten Registrierung-Skript aus.

## <a name="syntax"></a>Syntax

```cpp
[ registration_script(script) ]
```

### <a name="parameters"></a>Parameter

*Skript*<br/>
Der vollständige Pfad zu einer benutzerdefinierten Registrierungsskriptdatei (.rgs). Der Wert **keine**, z. B. `script = "none"`, gibt an, dass die Co-Klasse keine Anforderungen an die Registrierung.

## <a name="remarks"></a>Hinweise

Die **Registration_script** C++-Attribut führt die benutzerdefinierte Registrierungsskript gemäß *Skript*. Wenn dieses Attribut nicht angegeben ist, wird eine standard-RGS-Datei, die (mit Informationen zum Registrieren der Komponente) verwendet. Weitere Informationen zu RGS-Dateien finden Sie unter [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).

Dieses Attribut erfordert, dass die Attribute [coclass](coclass.md), [progid](progid.md), oder [vi_progid](vi-progid.md) (oder ein anderes Attribut, das eines der genannten impliziert) auch auf demselben Element angewendet werden.

## <a name="example"></a>Beispiel

Der folgende Code gibt an, dass die Komponente eine Registrierungsdatei cpp_attr_ref_registration_script.rgs aufgerufen hat.

```cpp
// cpp_attr_ref_registration_script.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="REG")];

[object, uuid("d9cd196b-6836-470b-9b9b-5b04b828e5b0")]
__interface IFace {};

// requires "cpp_attr_ref_registration_script.rgs"
// create sample .RGS file "cpp_attr_ref_registration_script.rgs" if it does not exist
[ coclass, registration_script(script="cpp_attr_ref_registration_script.rgs"),
  uuid("50d3ad42-3601-4f26-8cfe-0f1f26f98f67")]
class CMyClass:public IFace {};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**, **Struktur**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Eine oder mehrere der folgenden: `coclass`, `progid`, oder `vi_progid`.|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[rdx](rdx.md)