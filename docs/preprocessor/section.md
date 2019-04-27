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
ms.openlocfilehash: 41479d7d8767438d0e59fbe6beb7e435459dcb1b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62179632"
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
|**shared**|Gibt den Abschnitt für alle Prozesse frei, die das Image laden.|
|**nopage**|Markiert den Abschnitt als nicht auslagerbar; nützlich für Win32-Gerätetreiber.|
|**nocache**|Markiert den Abschnitt als nicht zwischenspeicherbar; nützlich für Win32-Gerätetreiber.|
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