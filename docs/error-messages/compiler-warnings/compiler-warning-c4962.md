---
title: Compilerwarnung C4962 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4962
dev_langs:
- C++
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: caff08744497936839e1021cef8fc86e0e8aa7e5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066257"
---
# <a name="compiler-warning-c4962"></a>Compilerwarnung C4962

'Funktion': Profilgesteuerte Optimierungen wurden deaktiviert, da durch die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde

Eine Funktion wurde nicht mit '/LTCG: PGO' kompiliert, da (Profil) Daten zur Anzahl für die Funktion nicht zuverlässig waren. Wiederholen Sie die Profilerstellung, um die PGC-Datei erneut zu generieren, die die unzuverlässigen Profildaten für diese Funktion enthält.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).