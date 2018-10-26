---
title: Support_error_info (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.support_error_info
dev_langs:
- C++
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b0d86b31823ec31461f953c7cfc16a5774f215fd
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50067162"
---
# <a name="supporterrorinfo"></a>support_error_info

Implementiert die Unterstützung für die Zurückgabe ausführlicher Fehler.

## <a name="syntax"></a>Syntax

```cpp
[ support_error_info(error_interface=uuid) ]
```

### <a name="parameters"></a>Parameter

*error_interface*<br/>
Der Bezeichner der Schnittstelle implementieren `IErrorInfo`.

## <a name="remarks"></a>Hinweise

Das **support_error_info** C++-Attribut implementiert die Unterstützung für die Zurückgabe ausführlicher, kontextbezogener Fehler am Zielobjekt an den Client. Für das Objekt, das Fehler, die Methoden unterstützt die `IErrorInfo` Schnittstelle muss von dem Objekt implementiert werden. Weitere Informationen finden Sie unter [Unterstützung IDispatch und IErrorInfo](../../atl/supporting-idispatch-and-ierrorinfo.md).

Dieses Attribut fügt dem Zielobjekt die [ISupportErrorInfoImpl](../../atl/reference/isupporterrorinfoimpl-class.md) -Klasse als Basisklasse hinzu. Dies führt zu einer standardmäßigen Implementierung von `ISupportErrorInfo` und kann verwendet werden, wenn eine einzelne Schnittstelle Fehler bei einem Objekt generiert.

## <a name="example"></a>Beispiel

Der folgende Code fügt standardmäßig Unterstützung für die `ISupportErrorInfo` Schnittstelle zu den `CMyClass` Objekt.

```cpp
// cpp_attr_ref_support_error_info.cpp
// compile with: /LD
#define _ATL_ATTRIBUTES
#include "atlbase.h"
#include "atlcom.h"

[module (name="mymod")];
[object, uuid("f0b17d66-dc6e-4662-baaf-76758e09c878")]
__interface IMyErrors
{
};

[ coclass, support_error_info("IMyErrors"),
  uuid("854dd392-bdc7-4781-8667-8757936f2a4f") ]
class CMyClass
{
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Klasse**|
|**Wiederholbar**|Ja|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[COM-Attribute](com-attributes.md)<br/>
[Klassenattribute](class-attributes.md)