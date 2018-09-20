---
title: 4. Umgebungsvariablen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 4ec7ed81-e9ca-46a1-84f8-8f9ce4587346
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aec56dad334dcd27de2068e660ff8ec5a6e72f90
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46415490"
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