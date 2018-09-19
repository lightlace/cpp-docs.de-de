---
title: Compilerfehler C2919 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2919
dev_langs:
- C++
helpviewer_keywords:
- C2919
ms.assetid: 140a6db9-eb48-4c5e-84a7-a09d2653605b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5d6ee01e32cd1855855fa6ac071af159be8bac0d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46106830"
---
# <a name="compiler-error-c2919"></a>Compilerfehler C2919

'type': Operatoren können nicht direkt auf der veröffentlichten Oberfläche eines WinRT-Typs verwendet werden.

Das Windows-Runtime-Typsystem unterstützt nicht die Operatormemberfunktionen auf der veröffentlichten Oberfläche eines Typs. Dies liegt daran, weil nicht alle Sprachen Operatormemberfunktionen verwenden können. Sie können private oder interne Operatormemberfunktionen erstellen, die über C++-Code in derselben Klasse oder Kompilationskomponente aufgerufen werden können.

Entfernen Sie zum Beheben dieses Problems die Operatormemberfunktion aus der öffentlichen Schnittstelle, oder ändern Sie sie in eine benannte Memberfunktion. Benennen Sie die Memberfunktion beispielsweise anstelle von `operator==` in `Equals` um.