---
title: HelpContext (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.helpcontext
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
ms.openlocfilehash: 8ec13d785ae491a4082d0bbdc908448cb1b8a49c
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69490913"
---
# <a name="helpcontext"></a>helpcontext

Gibt eine Kontext-ID an, mit der der Benutzerinformationen zu diesem Element in der **Hilfe** Datei anzeigen kann.

## <a name="syntax"></a>Syntax

```cpp
[ helpcontext(id) ]
```

### <a name="parameters"></a>Parameter

*ID*<br/>
Die Kontext-ID des Hilfe Themas. Siehe [HTML-Hilfe: Kontextbezogene Hilfe für Ihre Programme](../../mfc/html-help-context-sensitive-help-for-your-programs.md) , um weitere Informationen zu Kontext-IDs zu finden.

## <a name="remarks"></a>Hinweise

Das **HelpContext** C++ -Attribut verfügt über die gleiche Funktionalität wie das " [HelpContext](/windows/win32/Midl/helpcontext) "-Attribut "Mittel l".

## <a name="example"></a>Beispiel

Ein Beispiel für die Verwendung von **HelpContext**finden Sie im Beispiel für [DefaultValue](defaultvalue.md) .

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **typedef**, **Klasse**, Methode, Eigenschaft|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Schnittstellenattribut](interface-attributes.md)<br/>
[Klassenattribute](class-attributes.md)<br/>
[Methodenattribut](method-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[helpfile](helpfile.md)<br/>
[helpstring](helpstring.md)