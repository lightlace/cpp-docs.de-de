---
title: Compilerwarnung C4962
ms.date: 11/04/2016
f1_keywords:
- C4962
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
ms.openlocfilehash: e3f7b715da3774d8289fdd526cf1fa0b5bdddba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280801"
---
# <a name="compiler-warning-c4962"></a>Compilerwarnung C4962

'Funktion': Profilgesteuerte Optimierungen wurden deaktiviert, da die Optimierungen eine Inkonsistenz zwischen den Profildaten verursacht wurde."

Eine Funktion wurde nicht mit '/LTCG: PGO' kompiliert, da (Profil) Daten zur Anzahl für die Funktion nicht zuverlässig waren. Wiederholen Sie die Profilerstellung, um die PGC-Datei erneut zu generieren, die die unzuverlässigen Profildaten für diese Funktion enthält.

Diese Warnung ist standardmäßig deaktiviert. Weitere Informationen finden Sie unter [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md).