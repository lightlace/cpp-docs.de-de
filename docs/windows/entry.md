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
ms.openlocfilehash: 95875eaea7206cbfb4ded271e329f10d7aee13fe
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43221890"
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

*ID*  
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