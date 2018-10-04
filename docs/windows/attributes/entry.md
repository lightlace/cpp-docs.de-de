---
title: Eintrag (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
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
ms.openlocfilehash: 95eb37898d4934740e1520df758ed33d3dd4c79a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791244"
---
# <a name="entry"></a>entry

Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.

## <a name="syntax"></a>Syntax

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die ID des Einstiegspunkts.

## <a name="remarks"></a>Hinweise

Die **Eintrag** C++-Attribut hat die gleiche Funktionalität wie die [Eintrag](/windows/desktop/Midl/entry) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Idl_module](idl-module.md) für ein Beispiel für die Verwendung von **Eintrag**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|`idl_module`-Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)  