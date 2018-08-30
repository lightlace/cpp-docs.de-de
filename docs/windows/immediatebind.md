---
title: Immediatebind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.immediatebind
dev_langs:
- C++
helpviewer_keywords:
- immediatebind attribute
ms.assetid: 186d40e6-9166-4d0c-9853-4e7e4d25226f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd546f6d3eb3b2eae60b4bbc8c8fa9b0b4ed00f1
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43201024"
---
# <a name="immediatebind"></a>immediatebind

Gibt an, dass die Datenbank über alle Änderungen an einer Eigenschaft eines datengebundenen Objekts sofort benachrichtigt wird.

## <a name="syntax"></a>Syntax

```cpp
[immediatebind]
```

## <a name="remarks"></a>Hinweise

Die **Immediatebind** C++-Attribut hat die gleiche Funktionalität wie die [Immediatebind](/windows/desktop/Midl/immediatebind) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter [bindbare](../windows/bindable.md) ein Beispiel zur Verwendung für **Immediatebind**.

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
[defaultbind](../windows/defaultbind.md)  
[displaybind](../windows/displaybind.md)  
[requestedit](../windows/requestedit.md)  