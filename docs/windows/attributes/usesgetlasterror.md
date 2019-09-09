---
title: "\"US-GetLastErrorC++ \" (com-Attribut)"
ms.date: 10/02/2018
f1_keywords:
- vc-attr.usesgetlasterror
helpviewer_keywords:
- usesgetlasterror attribute
ms.assetid: d149e33d-35a7-46cb-9137-ae6883d86122
ms.openlocfilehash: b14316bd929f4b41b13a76c41e94b31b7534e9d8
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513890"
---
# <a name="usesgetlasterror"></a>usesgetlasterror

Teilt dem Aufrufer mit, dass der Aufrufer dann aufrufen `GetLastError` kann, um den Fehlercode abzurufen, wenn beim Aufrufen der Funktion ein Fehler auftritt.

## <a name="syntax"></a>Syntax

```cpp
[usesgetlasterror]
```

## <a name="remarks"></a>Hinweise

Das C++ Attribut " [" des](/windows/win32/Midl/usesgetlasterror) Attributs "" ist die gleiche Funktionalität wie das Attribut "" von "" in "".

## <a name="example"></a>Beispiel

Im Beispiel [idl_module](idl-module.md) finden Sie ein Beispiel für die Verwendung von " **" mit "".**

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Module** -Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)