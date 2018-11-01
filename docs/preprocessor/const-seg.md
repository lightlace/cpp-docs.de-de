---
title: const_seg
ms.date: 09/17/2018
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: ce932b068f5751b7cf1ceab969312defd18336f7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648343"
---
# <a name="constseg"></a>const_seg
Gibt das Segment, in denen [const](../cpp/const-cpp.md) Variablen werden in der OBJ-Datei gespeichert.

## <a name="syntax"></a>Syntax

```
#pragma const_seg ( [ [ { push | pop}, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Parameter

**push**<br/>
(Optional) Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann ein *Bezeichner* und *Segment-Name*.

**pop**<br/>
(Optional) Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.

*identifier*<br/>
(Optional) Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, nichts per pop ausgelesen wird.

Mithilfe von *Bezeichner* ermöglicht, mehrere Datensätze mit einem einzelnen entfernen **pop** Befehl.

"*Segment-Name*"<br/>
(Optional) Der Name eines Segments. Bei Verwendung mit **pop**, wird das Element im Stapel geholt und *Segment-Name* wird zum aktiven Segmentnamen.

"*Segmentklasse*"<br/>
(Optional) Für die Kompatibilität mit C++ vor Version 2.0 enthalten. Wird ignoriert.

## <a name="remarks"></a>Hinweise

Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind austauschbar, in diesem Thema.

OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment in der OBJ-Datei für `const`-Variablen ist .rdata. Einige `const`-Variablen, z. B. Skalare, sind automatisch im Codestream enthalten. Inlinecode erscheint nicht in .rdata.

Das Definieren eines Objekts, das eine dynamische Initialisierung in einem `const_seg` benötigt, führt zu einem nicht definierten Verhalten.

`#pragma const_seg` ohne Parameter setzt das Segment auf .rdata zurück.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="comments"></a>Kommentare

Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.

Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und Funktionen ([Code_seg](../preprocessor/code-seg.md)).

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)