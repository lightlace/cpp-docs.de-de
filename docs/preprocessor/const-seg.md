---
title: const_seg-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragmas, const_seg
- const_seg pragma
ms.assetid: 1eb58ee2-fb0e-4a39-9621-699c8f5ef957
ms.openlocfilehash: 845583889eb922ba97d145eefe6bca280a83817b
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220432"
---
# <a name="const_seg-pragma"></a>const_seg-Pragma

Gibt den Abschnitt (Segment) an, in dem [Konstanten](../cpp/const-cpp.md) Variablen in der Objektdatei (obj-Datei) gespeichert werden.

## <a name="syntax"></a>Syntax

> **#pragma Const_seg (** ["*section-Name*" [ **,** "*section-Class*"]] **)** \
> **#pragma Const_seg (** { **Push** | **Pop** } [ **,** *Identifier* ] [ **,** "*section-Name*" [ **,** "*section-Class*"]] **)**

### <a name="parameters"></a>Parameter

**Push**\
Optionale Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen.

**Chor**\
Optionale Entfernt einen Datensatz von der obersten Position des internen Compilerstapels. Ein **Pop** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen. Mithilfe des Bezeichners können Sie mehrere Datensätze mithilfe von nur einem **Pop** -Befehl Popups. Der *Abschnitts Name* wird zum aktiven Konstanten Abschnittsnamen nach dem Pop.

*Figur*\
Optionale Bei Verwendung mit **Push**weist dem Datensatz im internen compilerstapel einen Namen zu. Bei Verwendung mit **Pop**werden Datensätze vom internen Stapel, bis der *Bezeichner* entfernt wird, vom internen Stapel angeblendet. Wenn der Bezeichner im internen Stapel nicht gefunden wird, wird nichts weitergeleitet.

"*Abschnitts Name*" \
Optionale Der Name eines Abschnitts. Bei Verwendung mit **Pop**wird der Stapel per Pop und *section-Name* zum aktiven Konstanten Abschnittsnamen.

"*section-Class*" \
Optionale Wird ignoriert, aber ist aus Kompatibilitätsgründen mit C++ früheren Versionen von Microsoft als Version 2,0 enthalten.

## <a name="remarks"></a>Hinweise

Ein *Abschnitt* in einer Objektdatei ist ein benannter Datenblock, der als Einheit in den Arbeitsspeicher geladen wird. Bei einem Konstanten *Abschnitt* handelt es sich um einen Abschnitt, der Konstante Daten enthält. In diesem Artikel haben die Begriffe *Segment* und *Abschnitt* dieselbe Bedeutung.

Die **Const_seg** -pragma-Direktive weist den Compiler an, alle Konstanten Datenelemente aus der Übersetzungseinheit in einen konstanten Abschnitt namens *section-Name*einzufügen. Der Standardabschnitt in der Objektdatei für die **Konstanten** Variablen ist `.rdata`. Einige **Konstanten** Variablen, z. b. skalare, werden automatisch in den Codestream eingebunden. Inline Code wird in `.rdata`nicht angezeigt. Eine **Const_seg** -pragma-Direktive ohne *section-Name-* Parameter setzt den Abschnittsnamen für die nachfolgenden **Konstanten** Daten `.rdata`Elemente auf zurück.

Wenn Sie ein Objekt definieren, das eine dynamische Initialisierung in `const_seg`einem erfordert, ist das Ergebnis nicht definiertes Verhalten.

Eine Liste der Namen, die nicht zum Erstellen eines Abschnitts verwendet werden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md).

Sie können auch Abschnitte für initialisierte Daten ([data_seg](../preprocessor/data-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)) und Funktionen ([code_seg](../preprocessor/code-seg.md)) angeben.

Sie können den [DUMPBIN verwenden. EXE](../build/reference/dumpbin-command-line.md) -Anwendung zum Anzeigen von Objektdateien. Die Versionen von DUMPBIN für jede unterstützte Zielarchitektur sind in Visual Studio enthalten.

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

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
