---
title: Schwerwiegender Fehler C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 30cf003cc81cb27f7c68b7f0a38529e2d9c88ef5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677824"
---
# <a name="fatal-error-c1853"></a>Schwerwiegender Fehler C1853

> "*Filename*" vorkompilierte Headerdatei wird von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C (oder umgekehrt)

Mögliche Ursachen:

- Der vorkompilierte Header wurde mit einer früheren Compilerversion kompiliert. Versuchen Sie es den Header mit dem aktuellen Compiler neu zu kompilieren.

- Der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C. versuchen Sie es neu kompilieren zu müssen die Header für die Verwendung mit C durch Angabe eines der [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) Compileroptionen oder ändern das Suffix der Quelldatei in "c". Weitere Informationen finden Sie unter [zwei Methoden für das Vorkompilieren von Code](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).