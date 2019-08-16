---
title: Export (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.export
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
ms.openlocfilehash: 771bfdfe4eab2acf31e97a606795066e8938a8a1
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69501608"
---
# <a name="export"></a>"export"

Bewirkt, dass eine Datenstruktur in der IDL-Datei platziert wird.

## <a name="syntax"></a>Syntax

```cpp
[export]
```

## <a name="remarks"></a>Hinweise

Das **Export** C++ -Attribut bewirkt, dass eine Datenstruktur in der IDL-Datei platziert und dann in der Typbibliothek in einem Binär kompatiblen Format verfügbar ist, das Sie für die Verwendung in einer beliebigen Sprache verfügbar macht.

Das **Export** Attribut kann nicht auf eine Klasse angewendet werden, auch wenn die Klasse nur öffentliche Member hat (entspricht einer **Struktur**).

Wenn Sie eine unbenannte Enumeration oder **Struktur**exportieren, erhält Sie einen Namen, der mit **__unnamed**<em>x</em>beginnt, wobei *x* eine sequenzielle Zahl ist.

Die für den Export gültigen Typedefs sind Basis Typen, Strukturen, Unions, Enumerationstypen oder Typbezeichner.  Weitere Informationen finden Sie unter [typedef](/windows/win32/Midl/typedef) .

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie das **Export** -Attribut verwendet wird:

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
|**Betrifft**|**Union**, **typedef**,Aufzählung, **Struktur**oder **Schnittstelle**|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|None|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[Compilerattribute](compiler-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)