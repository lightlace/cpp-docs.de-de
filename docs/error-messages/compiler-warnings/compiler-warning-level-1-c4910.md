---
title: Compilerwarnung (Stufe 1) C4910 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6db959e467ea449a66feb3ee07c202f4dee002
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018950"
---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910

"\<Bezeichner >": "__declspec(dllexport)" und "Extern" bei einer expliziten Instanziierung nicht miteinander kompatibel sind

Die explizite Vorlageninstanziierung namens  *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.

## <a name="see-also"></a>Siehe auch

[Explizite Instantiierung](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)