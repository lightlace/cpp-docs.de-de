---
title: HelpContext (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpcontext
dev_langs:
- C++
helpviewer_keywords:
- helpcontext attribute
ms.assetid: 6fbb022d-a4b7-4989-a02f-7f18a9b0ad96
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bd3278ee31cf27dd6cd422e247c1d0911bc3bf5a
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48790583"
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