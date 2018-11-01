---
title: 4. Umgebungsvariablen
ms.date: 11/04/2016
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
ms.openlocfilehash: 0dec302762ad22fc3c7f6691ef63df1b07d5940d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456601"
---
# <a name="4-environment-variables"></a>4. Umgebungsvariablen

In diesem Kapitel wird beschrieben, die Umgebungsvariablen OpenMP-C- und C++-API (oder Äquivalent plattformspezifischen Mechanismen), die die Ausführung von parallelen Code steuern.  Die Namen der Umgebungsvariablen muss in Großbuchstaben. Die Werte, die ihnen zugewiesene werden Groß-/Kleinschreibung und möglicherweise führende und nachfolgende Leerzeichen.  Änderungen der Werte, die nach dem Start des Programms werden ignoriert.

Die Umgebungsvariablen sind wie folgt aus:

- **OMP_SCHEDULE** legt die Laufzeit-Zeitplan-Typ und Block Größe fest.

- **OMP_NUM_THREADS** legt die Anzahl der Threads an, während der Ausführung verwendet.

- **OMP_DYNAMIC** aktiviert oder deaktiviert die dynamische Anpassung der Anzahl von Threads.

- **OMP_NESTED** aktiviert oder deaktiviert die geschachtelten Parallelität.

Den Beispielen in diesem Kapitel wird nur gezeigt, wie diese Variablen in Unix C shellumgebungen (Csh) festgelegt werden können. In Korn ähneln Shell und DOS-Umgebungen die Aktionen, wie folgt:

Csh: Setenv OMP_SCHEDULE "dynamisch"

Ksh: Exportieren von OMP_SCHEDULE = "dynamic"

DOS: Legen Sie OMP_SCHEDULE = "dynamic"