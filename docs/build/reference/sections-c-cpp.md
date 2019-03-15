---
title: SECTIONS (C/C++)
ms.date: 11/04/2016
f1_keywords:
- SECTIONS
helpviewer_keywords:
- SECTIONS .def file statement
ms.assetid: 7b974366-9ef5-4e57-bbcc-73a1df6f8857
ms.openlocfilehash: 5125b09675969c784aafe375faf1fdbc36d8c5d9
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57815111"
---
# <a name="sections-cc"></a>SECTIONS (C/C++)

Stellt einen Abschnitt einer oder mehreren `definitions` Zugriffsspezifizierer für Abschnitte in der Ausgabedatei des Projekts sind.

```
SECTIONS
definitions
```

## <a name="remarks"></a>Hinweise

Jede Definition muss sich in einer separaten Zeile befinden. Die `SECTIONS` Schlüsselwort kann in der gleichen Zeile wie die erste Definition oder in einer vorherigen Zeile sein. Die DEF-Datei kann eine oder mehrere enthalten `SECTIONS` Anweisungen.

Dies `SECTIONS` Anweisung Attribute für einen oder mehrere Abschnitte in der Image-Datei festgelegt und kann verwendet werden, um die Standardattribute für jeden Abschnitt außer Kraft zu setzen.

Das Format für `definitions` ist:

`.section_name specifier`

wo `.section_name` ist der Name eines Abschnitts in Ihr Programmimage und `specifier` kann einen oder mehrere der folgenden Zugriffsmodifizierer:

|Modifizierer|Beschreibung|
|--------------|-----------------|
|`EXECUTE`|Der Abschnitt ist ausführbar.|
|`READ`|Ermöglicht Lesevorgänge für Daten|
|`SHARED`|Teilt den Abschnitt für alle Prozesse, die das Bild zu laden|
|`WRITE`|Ermöglicht Schreibvorgänge für Daten|

Trennen Sie Namen für Bezeichner durch ein Leerzeichen ein. Zum Beispiel:

```
SECTIONS
.rdata READ WRITE
```

`SECTIONS` markiert den Anfang einer Liste von Abschnitt `definitions`. Jede `definition` in einer separaten Zeile befinden muss. Die `SECTIONS` Schlüsselwort kann sein, in der gleichen Zeile wie die erste `definition` oder in einer vorherigen Zeile. Die DEF-Datei kann eine oder mehrere enthalten `SECTIONS` Anweisungen. Die `SEGMENTS` Schlüsselwort wird als Synonym für unterstützt `SECTIONS`.

Ältere Versionen von Visual C++ unterstützt:

```
section [CLASS 'classname'] specifier
```

Die `CLASS` Schlüsselwort wird für die Kompatibilität unterstützt, wird jedoch ignoriert.

Genauso wie Abschnittsattribute ist mit der [/SECTION](section-specify-section-attributes.md) Option.

## <a name="see-also"></a>Siehe auch

[Regeln für Moduldefinitionsanweisungen](rules-for-module-definition-statements.md)
