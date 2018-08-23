---
title: Exportieren Sie | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: e696b3c141a83882af67e72039c164a0f917d446
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611199"
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

Die Typdefinitionen für den Export gültig sind, Basistypen, Strukturen, Unions, Enumerationen, oder geben Bezeichner.  Finden Sie unter [Typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) für Weitere Informationen.

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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  