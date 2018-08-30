---
title: Helpstring | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpstring
dev_langs:
- C++
helpviewer_keywords:
- helpstring attribute [C++]
ms.assetid: 0401e905-a63e-4fad-98d0-d1efea111966
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae2d5121e17a9325ec45143e7e90e7d2a211f380
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223097"
---
# <a name="helpstring"></a>helpstring

Gibt eine Zeichenfolge an, die zum Beschreiben des Elements verwendet wird, auf das sie angewendet wird.

## <a name="syntax"></a>Syntax

```cpp
[ helpstring(
   "string"
) ]
```

### <a name="parameters"></a>Parameter

*string*  
Der Text des Hilfe-Zeichenfolge.

## <a name="remarks"></a>Hinweise

Die **Helpstring** C++-Attribut hat die gleiche Funktionalität wie die [Helpstring](/windows/desktop/Midl/helpstring) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](../windows/defaultvalue.md) ein Beispiel zur Verwendung für **Helpstring**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode, Eigenschaft|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Schnittstellenattribut](../windows/interface-attributes.md)  
[Klassenattribute](../windows/class-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  
[helpfile](../windows/helpfile.md)  
[helpcontext](../windows/helpcontext.md)  