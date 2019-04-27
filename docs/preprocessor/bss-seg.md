---
title: bss_seg
ms.date: 10/22/2018
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: 489ced11bb6024fdf9818872c07ab7feebfeabf3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62212412"
---
# <a name="bssseg"></a>bss_seg

Gibt das Segment an, in dem nicht initialisierte Variablen in der OBJ-Datei gespeichert werden.

## <a name="syntax"></a>Syntax

```
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Parameter

**push**<br/>
(Optional) Legt einen Datensatz auf dem internen compilerstapel ab. Ein *Pu*sh * kann ein *Bezeichner* und *Segment-Name*.

**pop**<br/>
(Optional) Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.

*identifier*<br/>
(Optional) Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. *Bezeichner* ermöglicht, mehrere Datensätze mit einem einzelnen entfernen **pop** Befehl. Bei Verwendung mit **pop**, die Richtlinie wird Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, ist "nothing" per POP entfernt.

*"Segment-Name"*<br/>
(Optional) Der Name eines Segments. Bei Verwendung mit **pop**, wird das Element im Stapel geholt und *Segment-Name* wird zum aktiven Segmentnamen.

*"segment-class"*<br/>
(Optional) Für die Kompatibilität mit C++ vor Version 2.0 enthalten. Wird ignoriert.

## <a name="remarks"></a>Hinweise

. OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment für nicht initialisierte Variablen in der OBJ-Datei ist ".bss". In einigen Fällen zu verwenden, der **Bss_seg** können Ladezeiten, indem nicht initialisierte Daten in einen Abschnitt gruppiert.

**Bss_seg** ohne Parameter setzt das Segment auf ".BSS".

Daten, die mit der **Bss_seg** Pragma behält keine Informationen über den Speicherort.

Sie können auch Abschnitte für initialisierte Daten angeben ([Data_seg](../preprocessor/data-seg.md)), Funktionen ([Code_seg](../preprocessor/code-seg.md)), und const-Variablen ([Const_seg](../preprocessor/const-seg.md)).

Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
