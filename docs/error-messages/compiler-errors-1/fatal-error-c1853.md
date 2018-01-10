---
title: Schwerwiegender Fehler C1853 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1853
dev_langs: C++
helpviewer_keywords: C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 05c29c266aad095517734fdcac776e12467d34ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1853"></a>Schwerwiegender Fehler C1853
  
> "*Filename*" vorkompilierte Headerdatei wird von einer früheren Version des Compilers, oder der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C (oder umgekehrt)  
  
Mögliche Ursachen:  
  
-   Der vorkompilierte Header wurde mit einer früheren Compilerversion kompiliert. Versuchen Sie, den Header mit dem aktuellen Compiler neu zu kompilieren.  
  
-   Der vorkompilierte Header stammt von C++, und Sie verwenden ihn von C. versuchen Sie es den Header für die Verwendung mit C durch Angabe einer Neukompilierung der [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) Compileroptionen oder ändern das Suffix der Quelldatei in "c". Weitere Informationen finden Sie unter [zwei Optionen für das Vorkompilieren von Code](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).