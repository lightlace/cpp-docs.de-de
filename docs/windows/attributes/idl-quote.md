---
title: Idl_quote (C++-COM-Attribut)
ms.date: 10/02/2018
f1_keywords:
- vc-attr.idl_quote
helpviewer_keywords:
- idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
ms.openlocfilehash: edfeb18053f3ae4fa8c45211833e0ceaa037cf79
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50595571"
---
# <a name="idlquote"></a>idl_quote

Ermöglicht es Ihnen, die IDL-Konstrukte verwenden, die in der aktuellen Version von Visual C++ nicht unterstützt werden, und lassen sie die an der generierten IDL-Datei übergeben.

## <a name="syntax"></a>Syntax

```cpp
[ idl_quote(text) ]
```

### <a name="parameters"></a>Parameter

*Text*<br/>
Der Attributname, die Visual C++-Compiler mit der generierten IDL-Datei übergeben, ohne einen Compilerfehler zurückgegeben werden sollen.

## <a name="remarks"></a>Hinweise

Wenn die **Idl_quote** C++-Attribut dient als eigenständiges Attribut für den (durch ein Semikolon nach der schließenden Klammer), klicken Sie dann *Text* befindet sich in der zusammengeführten IDL-Datei unverändert. Wenn **Idl_quote** wird verwendet, auf ein Symbol, *Text* befindet sich innerhalb des Attributblocks für das Symbol.

## <a name="example"></a>Beispiel

Der folgende Code zeigt, wie Sie ein nicht unterstütztes Attribut angeben können (mit **in**, das unterstützt wird) und das Definieren und verwenden Sie ein nicht definierter IDL-Konstrukt:

```cpp
// cpp_attr_ref_idl_quote.cpp
// compile with: /LD
#include <unknwn.h>
[module(name="MyLibrary")];

[export]
struct MYFLOT {
   int i;
};

[export]
struct MYDUB {
   int i;
};

[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];

typedef struct _S1_TYPE {
   long l1;

union {
   MYFLOT f1; MYDUB d2; } U1_TYPE;
} S1_TYPE;

[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]
__interface IStatic{
   HRESULT Func1([idl_quote("in")] int i);
   HRESULT func( S1_TYPE* myStruct );
};
```

Dieser Code verursacht `MYFLOT` und `MYDUB` und *Text* Eintrag in der generierten IDL-Datei platziert werden. Die *Namen* erzwingt, dass Parameter *Text* , vor allem platziert werden soll, die verweist *Namen* in der generierten IDL-Datei. Die *Abhängigkeiten* Parameter erzwingt, dass die Abhängigkeit Listendefinitionen, bevor Sie platziert werden soll *Text* in der generierten IDL-Datei.

## <a name="requirements"></a>Anforderungen

### <a name="attribute-context"></a>Attributkontext

|||
|-|-|
|**Betrifft**|Überall|
|**Wiederholbar**|Nein|
|**Erforderliche Attribute**|Keiner|
|**Ungültige Attribute**|Keiner|

Weitere Informationen finden Sie unter [Attributkontexte](cpp-attributes-com-net.md#contexts).

## <a name="see-also"></a>Siehe auch

[IDL-Attribute](idl-attributes.md)<br/>
[Eigenständige Attribute](stand-alone-attributes.md)