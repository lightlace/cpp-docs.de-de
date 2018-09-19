---
title: Usesgetlasterror | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 39052024224b1a78a84b2d9503957b8fff09b96f
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208290"
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

Finden Sie unter den [Idl_module](../windows/idl-module.md) Beispiel zur Verwendung **Usesgetlasterror**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Modul** Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](../windows/idl-attributes.md)  