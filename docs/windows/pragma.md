---
title: Pragmas | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.pragma
dev_langs:
- C++
helpviewer_keywords:
- pragma attribute
ms.assetid: 3f90d023-b8b5-4007-8311-008bb72cbea1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f8ff470af7b7c825fb1c1dc7bf118e969a4b992
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603052"
---
# <a name="pragma"></a>pragma

Gibt die angegebene Zeichenfolge in der generierten IDL-Datei ohne die Verwendung von Anführungszeichen.

## <a name="syntax"></a>Syntax

```cpp
[ pragma(
   pragma_statement
) ];
```

### <a name="parameters"></a>Parameter

*pragma_statement*  
Das Pragma, das in der generierten IDL-Datei aufgenommen werden sollen.

## <a name="remarks"></a>Hinweise

Die **Pragma** C++-Attribut hat die gleiche Funktionalität wie die [Pragma](http://msdn.microsoft.com/library/windows/desktop/aa367143) MIDL-Attribut.

## <a name="example"></a>Beispiel

```cpp
// cpp_attr_ref_pragma.cpp
// compile with: /LD
#include "unknwn.h"
[module(name="MyLib")];
[pragma(pack(4))];

[dispinterface, uuid("00000000-0000-0000-0000-000000000001")]
__interface A
{
   [id(1)] HRESULT MyMethod ([in, satype("BSTR")] SAFEARRAY **p);
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

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Eigenständige Attribute](../windows/stand-alone-attributes.md)  
[pack](../preprocessor/pack.md)  