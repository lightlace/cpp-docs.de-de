---
title: Compilerfehler C2212
ms.date: 11/04/2016
f1_keywords:
- C2212
helpviewer_keywords:
- C2212
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
ms.openlocfilehash: a632aaf9809cd306354320a21cb03b993d60a95f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50496472"
---
# <a name="compiler-error-c2212"></a>Compilerfehler C2212

"Bezeichner": __based ist nicht verfügbar für Zeiger auf Funktionen

Zeiger auf Funktionen können nicht deklariert werden `__based`. Wenn Sie Code basierende Daten benötigen, verwenden Sie die `__declspec` Schlüsselwort oder `data_seg` Pragma.