---
title: Compilerfehler C2818
ms.date: 11/04/2016
f1_keywords:
- C2818
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
ms.openlocfilehash: f6e33d0e0ee139138df7d8e11357100b3ec3a1a9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593439"
---
# <a name="compiler-error-c2818"></a>Compilerfehler C2818

Anwendung des überladenen Operators "->" wird durch den Typ 'Typ'

Eine Neudefinition des dem Klassenmemberzugriffs-Operator enthält einen rekursiven `return` Anweisung. So definieren Sie um die `->` Operator bei der Rekursion, müssen Sie verschieben die rekursive Routine in eine separate Funktion des Operators aufgerufen überschreiben Funktion.