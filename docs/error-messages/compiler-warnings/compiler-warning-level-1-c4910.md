---
title: Compilerwarnung (Stufe 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 49cbbf3369fc4765d93e67e2dca84a4d975560d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242889"
---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910

"\<Bezeichner >": "__declspec(dllexport)" und "Extern" bei einer expliziten Instanziierung nicht miteinander kompatibel sind

Die explizite Vorlageninstanziierung namens  *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.

## <a name="see-also"></a>Siehe auch

[Explizite Instantiierung](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)