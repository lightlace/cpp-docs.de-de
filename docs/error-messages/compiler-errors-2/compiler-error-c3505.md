---
title: Compilerfehler C3505 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3505
dev_langs:
- C++
helpviewer_keywords:
- C3505
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0d6af1b96f23332b5eed82fab2c24c93e2d53dee
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054973"
---
# <a name="compiler-error-c3505"></a>Compilerfehler C3505

> Typbibliothek kann nicht geladen werden kann '*Guid*"

C3505 kann verursacht werden, wenn Sie die 32-Bit, X86 gehostete-Cross-Compiler für 64-Bit-Version ausführen, X64 Ziele auf einem 64-Bit-Computer, da der Compiler unter WOW64 ausgeführt wird, und können nur aus der 32-Bit-Registrierungsstruktur lesen.

Sie können diesen Fehler beheben, durch das Erstellen von 32-Bit- und 64-Bit-Versionen der Typbibliothek, die Sie importieren möchten, und registrieren Sie sie beide.  Sie können auch den systemeigenen 64-Bit-Compiler, der ändern, muss Ihre **VC++-Verzeichnisse** Eigenschaft in der IDE, um auf die 64-Bit-Compiler zu verweisen.

Weitere Informationen finden Sie unter

- [Vorgehensweise: Aktivieren eines 64-Bit-Visual C++-Toolsets auf der Befehlszeile](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)

- [Vorgehensweise: Konfigurieren von Visual C++-Projekten für 64-Bit-x64-Zielplattformen](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)