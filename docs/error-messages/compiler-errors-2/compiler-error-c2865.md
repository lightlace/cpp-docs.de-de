---
title: Compilerfehler C2865 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2865
dev_langs: C++
helpviewer_keywords: C2865
ms.assetid: 973eb6a0-c99a-4d25-b3e5-fe0539794d77
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 149ca019ef30d66dba63bc927d79064a269d8c70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2865"></a>Compilerfehler C2865
'Funktion': Unzulässiger Vergleich für Handle_or_pointer  
  
 Sie können Verweise auf Vergleichen [Klassen und Strukturen](../../windows/classes-and-structs-cpp-component-extensions.md) oder verwaltete Verweistypen nur auf Gleichheit zu überprüfen, ob sie auf dasselbe Objekt (==) oder auf andere Objekte verweisen (! =).  
  
 Sie können nicht verglichen werden zum Sortieren, da der .NET Common Language Runtime verwaltete Objekte zu einem beliebigen Zeitpunkt verschoben werden kann das Ergebnis des Tests ändern.