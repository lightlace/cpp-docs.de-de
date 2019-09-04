---
title: section-Pragma
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 47ae2ff2503317e937e2b3a497357afbd5522a64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216603"
---
# <a name="section-pragma"></a>section-Pragma

Erstellt einen Abschnitt in einer OBJ-Datei.

## <a name="syntax"></a>Syntax

> **#pragma Abschnitt (** "*Abschnitts Name*" [ **,** *Attribute* ] **)**

## <a name="remarks"></a>Hinweise

Die Begriffe *Segment* und *Abschnitt* haben dieselbe Bedeutung in diesem Artikel.

Sobald ein Abschnitt definiert wurde, bleibt er für den Rest der Kompilierung gültig. Sie müssen jedoch [__declspec (zuordnen)](../cpp/allocate.md)verwenden, oder es wird nichts in den-Abschnitt eingefügt.

*section-Name* ist ein erforderlicher Parameter, der zum Namen des Abschnitts wird. Der Name darf keinem Standard-Abschnittsnamen ähneln. Eine Liste der Namen, die Sie beim Erstellen eines Abschnitts nicht verwenden sollten, finden Sie unter [/section](../build/reference/section-specify-section-attributes.md) .

*Attribute* ist ein optionaler Parameter, der aus einem oder mehreren durch Trennzeichen getrennten Attributen besteht, die dem Abschnitt zugewiesen werden sollen. Mögliche *Attribute* :

|Attribut|Beschreibung|
|-|-|
|**read**|Ermöglicht Lesevorgänge für Daten.|
|**write**|Ermöglicht Schreibvorgänge für Daten.|
|**execute**|Ermöglicht die Ausführung von Code.|
|**Genu**|Gibt den Abschnitt für alle Prozesse frei, die das Image laden.|
|**nopage**|Markiert den Abschnitt als nicht zuladbar. Nützlich für Win32-Gerätetreiber.|
|**NoCache**|Markiert den Abschnitt als nicht zwischen speicherbar. Nützlich für Win32-Gerätetreiber.|
|**discard**|Markiert den Abschnitt als verworfen. Nützlich für Win32-Gerätetreiber.|
|**remove**|Markiert den Abschnitt als nicht Speicher residente. Nur für virtuelle Gerätetreiber (V*x*D).|

Wenn Sie keine Attribute angeben, enthält der Abschnitt **Lese** -und **Schreib** Attribute.

## <a name="example"></a>Beispiel

In diesem Beispiel identifiziert das erste Abschnitts-Pragma den Abschnitt und seine Attribute. Die Ganzzahl `j` wird nicht in `mysec` eingefügt, da Sie nicht mit `__declspec(allocate)`deklariert wurde. `j` Stattdessen wechselt in den Abschnitt "Data" (Daten). Die Ganzzahl `i` wird aufgrund ihres `mysec`-Speicherklassenattributs in `__declspec(allocate)` eingefügt.

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
