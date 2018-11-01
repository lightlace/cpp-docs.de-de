---
title: LIB-Eingabedateien
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: 885d03e74c7acff54e527c2dbad38de055913b5f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503315"
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

[Übersicht über LIB](../../build/reference/overview-of-lib.md)