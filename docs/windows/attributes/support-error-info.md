---
title: Support_error_info (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.support_error_info
helpviewer_keywords:
- support_error_info attribute
ms.assetid: 20a2b55c-4738-4b35-a71d-e5e9c3a7e3bc
ms.openlocfilehash: c05b6735c5c29e44f3cc190a150a5efe02025519
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59023762"
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