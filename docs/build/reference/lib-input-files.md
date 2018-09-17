---
title: LIB-Eingabedateien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- Lib
dev_langs:
- C++
helpviewer_keywords:
- input files, LIB
ms.assetid: e1236f0d-cd90-446b-b900-f311f456085c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 952c3345234192e3798fea483d527cd3afec4bff
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702467"
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