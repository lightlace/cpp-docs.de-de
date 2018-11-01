---
title: Schwerwiegender Fehler C1905
ms.date: 11/04/2016
f1_keywords:
- C1905
helpviewer_keywords:
- C1905
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
ms.openlocfilehash: 3fb4db30d91e0dd8c9dbeeebca46210122e5ff07
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663151"
---
# <a name="fatal-error-c1905"></a>Schwerwiegender Fehler C1905

Front-End und Back-End sind nicht kompatibel (müssen auf denselben Prozessor ausgerichtet sein).

Dieser Fehler tritt auf, wenn eine OBJ-Datei wird von einem Compiler-Front-End (C1.dll) einen Prozessor, z. B. X86, ARM oder X64 generiert, aber durch ein Back-End (C2.dll), die einen anderen Zielprozessor gelesen wird.

Stellen Sie zur Behebung dieses Problems sicher, dass Front-End und Back-End kompatibel sind. Dies ist die Standardeinstellung für Projekte, die in Visual Studio erstellt wurden. Dieser Fehler kann auftreten, wenn Sie die Projektdatei bearbeitet und dabei verschiedene Pfade zu den Compilertools verwendet haben. Wenn Sie den Pfad für die Compilertools nicht ausdrücklich festgelegt haben, kann dieser Fehler auftreten, wenn die Visual Studio-Installation beschädigt ist. Beispielsweise können Sie Compiler-DLL-Dateien von einem Speicherort zu einem anderen kopiert haben. Verwendung **Programme und Funktionen** in der Windows-Systemsteuerung zu reparieren oder installieren Sie Visual Studio.