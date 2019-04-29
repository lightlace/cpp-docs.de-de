---
title: Usesgetlasterror (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: 9f050bbf69edf1ab8327a283299cb5e687ce5380
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407067"
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