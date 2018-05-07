---
title: Compilerfehler C2129 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2129
dev_langs:
- C++
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4d151c774672b1788ca893a9812deb3e41100dc0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2129"></a>Compilerfehler C2129
statische Funktion 'Funktion' deklariert, aber nicht definiert  
  
 Ein Vorwärtsverweis wird versucht, eine `static` -Funktion, die nie definiert ist.  
  
 Ein `static` -Funktion im Dateibereich definiert werden muss. Wenn die Funktion in einer anderen Datei definiert ist, er muss deklariert werden `extern`.