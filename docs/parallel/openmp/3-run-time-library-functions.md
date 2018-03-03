---
title: 3. Run-Time-Bibliotheksfunktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: b226e512-6822-4cbe-a2ca-74cc2bb7e880
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f1cbedf8782c9c5ccb25bda3f8b43df8a526f268
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="3-run-time-library-functions"></a>3. Run-Time Library-Funktionen
Dieser Abschnitt beschreibt die Funktionen der OpenMP-C- und C++-Laufzeitbibliothek. Der Header  **\<omp.h >** deklariert zwei Typen, die mehrere Funktionen, die verwendet werden können, zum Steuern und Abfragen der Umgebung für die parallele Ausführung und Sperren von Funktionen, die zum Synchronisieren des Zugriffs auf Daten verwendet werden können.  
  
 Der Typ **Omp_lock_t** kann ein Objekttyp, um darzustellen, dass eine Sperre verfügbar wird oder ein Thread im Besitz einer Sperre. Diese Sperren werden als bezeichnet *einfache Sperren*.  
  
 Der Typ **aufgerufen** einen Objekttyp, der entweder, dass darstellen kann eine Sperre ist verfügbar, oder sowohl die Identität des Threads, die die Sperre besitzt und eine *Schachteln von Count* (siehe unten). Diese Sperren werden als bezeichnet *omp_nest_lock_t Sperren*.  
  
 Die Bibliotheksfunktionen sind externe Funktionen mit "C"-Bindung.  
  
 Die Beschreibungen in diesem Kapitel sind in den folgenden Themen unterteilt:  
  
-   Ausführungsumgebungsfunktionen (siehe [Abschnitt 3.1](../../parallel/openmp/3-1-execution-environment-functions.md) auf Seite "35").  
  
-   Sperren von Funktionen (finden Sie unter [Abschnitt 3.2](../../parallel/openmp/3-2-lock-functions.md) auf Seite 41).