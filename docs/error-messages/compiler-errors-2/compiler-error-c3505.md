---
title: Compilerfehler C3505
ms.date: 11/04/2016
f1_keywords:
- C3505
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
ms.openlocfilehash: 5730102371d00ebaf3ae05fdefb70184b58d7c18
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400330"
---
# <a name="compiler-error-c3505"></a>Compilerfehler C3505

> Typbibliothek kann nicht geladen werden kann '*Guid*"

C3505 kann verursacht werden, wenn Sie die 32-Bit, X86 gehostete-Cross-Compiler für 64-Bit-Version ausführen, X64 Ziele auf einem 64-Bit-Computer, da der Compiler unter WOW64 ausgeführt wird, und können nur aus der 32-Bit-Registrierungsstruktur lesen.

Sie können diesen Fehler beheben, durch das Erstellen von 32-Bit- und 64-Bit-Versionen der Typbibliothek, die Sie importieren möchten, und registrieren Sie sie beide.  Sie können auch den systemeigenen 64-Bit-Compiler, der ändern, muss Ihre **VC++-Verzeichnisse** Eigenschaft in der IDE, um auf die 64-Bit-Compiler zu verweisen.

Weitere Informationen finden Sie unter

- [Vorgehensweise: Aktivieren eines 64-Bit-Visual C++-Toolsets über die Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [Vorgehensweise: Konfigurieren von Visual C++-Projekten für 64-Bit-Zielplattformen (x64)](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)