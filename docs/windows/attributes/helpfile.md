---
title: HelpFile-(C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.helpfile
dev_langs:
- C++
helpviewer_keywords:
- helpfile attribute
ms.assetid: d75161c1-1363-4019-ae09-e7e3b8a3971e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9a498cefce01d5a22df5211d0f7bb2f64e3a7b79
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48792091"
---
# <a name="helpfile"></a>helpfile

Legt den Namen der Hilfedatei für die Typbibliothek.

## <a name="syntax"></a>Syntax

```cpp
[ helpfile("filename") ]
```

### <a name="parameters"></a>Parameter

*filename*<br/>
Der Name der Datei, die die Hilfethemen enthält.

## <a name="remarks"></a>Hinweise

Die **Helpfile** C++-Attribut hat die gleiche Funktionalität wie die [Helpfile](/windows/desktop/Midl/helpfile) MIDL-Attribut.

## <a name="example"></a>Beispiel

Siehe das Beispiel für [Modul](module-cpp.md) ein Beispiel zur Verwendung für **Helpfile**.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Schnittstelle**, **Typedef**, **Klasse**, Methode **Eigenschaft**|
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
[helpcontext](helpcontext.md)<br/>
[helpstring](helpstring.md)  