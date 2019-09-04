---
title: data_seg-Pragma
ms.date: 08/29/2019
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: f67a9f39695adf5067c61288cf09ea7eb481c7dd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220381"
---
# <a name="data_seg-pragma"></a>data_seg-Pragma

Gibt den Daten Abschnitt (Segment) an, in dem initialisierte Variablen in der Objektdatei (obj-Datei) gespeichert werden.

## <a name="syntax"></a>Syntax

> **#pragma data_seg (** ["*section-Name*" [ **,** "*section-Class*"]] **)** \
> **#pragma data_seg (** { **Push** | **Pop** } [ **,** *Identifier* ] [ **,** "*section-Name*" [ **,** "*section-Class*"]] **)**

### <a name="parameters"></a>Parameter

**Push**\
Optionale Legt einen Datensatz auf dem internen compilerstapel ab. Ein **Push** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen.

**Chor**\
Optionale Entfernt einen Datensatz von der obersten Position des internen Compilerstapels. Ein **Pop** kann einen *Bezeichner* und einen *Abschnittsnamen*aufweisen. Mithilfe des Bezeichners können Sie mehrere Datensätze mithilfe von nur einem **Pop** -Befehl Popups. Der *Abschnitts Name* wird zum Namen des aktiven Daten Abschnitts nach dem Pop.

*Figur*\
Optionale Bei Verwendung mit **Push**weist dem Datensatz im internen compilerstapel einen Namen zu. Bei Verwendung mit **Pop**werden Datensätze vom internen Stapel bis zum Entfernen des Bezeichners angezeigt. Wenn der Bezeichner im internen Stapel nicht gefunden wird, wird nichts weitergeleitet.

der Bezeichner ermöglicht das popten mehrerer Datensätze mit einem einzelnen **Pop** -Befehl.

*"section-Name"* \
Optionale Der Name eines Abschnitts. Bei Verwendung mit **Pop**wird der Stapel per Pop und *Abschnitts Name* zum aktiven Daten Abschnittsnamen.

*"section-Class"* \
Optionale Wird ignoriert, aber ist aus Kompatibilitätsgründen mit C++ früheren Versionen von Microsoft als Version 2,0 enthalten.

## <a name="remarks"></a>Hinweise

Ein *Abschnitt* in einer Objektdatei ist ein benannter Datenblock, der als Einheit in den Arbeitsspeicher geladen wird. Ein *Daten Abschnitt* ist ein Abschnitt, der initialisierte Daten enthält. In diesem Artikel haben die Begriffe *Segment* und *Abschnitt* dieselbe Bedeutung.

Der Standardabschnitt in der obj-Datei für initialisierte Variablen ist `.data`. Nicht initialisierte Variablen werden als initialisiert mit 0 (null) betrachtet und in `.bss`gespeichert.

Die **data_seg** -pragma-Direktive weist den Compiler an, alle initialisierten Datenelemente aus der Übersetzungseinheit in einen Daten Abschnitt namens *section-Name*einzufügen. Standardmäßig wird der Daten Abschnitt, der für initialisierte Daten in einer Objektdatei verwendet `.data`wird, benannt. Nicht initialisierte Variablen werden als mit NULL initialisiert betrachtet und in `.bss`gespeichert. Eine **data_seg** -pragma-Direktive ohne *section-Name-* Parameter setzt den Namen des Daten Abschnitts für die nachfolgenden initialisierten Datenelemente auf `.data`zurück.

Mit **data_seg** zugeordnete Daten behalten keine Informationen über ihren Speicherort bei.

Eine Liste der Namen, die nicht zum Erstellen eines Abschnitts verwendet werden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md).

Sie können auch Abschnitte für Konstanten Variablen ([Const_seg](../preprocessor/const-seg.md)), nicht initialisierte Daten ([Bss_seg](../preprocessor/bss-seg.md)) und Funktionen ([code_seg](../preprocessor/code-seg.md)) angeben.

Sie können den [DUMPBIN verwenden. EXE](../build/reference/dumpbin-command-line.md) -Anwendung zum Anzeigen von Objektdateien. Die Versionen von DUMPBIN für jede unterstützte Zielarchitektur sind in Visual Studio enthalten.

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

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
