---
title: Data_seg | Microsoft-Dokumentation
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
dev_langs:
- C++
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eed0e7616515d96c6ccba8cdcb56f963d13bf324
ms.sourcegitcommit: 80fc7b0452aafa36b0c915cbd29c75e1ffa25630
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003545"
---
# <a name="dataseg"></a>data_seg

Gibt das Datensegment an, in dem initialisierte Variablen in der OBJ-Datei gespeichert werden.

## <a name="syntax"></a>Syntax

```
#pragma data_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Parameter

**push**<br/>
(Optional) Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann ein *Bezeichner* und *Segment-Name*.

**pop**<br/>
(Optional) Entfernt einen Datensatz von der obersten Position des internen Compilerstapels.

*identifier*<br/>
(Optional) Bei Verwendung mit **Push**, den Datensatz im internen compilerstapel ein Name zugewiesen. Bei Verwendung mit **pop**, Datensätze vom internen Stapel bis *Bezeichner* wird entfernt; Wenn *Bezeichner* wurde nicht gefunden im internen Stapel, nichts per pop ausgelesen wird.

*Bezeichner* ermöglicht, mehrere Datensätze mit einem einzelnen entfernen **pop** Befehl.

*"Segment-Name"*<br/>
(Optional) Der Name eines Segments. Bei Verwendung mit **pop**, wird das Element im Stapel geholt und *Segment-Name* wird zum aktiven Segmentnamen.

*"Segment-Class"*<br/>
(Optional) Für die Kompatibilität mit C++ vor Version 2.0 enthalten. Wird ignoriert.

## <a name="remarks"></a>Hinweise

Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind austauschbar, in diesem Thema.

OBJ-Dateien können angezeigt werden, mit der [Dumpbin](../build/reference/dumpbin-command-line.md) Anwendung. Das Standardsegment für initialisierte Variablen in der OBJ-Datei ist ".data". Nicht initialisierte Variablen werden als mit Null initialisiert behandelt und in ".bss" gespeichert.

**Data_seg** ohne Parameter setzt das Segment auf ".Data".

## <a name="example"></a>Beispiel

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

Daten, die mit **Data_seg** behält keine Informationen über den Speicherort.

Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.

Sie können auch Abschnitte für const-Variablen angeben ([Const_seg](../preprocessor/const-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)), und Funktionen ([Code_seg](../preprocessor/code-seg.md)).

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
