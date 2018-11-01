---
title: 3.2 Lock-Funktionen
ms.date: 11/04/2016
ms.assetid: 0ec855c6-55a9-49d7-bee4-5edae6e86a1b
ms.openlocfilehash: c189ba5b1f0bb365b387b4b4b887cfdb74d1bf2c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573068"
---
# <a name="32-lock-functions"></a>3.2 Lock-Funktionen

Die Funktionen, die in diesem Abschnitt beschriebenen bearbeiten, sperren, die für die Synchronisierung verwendet wird.

Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen **Omp_lock_t**. Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle Lock-Funktionen erfordern ein Argument, das einen Zeiger auf hat **Omp_lock_t** Typ.

- Die `omp_init_lock` Funktion initialisiert, eine einfache Sperre.

- Die `omp_destroy_lock` -Funktion entfernt eine einfache Sperre.

- Die `omp_set_lock` Funktion wartet, bis eine einfache Sperre verfügbar ist.

- Die `omp_unset_lock` Funktion gibt eine einfache Sperre frei.

- Die `omp_test_lock` Funktion testet eine einfache Sperre.

Für die folgenden Funktionen, die Sperren der Variable muss einen Typ aufweisen **aufgerufen**.  Diese Variable muss nur über diese Funktionen zugegriffen werden. Alle Funktionen der omp_nest_lock_t-Sperre erfordern ein Argument, das ist einen Zeiger auf **aufgerufen** Typ.

- Die `omp_init_nest_lock` Funktion initialisiert den omp_nest_lock_t-Sperre.

- Die `omp_destroy_nest_lock` -Funktion entfernt eine omp_nest_lock_t-Sperre.

- Die `omp_set_nest_lock` Funktion wartet, bis eine omp_nest_lock_t-Sperre verfügbar ist.

- Die `omp_unset_nest_lock` Funktion gibt eine omp_nest_lock_t-Sperre frei.

- Die `omp_test_nest_lock` Funktion testet eine omp_nest_lock_t-Sperre.

Die OpenMP-Lock-Funktionen auf die Sperren der Variable so, dass sie immer lesen und aktualisieren Sie den aktuellen Wert der Sperre Variablen zugreifen. Es ist daher nicht erforderlich für ein OpenMP-Programm explizite einschließen **leeren** Anweisungen, um sicherzustellen, dass die Sperre der Variablen in verschiedenen Threads konsistent ist. (Es kann beispielsweise erforderlich sein **leeren** Anweisungen, um die Werte der anderen Variablen konsistent zu machen.)