---
title: Compilerfehler C2129
ms.date: 11/04/2016
f1_keywords:
- C2129
helpviewer_keywords:
- C2129
ms.assetid: 21a8223e-1d22-4baa-9ca1-922b7f751dd0
ms.openlocfilehash: e55107419235420d272c738e9d8ef7cf277c11c9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50593455"
---
# <a name="compiler-error-c2129"></a>Compilerfehler C2129

statische Funktion 'Funktion' deklariert, aber nicht definiert

Ein Vorwärtsverweis wird versucht, eine `static` -Funktion, die nicht definiert ist.

Ein `static` -Funktion im Dateibereich definiert werden muss. Wenn die Funktion in einer anderen Datei definiert ist, muss diese deklariert werden `extern`.