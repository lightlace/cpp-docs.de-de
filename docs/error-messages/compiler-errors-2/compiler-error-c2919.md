---
title: Compilerfehler C2919 | Microsoft Docs
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
ms.openlocfilehash: c5e2eb2a32f1a906814f5b347ba1ebf13eba71ff
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245801"
---
# <a name="compiler-error-c2919"></a>Compilerfehler C2919
'type': Operatoren können nicht direkt auf der veröffentlichten Oberfläche eines WinRT-Typs verwendet werden.  
  
 Das Windows-Runtime-Typsystem unterstützt nicht die Operatormemberfunktionen auf der veröffentlichten Oberfläche eines Typs. Dies liegt daran, weil nicht alle Sprachen Operatormemberfunktionen verwenden können. Sie können private oder interne Operatormemberfunktionen erstellen, die über C++-Code in derselben Klasse oder Kompilationskomponente aufgerufen werden können.  
  
 Entfernen Sie zum Beheben dieses Problems die Operatormemberfunktion aus der öffentlichen Schnittstelle, oder ändern Sie sie in eine benannte Memberfunktion. Benennen Sie die Memberfunktion beispielsweise anstelle von `operator==` in `Equals` um.