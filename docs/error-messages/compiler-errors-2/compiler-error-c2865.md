---
title: Compilerfehler C2865 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2865
dev_langs:
- C++
helpviewer_keywords:
- C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70b2c6c831fde18f9054e139a120d834a75b6950
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2865"></a>Compilerfehler C2865
'Funktion': Unzulässiger Vergleich für Handle_or_pointer  
  
 Sie können Verweise auf Vergleichen [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) oder verwaltete Verweistypen nur auf Gleichheit zu überprüfen, ob sie auf dasselbe Objekt (==) oder auf andere Objekte verweisen (! =).  
  
 Sie können nicht verglichen werden zum Sortieren, da der .NET Common Language Runtime verwaltete Objekte zu einem beliebigen Zeitpunkt verschoben werden kann das Ergebnis des Tests ändern.