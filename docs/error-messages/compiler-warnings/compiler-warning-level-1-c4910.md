---
title: Compilerwarnung (Stufe 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: f0d1df0a383b6646d52fc2babc53ca656d49ace6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428196"
---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910

"\<Bezeichner >": "__declspec(dllexport)" und "Extern" bei einer expliziten Instanziierung nicht miteinander kompatibel sind

Die explizite Vorlageninstanziierung namens  *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.

## <a name="see-also"></a>Siehe auch

[Explizite Instantiierung](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)