---
title: Eintrag (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.entry
helpviewer_keywords:
- entry attribute
ms.assetid: ba4843e3-d7ad-4b86-9a15-0b4192f0f698
ms.openlocfilehash: 703a55ee7c56b64a5b168016770508508bab09e0
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59036301"
---
# <a name="entry"></a>entry

Gibt eine exportierte Funktion oder Konstante in einem Modul durch identifizieren den Einstiegspunkt in der DLL an.

## <a name="syntax"></a>Syntax

```cpp
[ entry(id) ]
```

### <a name="parameters"></a>Parameter

*id*<br/>
Die ID des Einstiegspunkts.

## <a name="remarks"></a>Hinweise

Die **Eintrag** C++-Attribut hat die gleiche Funktionalität wie die [Eintrag](/windows/desktop/Midl/entry) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Idl_module](idl-module.md) für ein Beispiel für die Verwendung von **Eintrag**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|`idl_module` Attribut|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)