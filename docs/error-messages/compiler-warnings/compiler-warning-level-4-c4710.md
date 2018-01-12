---
title: Compilerwarnung (Stufe 4) C4710 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4710
dev_langs: C++
helpviewer_keywords: C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0464d924c21a029a97a8f03d30f88127f3aea6a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4710"></a>Compilerwarnung (Stufe 4) C4710
'Funktion': Funktion nicht inline  
  
 Die angegebene Funktion für die Inlineerweiterung ausgewählt wurde, aber der Compiler hat nicht ausgeführt, das inlining.  
  
 Inlining erfolgt nach Ermessen des Compilers. Die **Inline** Schlüsselwort, z. B. die **registrieren** Schlüsselwort dient als Hinweis für den Compiler. Der Compiler verwendet Heuristik, um festzustellen, ob es eine bestimmte Funktion, die Code beschleunigen, beim Kompilieren für Geschwindigkeit sollten oder wenn es eine bestimmte Funktion, den Code beim Kompilieren für Speicherplatz verkleinern sollten. Der Compiler nur Inline wird beim Kompilieren für Speicherplatz sehr kleine Funktionen.  
  
 In einigen Fällen der Compiler wird nicht Inline eine bestimmte Funktion mechanische Gründen. Finden Sie unter [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) eine Liste der Gründe, die der Compiler kann eine Funktion nicht Inline.  
  
 Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .