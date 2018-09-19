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
ms.openlocfilehash: d5da3f03500ccaadb4cff3be0226592e36ed3160
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43200888"
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

Weitere Informationen finden Sie unter [Attributkontexte](../windows/attribute-contexts.md).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](../windows/compiler-attributes.md)  
[typedef-, enum-, union- und struct-Attribute](../windows/typedef-enum-union-and-struct-attributes.md)  