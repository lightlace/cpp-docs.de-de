---
title: section
ms.date: 11/04/2016
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: cd8eee564fa17b21d5421a3471fd676af921f444
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462139"
---
# <a name="section"></a>section

Erstellt einen Abschnitt in einer OBJ-Datei.

## <a name="syntax"></a>Syntax

```
#pragma section( "section-name" [, attributes] )
```

## <a name="remarks"></a>Hinweise

Die Bedeutung der Begriffe *Segment* und *Abschnitt* sind austauschbar, in diesem Thema.

Sobald ein Abschnitt definiert wurde, bleibt er für den Rest der Kompilierung gültig. Sie müssen allerdings verwenden [__declspec(allocate)](../cpp/allocate.md) oder "nothing" im Abschnitt platziert.

*Name des Abschnitts* ist ein erforderlicher Parameter, die den Namen des Abschnitts. Der Name darf keinem Standard-Abschnittsnamen ähneln. Finden Sie unter [/SECTION](../build/reference/section-specify-section-attributes.md) eine Liste der Namen sollten Sie beim Erstellen eines Abschnitts nicht verwenden.

*Attribute* ist ein optionaler Parameter, bestehend aus ein oder mehrere durch Kommas getrennten Attributen, die Sie dem Abschnitt zuweisen möchten. Mögliche *Attribute* sind:

|Attribut|Beschreibung|
|-|-|
|**read**|Ermöglicht Lesevorgänge für Daten.|
|**write**|Ermöglicht Schreibvorgänge für Daten.|
|**execute**|Ermöglicht die Ausführung von Code.|
|**Freigegebene**|Gibt den Abschnitt für alle Prozesse frei, die das Image laden.|
|**nopage**|Markiert den Abschnitt als nicht auslagerbar; nützlich für Win32-Gerätetreiber.|
|**NoCache**|Markiert den Abschnitt als nicht zwischenspeicherbar; nützlich für Win32-Gerätetreiber.|
|**discard**|Markiert den Abschnitt als entfernbar; nützlich für Win32-Gerätetreiber.|
|**remove**|Markiert den Abschnitt als nicht speicherresident; Virtuelle Gerätetreiber (V*x*D) nur.|

Wenn Sie keine Attribute angeben, enthält der Abschnitt Lese- und Schreibattribute.

## <a name="example"></a>Beispiel

Im folgenden Beispiel identifiziert die erste Anweisung den Abschnitt und seine Attribute. Die Ganzzahl `j` wird nicht in `mysec` eingefügt, da sie nicht mit `__declspec(allocate)` deklariert wurde. `j` wird in den Datenbereich eingefügt. Die Ganzzahl `i` wird aufgrund ihres `mysec`-Speicherklassenattributs in `__declspec(allocate)` eingefügt.

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>Siehe auch

[Pragma-Direktiven und das __Pragma-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)