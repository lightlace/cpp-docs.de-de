---
title: Eintrag | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.entry
dev_langs:
- C++
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a40ad39b089ea68209bfef2997f015c355ca6893
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46414042"
---
# <a name="entry"></a>entry

Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.

## <a name="syntax"></a>Syntax

```cpp
[ entry(
   id
) ]
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die ID des Einstiegspunkts.

## <a name="remarks"></a>Hinweise

Die **Eintrag** C++-Attribut hat die gleiche Funktionalität wie die [Eintrag](/windows/desktop/Midl/entry) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Idl_module](../windows/idl-module.md) für ein Beispiel für die Verwendung von **Eintrag**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|`idl_module`-Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  