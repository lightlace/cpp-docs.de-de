---
title: LIB-Eingabedateien
ms.date: 11/04/2016
f1_keywords:
- Lib
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
ms.openlocfilehash: fb0095bd9e8699fbc9a1a144833d12d2cf4a1f83
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57423091"
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
