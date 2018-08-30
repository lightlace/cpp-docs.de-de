---
title: ID | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.id
dev_langs:
- C++
helpviewer_keywords:
- id attribute
ms.assetid: a48d2c99-c5d2-4f46-bf96-5ac88dcb5d0c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9b5250a730b0ce80cbbe9698b4b5e636a85986b6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43223185"
---
# <a name="id"></a>ID

Gibt an, eine *Dispid* Parameter für eine Memberfunktion (eine Eigenschaft oder eine Methode, in eine Schnittstelle oder Disp-Schnittstelle).

## <a name="syntax"></a>Syntax

```cpp
[ id(
   dispid
) ]
```

### <a name="parameters"></a>Parameter

*DISPID*  
Die Dispatch-ID für die Schnittstellenmethode.

## <a name="remarks"></a>Hinweise

Die **Id** C++-Attribut hat die gleiche Funktionalität wie die [Id](/windows/desktop/Midl/id) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](../windows/bindable.md) ein Beispiel zur Verwendung für **Id**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  
[Datenmemberattribute](../windows/data-member-attributes.md)  
[defaultvalue](../windows/defaultvalue.md)  
[in](../windows/in-cpp.md)  
[out](../windows/out-cpp.md)  