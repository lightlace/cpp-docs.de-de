---
title: Vorteile von Inlineassemblys
ms.date: 08/30/2018
helpviewer_keywords:
- assembler [C++], advantages
- inline assembly [C++], about inline assembly
- inline assembly [C++], using
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
ms.openlocfilehash: ecf1598ec90a8600e1fa9aae565724c254dc11e6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62167399"
---
# <a name="advantages-of-inline-assembly"></a>Vorteile von Inlineassemblys

**Microsoft-spezifisch**

Da der Inlineassembler keine separaten Assembly- und Verknüpfungsschritte erfordert, ist er einfacher als ein getrennter Assembler. Der Inlineassemblycode kann alle C-Variablen und -Funktionsnamen verwenden, die sich im Gültigkeitsbereich befinden. Daher ist es einfach, ihn in den C-Programmcode zu integrieren. Da der Assemblycode Inline mit C oder C++-Anweisungen kombiniert werden, kann, können sie Aufgaben ausführen, die mühsam oder unmöglich in C oder C++ sind.

Die Verwendung von Inlineassemblys gehören:

- Schreiben von Funktionen in der Assemblysprache.

- Stelle – Optimieren der Geschwindigkeit kritische Abschnitte des Codes.

- Machen direkten Hardwarezugriff für Gerätetreiber.

- Schreiben von Prolog- und epilogsequenzen Code für "naked" Aufrufe.

Inlineassembly ist ein spezielles Tool. Wenn Sie eine Anwendung auf verschiedenen Computern zu portieren möchten, sollten Sie wahrscheinlich computerspezifische Code in einem separaten Modul zu platzieren. Da der Inlineassembler aller Microsoft Macro Assembler (MASM) nicht unterstützt-Makro und Daten Anweisungen Umständen ist es praktischer MASM für solcher Module verwenden.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Inlineassembler](../../assembler/inline/inline-assembler.md)<br/>