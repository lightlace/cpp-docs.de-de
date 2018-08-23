---
title: Retval | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.retval
dev_langs:
- C++
helpviewer_keywords:
- retval attribute
ms.assetid: bfa16f08-157d-4eea-afde-1232c54b8501
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d29d619f8e561f1c506b69ffd132c46276026e13
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604589"
---
# <a name="retval"></a>retval

Legt fest, den Parameter, der den Rückgabewert des Members empfängt.

## <a name="syntax"></a>Syntax

```cpp
[retval]
```

## <a name="remarks"></a>Hinweise

Die **Retval** C++-Attribut hat die gleiche Funktionalität wie die [Retval](http://msdn.microsoft.com/library/windows/desktop/aa367158) MIDL-Attribut.

**Retval** muss für das letzte Argument in einer Funktion Deklaration angezeigt werden.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [bindbare](../windows/bindable.md) für ein Beispiel für die Verwendung von **Retval**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Parameter, für die Schnittstellenmethode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|**out**|
|**Ungültige Attribute**|**in**|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  
[Parameterattribute](../windows/parameter-attributes.md)  
[Methodenattribut](../windows/method-attributes.md)  