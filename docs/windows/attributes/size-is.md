---
title: size_is (C++ com-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.size_is
helpviewer_keywords:
- size_is attribute
ms.assetid: 70192d09-f6c5-4d52-b3fe-303f8cb10aa5
ms.openlocfilehash: 504f1bf72b8ffa15e8df50bb00c86ef909688f1e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69514039"
---
# <a name="size_is"></a>size_is

Geben Sie die Größe des zugeordneten Arbeitsspeichers für Größen Zeiger, große Zeiger auf Größen Zeiger und einzelne oder mehrdimensionale Arrays an.

## <a name="syntax"></a>Syntax

```cpp
[ size_is("expression") ]
```

### <a name="parameters"></a>Parameter

*expression*<br/>
Die Größe des zugeordneten Arbeitsspeichers für Größen Zeiger.

## <a name="remarks"></a>Hinweise

Das **size_is** C++ -Attribut verfügt über die gleiche Funktionalität wie das [size_is](/windows/win32/Midl/size-is) -Mittell-Attribut.

## <a name="example"></a>Beispiel

Im Beispiel für [First_is](first-is.md) finden Sie ein Beispiel für die Angabe eines Abschnitts eines Arrays.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Feld in **Struktur** oder **Union**, Schnittstellenparameter, Schnittstellen Methode|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|None|
|**Ungültige Attribute**|`max_is`|

Weitere Informationen zu den Attributkontexten finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[typedef-, enum-, union- und struct-Attribute](typedef-enum-union-and-struct-attributes.md)<br/>
[Parameterattribute](parameter-attributes.md)<br/>
[first_is](first-is.md)<br/>
[last_is](last-is.md)<br/>
[max_is](max-is.md)<br/>
[length_is](length-is.md)