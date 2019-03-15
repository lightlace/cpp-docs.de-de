---
title: LIB-Eingabedateien
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 648871464dbc99972b8ca40579046347727e81cf
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808130"
---
# <a name="lib-input-files"></a>LIB-Eingabedateien

Die Eingabedateien, die von LIB erwartet hängen von der Modus, in dem Programm verwendet wird, wie in der folgenden Tabelle gezeigt.

|Modus|Eingabe|
|----------|-----------|
|Standard (erstellen oder Ändern einer Bibliothek)|COFF-Objektdateien (obj), COFF-Bibliotheken (lib), 32-Bit-Object-Modell-Format (OMF) Objektdateien (obj)|
|Extrahiert ein Element mit/Extract|COFF-Bibliothek (.lib)|
|Erstellen einen Export und Importbibliothek mit/DEF|Moduldefinitionsdatei (.def), COFF-Objektdateien (.obj), COFF-Bibliotheken (.lib), 32-Bit-OMF-Objektdateien (obj)-Dateien|

> [!NOTE]
>  OMF-Bibliotheken, die von der 16-Bit-Version der LIB erstellt, können nicht als Eingabe für die 32-Bit-Version der LIB verwendet werden.

## <a name="see-also"></a>Siehe auch

[Übersicht über LIB](overview-of-lib.md)
