---
title: LCID (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.lcid
helpviewer_keywords:
- LCID attribute
ms.assetid: 7f248c69-ee1c-42c3-9411-39cf27c9f43d
ms.openlocfilehash: d97ad86e143102c96e87ae0a32245b0c01042501
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59032427"
---
# <a name="lcid"></a>lcid

Sie können einen Gebietsschemabezeichner an eine Funktion übergeben.

## <a name="syntax"></a>Syntax

```cpp
[lcid]
```

## <a name="remarks"></a>Hinweise

Die **Lcid** C++-Attribut implementiert die Funktionalität der [Lcid](/windows/desktop/Midl/lcid) MIDL-Attribut. Wenn Sie das Gebietsschema für ein bibliotheksblock implementieren möchten, verwenden Sie die **Lcid =** `lcid` Parameter, um die [Modul](module-cpp.md) Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_lcid.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];
typedef long HRESULT;

[dual, uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA")]
__interface IStatic {
   HRESULT MyFunc([in, lcid] long LocaleID, [out, retval] BSTR * ReturnVal);
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenparameter|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)