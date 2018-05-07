---
title: Schwerwiegender Fehler C1853 | Microsoft Docs
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
ms.openlocfilehash: 9aa6a67c13f76b0bf43159b9e9de95068102a2b1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1853"></a>Schwerwiegender Fehler C1853
  
> "*Filename*" vorkompilierte Headerdatei wird von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C (oder umgekehrt)  
  
Mögliche Ursachen:  
  
-   Der vorkompilierte Header wurde mit einer früheren Compilerversion kompiliert. Versuchen Sie, den Header mit dem aktuellen Compiler neu zu kompilieren.  
  
-   Der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C. versuchen Sie es den Header für die Verwendung mit C durch Angabe einer Neukompilierung der [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) Compileroptionen oder ändern das Suffix der Quelldatei in "c". Weitere Informationen finden Sie unter [zwei Optionen für das Vorkompilieren von Code](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).