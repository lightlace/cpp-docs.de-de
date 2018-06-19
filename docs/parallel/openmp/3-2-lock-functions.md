---
title: 3.2 Sperren Funktionen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cd788b0ef1c72b1f38a44ee608ce0c7760e24adc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696252"
---
# <a name="32-lock-functions"></a>3.2 Lock-Funktionen
Die Funktionen, die in diesem Abschnitt beschriebenen bearbeiten, sperren, die für die Synchronisierung verwendet wird.  
  
 Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen **Omp_lock_t**. Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle Funktionen der Sperre erfordert ein Argument, das einen Zeiger auf **Omp_lock_t** Typ.  
  
-   Die `omp_init_lock` Funktion initialisiert, eine einfache Sperre.  
  
-   Die `omp_destroy_lock` -Funktion entfernt eine einfache Sperre.  
  
-   Die `omp_set_lock` Funktion wartet, bis eine einfache Sperre verfügbar ist.  
  
-   Die `omp_unset_lock` Funktion gibt eine einfache Sperre frei.  
  
-   Die `omp_test_lock` Funktion testet eine einfache Sperre.  
  
 Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen **aufgerufen**.  Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle omp_nest_lock_t-Sperre-Funktionen erfordern ein Argument, das einen Zeiger auf **aufgerufen** Typ.  
  
-   Die `omp_init_nest_lock` Funktion initialisiert omp_nest_lock_t-Sperre.  
  
-   Die `omp_destroy_nest_lock` -Funktion entfernt omp_nest_lock_t-Sperre.  
  
-   Die `omp_set_nest_lock` Funktion wartet, bis eine Sperre omp_nest_lock_t verfügbar ist.  
  
-   Die `omp_unset_nest_lock` Funktion gibt eine omp_nest_lock_t-Sperre frei.  
  
-   Die `omp_test_nest_lock` Funktion testet eine omp_nest_lock_t Sperre.  
  
 Die OpenMP Lock-Funktionen zuzugreifen, die Sperren der Variable auf eine Weise, dass sie immer lesen und aktualisieren Sie den aktuellen Wert der Sperre Variablen. Es ist daher nicht erforderlich für ein OpenMP-Programm explizite einschließen **leeren** Anweisungen, um sicherzustellen, dass die Sperre Variable zwischen verschiedenen Threads konsistent ist. (Es gibt möglicherweise eine Notwendigkeit einer **leeren** Anweisungen, um die Werte der anderen Variablen konsistent zu machen.)