---
title: Compilerfehler C2919
ms.date: 11/04/2016
f1_keywords:
- C2919
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
ms.openlocfilehash: ab11226c8cc4629a265dd182d5f882f6b3be7e5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62160851"
---
# <a name="compiler-error-c2919"></a>Compilerfehler C2919

'type': Operatoren können nicht auf der veröffentlichten Oberfläche eines WinRT-Typs verwendet werden

Das Windows-Runtime-Typsystem unterstützt nicht die Operatormemberfunktionen auf der veröffentlichten Oberfläche eines Typs. Dies liegt daran, weil nicht alle Sprachen Operatormemberfunktionen verwenden können. Sie können private oder interne Operatormemberfunktionen erstellen, die über C++-Code in derselben Klasse oder Kompilationskomponente aufgerufen werden können.

Entfernen Sie zum Beheben dieses Problems die Operatormemberfunktion aus der öffentlichen Schnittstelle, oder ändern Sie sie in eine benannte Memberfunktion. Benennen Sie die Memberfunktion beispielsweise anstelle von `operator==` in `Equals` um.