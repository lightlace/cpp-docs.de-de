---
title: HelpContext (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 921e5370303cb62830ec281bcefd7c03331efaeb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552749"
---
# <a name="helpcontext"></a>helpcontext

Gibt eine Kontext-ID, mit dem die Benutzerinformationen zu diesem Element in der **Hilfe** Datei.

## <a name="syntax"></a>Syntax

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Kontext-ID des Hilfethemas. Finden Sie unter [HTML-Hilfe: kontextbezogene Hilfe für Programme](../../mfc/html-help-context-sensitive-help-for-your-programs.md) Weitere Informationen zum Kontext-IDs.

## <a name="remarks"></a>Hinweise

Die **Helpcontext** C++-Attribut hat die gleiche Funktionalität wie die [Helpcontext](/windows/desktop/Midl/helpcontext) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Defaultvalue](defaultvalue.md) ein Beispiel zur Verwendung für **Helpcontext**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode, Eigenschaft|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)