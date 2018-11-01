---
title: Schwerwiegender Fehler C1128
ms.date: 11/04/2016
f1_keywords:
- C1128
helpviewer_keywords:
- C1128
ms.assetid: 6f9580fd-ecef-48be-9780-dcf666704279
ms.openlocfilehash: bb1d9af10084d6b3e75325450c7f13ea1683ee2e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661218"
---
# <a name="fatal-error-c1128"></a>Schwerwiegender Fehler C1128

Anzahl der Abschnitte überschreitet Objektdateiformatgrenze: Kompilieren mit /bigobj

Eine OBJ-Datei hat die Anzahl der zulässigen Abschnitte überschritten. Hierbei handelt es sich um eine Formatbeschränkung für COFF-Objektdateien.

Erreichen dieser kann sich auf das Ergebnis der Verwendung von [/Gy](../../build/reference/gy-enable-function-level-linking.md) ein Debugbuild; **/Gy** bewirkt, dass Funktionen in ihren eigenen COMDAT-Abschnitten wechseln. Ein Debugbuild enthält für jede COMDAT-Funktion einen Abschnitt mit Debuginformationen.

C1128 kann auch durch die Verwendung zu vieler Inlinefunktionen verursacht werden.

Um diesen Fehler zu beheben, teilen Sie Ihre Quelldatei in mehrere Quellcodedateien auf und Kompilieren ohne **/Gy**, oder Kompilieren Sie mit  [ /bigobj (Erhöhen der Anzahl von Abschnitten in. OBJ-Datei)](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md).  Wenn Sie nicht mit Kompilieren **/Gy**, Sie müssen die Optimierungen einzeln angeben da **"/ O2"** und **"/ O1"** sowohl implizieren **/Gy**.

Kompilieren Sie nach Möglichkeit ohne Debuginformationen.

Möglicherweise benötigen Sie außerdem spezifische Vorlageninstanziierungen in separaten Quellcodedateien, anstatt sie vom Compiler ausgeben zu lassen.

Beim Portieren von Code wird C1128 wahrscheinlich erst bei Verwendung der X64 Compiler und viel später bei der X86 Compiler. X64 müssen mindestens 4 Bereiche jeder kompilierten Funktion zugeordneten **/Gy** oder in Vorlagen oder Klassen: code, Pdata, und die Debuginformationen sowie möglicherweise Xdata.  Bei X86 ist der pdata-Abschnitt nicht vorhanden.