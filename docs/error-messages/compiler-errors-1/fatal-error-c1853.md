---
title: Schwerwiegender Fehler C1853 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 016e5bbf064643ddff0f63c5e16a967ed914f3e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044950"
---
# <a name="fatal-error-c1853"></a>Schwerwiegender Fehler C1853

> "*Filename*" vorkompilierte Headerdatei wird von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C (oder umgekehrt)

Mögliche Ursachen:

- Der vorkompilierte Header wurde mit einer früheren Compilerversion kompiliert. Versuchen Sie es den Header mit dem aktuellen Compiler neu zu kompilieren.

- Der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C. versuchen Sie es neu kompilieren zu müssen die Header für die Verwendung mit C durch Angabe eines der [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) Compileroptionen oder ändern das Suffix der Quelldatei in "c". Weitere Informationen finden Sie unter [zwei Methoden für das Vorkompilieren von Code](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).