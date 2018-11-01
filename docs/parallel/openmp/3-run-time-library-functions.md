---
title: 3. Funktionen der Laufzeitbibliothek
ms.date: 11/04/2016
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
ms.openlocfilehash: e1d8d498be7f58bcf510025c67c539127f450824
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484096"
---
# <a name="3-run-time-library-functions"></a>3. Funktionen der Laufzeitbibliothek

Dieser Abschnitt beschreibt die Funktionen für OpenMP-C- und C++-Laufzeitbibliothek. Der Header  **\<comp.h >** deklariert zwei Typen, die mehrere Funktionen, die verwendet werden können, zur Steuerung und die Umgebung für die Ausführung paralleler Abfragen und Sperren von Funktionen, die zum Synchronisieren des Zugriffs auf Daten verwendet werden können.

Der Typ **Omp_lock_t** ein Objekttyp ausgedrückt werden können, dass eine Sperre verfügbar ist, oder für den Besitz eines Threads ist eine Sperre. Diese Sperren werden als bezeichnet *einfache Sperren*.

Der Typ **aufgerufen** ist ein Objekttyp kann darstellt, entweder, dass eine Sperre verfügbar ist oder sowohl die Identität des Threads, die die Sperre besitzt und eine *schachteln Anzahl* (siehe unten). Diese Sperren werden als bezeichnet *schachtelbaren Sperren*.

Die Bibliotheksfunktionen weisen externe Funktionen mit "C"-Verknüpfung.

Die Beschreibungen in diesem Kapitel sind in den folgenden Themen unterteilt:

- Ausführungsumgebungsfunktionen (finden Sie unter [Abschnitt 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) auf 35).

- Sperren von Funktionen (finden Sie unter [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41).