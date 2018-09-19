---
title: Compilerwarnung (Stufe 4) C4710 | Microsoft-Dokumentation
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
ms.openlocfilehash: 1f6de17f7005db3834bfcfc93aff03f12f0293ce
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046094"
---
# <a name="compiler-warning-level-4-c4710"></a>Compilerwarnung (Stufe 4) C4710

'Funktion': Funktion, die nicht "inline"

Die angegebene Funktion für die Inlineerweiterung ausgewählt wurde, aber der Compiler hat nicht ausgeführt, das inlining.

Inlining wird nach Ermessen des Compilers ausgeführt. Die **Inline** Schlüsselwort, z. B. die **registrieren** Schlüsselwort dient als Hinweis für den Compiler. Der Compiler verwendet Heuristik beim Ermitteln, ob sollte eine bestimmte Funktion, um den Code zu beschleunigen, beim Kompilieren für Geschwindigkeit, oder wenn sie eine bestimmte Funktion, den Code zu verkleinern beim Kompilieren für Speicherplatz sollte. Der Compiler nur Inline wird beim Kompilieren für Speicherplatz sehr kleine Funktionen.

In einigen Fällen der Compiler werden nicht Inline eine bestimmte Funktion technischen Gründen. Finden Sie unter [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) eine Liste der Gründe, die der Compiler kann eine Funktion nicht Inline.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Standardmäßig deaktivierte Compilerwarnungen](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .