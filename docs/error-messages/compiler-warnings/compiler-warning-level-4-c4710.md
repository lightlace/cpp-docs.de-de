---
title: Compilerwarnung (Stufe 4) C4710 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c1cc77d8ee5393fe600ceadd9c1335d76e32efe
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33296386"
---
# <a name="compiler-warning-level-4-c4710"></a>Compilerwarnung (Stufe 4) C4710
'Funktion': Funktion nicht inline  
  
 Die angegebene Funktion für die Inlineerweiterung ausgewählt wurde, aber der Compiler hat nicht ausgeführt, das inlining.  
  
 Inlining erfolgt nach Ermessen des Compilers. Die **Inline** Schlüsselwort, z. B. die **registrieren** Schlüsselwort dient als Hinweis für den Compiler. Der Compiler verwendet Heuristik, um festzustellen, ob es eine bestimmte Funktion, die Code beschleunigen, beim Kompilieren für Geschwindigkeit sollten oder wenn es eine bestimmte Funktion, den Code beim Kompilieren für Speicherplatz verkleinern sollten. Der Compiler nur Inline wird beim Kompilieren für Speicherplatz sehr kleine Funktionen.  
  
 In einigen Fällen der Compiler wird nicht Inline eine bestimmte Funktion mechanische Gründen. Finden Sie unter [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) eine Liste der Gründe, die der Compiler kann eine Funktion nicht Inline.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .