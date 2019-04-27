---
title: Schwerwiegender Fehler C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: ec2d6bf6bac46cca8bdc2e3b8fe7cc6b7799d78a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165917"
---
# <a name="fatal-error-c1853"></a>Schwerwiegender Fehler C1853

> "*Filename*" vorkompilierte Headerdatei wird von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C (oder umgekehrt)

Mögliche Ursachen:

- Der vorkompilierte Header wurde mit einer früheren Compilerversion kompiliert. Versuchen Sie es den Header mit dem aktuellen Compiler neu zu kompilieren.

- Der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C. versuchen Sie es neu kompilieren zu müssen die Header für die Verwendung mit C durch Angabe eines der [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) Compileroptionen oder ändern das Suffix der Quelldatei in "c". Weitere Informationen finden Sie unter [zwei Methoden für das Vorkompilieren von Code](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code).