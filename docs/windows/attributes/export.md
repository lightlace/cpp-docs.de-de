---
title: Exportieren (C++-COM-Attribut) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/02/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a636b7d4c943896bcd1e5e7b3580c2d3f7410fc8
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48791194"
---
# <a name="export"></a>"export"

Bewirkt, dass eine Datenstruktur, in der IDL-Datei platziert wird.

## <a name="syntax"></a>Syntax

```cpp
[export]
```

## <a name="remarks"></a>Hinweise

Die **exportieren** C++-Attribut bewirkt, dass eine Datenstruktur, die in der IDL-Datei platziert werden und dann in der Typbibliothek in eine Binärdatei-kompatiblen Format zur Verfügung, die sie für die Verwendung mit einer beliebigen Sprache zur Verfügung stellt.

Können nicht angewendet werden die **exportieren** -Attribut auf eine Klasse, auch wenn die Klasse nur öffentliche Member hat (das Äquivalent einer **Struktur**).

Wenn Sie eine nicht benannte exportieren **Enum** oder **Struktur**, erhält sie einen Namen, die mit beginnt **__unnamed**<em>x</em>, wobei *x* ist eine sequenzielle Zahl.

Die Typdefinitionen für den Export gültig sind, Basistypen, Strukturen, Unions, Enumerationen, oder geben Bezeichner.  Finden Sie unter [Typedef](/windows/desktop/Midl/typedef) für Weitere Informationen.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie mit der **exportieren** Attribut:

```cpp
// cpp_attr_ref_export.cpp
// compile with: /LD
[module(name="MyLibrary")];

[export]
struct MyStruct {
   int i;
};
```

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|**Union**, **Typedef**, **Enum**, **Struktur**, oder **Schnittstelle**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)  