---
title: bss_seg-Pragma
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: a343fb45b4bbe4789f38b7a1102572cf4241ec53
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218547"
---
# <a name="bss_seg-pragma"></a>bss_seg-Pragma

Gibt den Abschnitt (Segment) an, in dem nicht initialisierte Variablen in der Objektdatei (obj-Datei) gespeichert werden.

## <a name="syntax"></a>Syntax

> **#pragma Bss_seg (** ["*section-Name*" [ **,** "*section-Class*"]] **)** \
> **#pragma Bss_seg (** { **Push** | **Pop** } [ **,** *Identifier* ] [ **,** "*section-Name*" [ **,** "*section-Class*"]] **)**

### <a name="parameters"></a>Parameter

**Push**\
Optionale Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen.

**Chor**\
Optionale Entfernt einen Datensatz von der obersten Position des internen Compilerstapels. Ein **Pop** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen. Mithilfe des Bezeichners können Sie mehrere Datensätze mithilfe von nur einem **Pop** -Befehl Popups. Der *Abschnitts Name* wird nach dem Pop zum aktiven BSS-Abschnittsnamen.

*Figur*\
Optionale Bei Verwendung mit **Push**weist dem Datensatz im internen compilerstapel einen Namen zu. Bei Verwendung mit **Pop**werden Datensätze vom internen Stapel, bis der *Bezeichner* entfernt wird, vom internen Stapel angeblendet. Wenn der Bezeichner im internen Stapel nicht gefunden wird, wird nichts weitergeleitet.

*"section-Name"* \
Optionale Der Name eines Abschnitts. Bei Verwendung mit **Pop**wird der Stapel per Pop und *Abschnitts Name* zum aktiven BSS-Abschnittsnamen.

*"section-Class"* \
Optionale Wird ignoriert, aber ist aus Kompatibilitätsgründen mit C++ früheren Versionen von Microsoft als Version 2,0 enthalten.

## <a name="remarks"></a>Hinweise

Ein *Abschnitt* in einer Objektdatei ist ein benannter Datenblock, der als Einheit in den Arbeitsspeicher geladen wird. Ein *BSS-Abschnitt* ist ein Abschnitt, der nicht initialisierte Daten enthält. In diesem Artikel haben die Begriffe *Segment* und *Abschnitt* dieselbe Bedeutung.

Die **Bss_seg** -pragma-Direktive weist den Compiler an, alle nicht initialisierten Datenelemente aus der Übersetzungseinheit in einen BSS-Abschnitt mit dem Namen " *section-Name*" einzufügen. In einigen Fällen kann die Verwendung von **Bss_seg** Ladezeiten beschleunigen, indem nicht initialisierte Daten zu einem Abschnitt gruppiert werden. Standardmäßig hat der BSS-Abschnitt, der für nicht initialisierte Daten in einer Objektdatei `.bss`verwendet wird, den Namen. Eine **Bss_seg** -pragma-Direktive ohne *section-Name-* Parameter setzt den BSS-Abschnittsnamen für die nachfolgenden nicht initialisierten Datenelemente auf `.bss`zurück.

Mit dem **Bss_seg** -Pragma zugeordnete Daten behalten keine Informationen über ihren Speicherort bei.

Eine Liste der Namen, die nicht zum Erstellen eines Abschnitts verwendet werden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md).

Sie können auch Abschnitte für initialisierte Daten ([data_seg](../preprocessor/data-seg.md)), Functions ([code_seg](../preprocessor/code-seg.md)) und Konstanten Variablen ([Const_seg](../preprocessor/const-seg.md)) angeben.

Sie können den [DUMPBIN verwenden. EXE](../build/reference/dumpbin-command-line.md) -Anwendung zum Anzeigen von Objektdateien. Die Versionen von DUMPBIN für jede unterstützte Zielarchitektur sind in Visual Studio enthalten.

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
