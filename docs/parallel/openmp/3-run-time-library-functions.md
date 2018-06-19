---
title: 3. Run-Time-Bibliotheksfunktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d747f775509c6b3b2b95be51d95ea937816d3cd1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688114"
---
# <a name="3-run-time-library-functions"></a>3. Run-Time Library-Funktionen
Dieser Abschnitt beschreibt die Funktionen der OpenMP-C- und C++-Laufzeitbibliothek. Der Header  **\<omp.h >** deklariert zwei Typen, die mehrere Funktionen, die verwendet werden können, zum Steuern und Abfragen der Umgebung für die parallele Ausführung und Sperren von Funktionen, die zum Synchronisieren des Zugriffs auf Daten verwendet werden können.  
  
 Der Typ **Omp_lock_t** kann ein Objekttyp, um darzustellen, dass eine Sperre verfügbar wird oder ein Thread im Besitz einer Sperre. Diese Sperren werden als bezeichnet *einfache Sperren*.  
  
 Der Typ **aufgerufen** einen Objekttyp, der entweder, dass darstellen kann eine Sperre ist verfügbar, oder sowohl die Identität des Threads, die die Sperre besitzt und eine *Schachteln von Count* (siehe unten). Diese Sperren werden als bezeichnet *omp_nest_lock_t Sperren*.  
  
 Die Bibliotheksfunktionen sind externe Funktionen mit "C"-Bindung.  
  
 Die Beschreibungen in diesem Kapitel sind in den folgenden Themen unterteilt:  
  
-   Ausführungsumgebungsfunktionen (siehe [Abschnitt 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) auf Seite "35").  
  
-   Sperren von Funktionen (finden Sie unter [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41).