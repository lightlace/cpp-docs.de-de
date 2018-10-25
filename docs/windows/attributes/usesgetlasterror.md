---
title: Usesgetlasterror (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.usesgetlasterror
dev_langs:
- C++
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bb08e2442e34c4d579e568c68d240accdfdbde59
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50074240"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Wird dem Aufrufer mitgeteilt, dass bei wird ein Fehler beim Aufrufen dieser Funktion klicken Sie dann der Aufrufer aufrufen kann `GetLastError` auf den Fehlercode abzurufen.

## <a name="syntax"></a>Syntax

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Hinweise

Die **Usesgetlasterror** C++-Attribut hat die gleiche Funktionalität wie die [Usesgetlasterror](/windows/desktop/Midl/usesgetlasterror) MIDL-Attribut.

## <a name="example"></a>Beispiel

Finden Sie unter den [Idl_module](idl-module.md) Beispiel zur Verwendung **Usesgetlasterror**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Modul** Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)