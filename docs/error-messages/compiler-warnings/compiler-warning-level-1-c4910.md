---
title: Compilerwarnung (Stufe 1) C4910 | Microsoft Docs
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
ms.openlocfilehash: 34ed2ec16f579b05a572cf6bfc236cd8d5743f63
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910
"\<Bezeichner >": "__declspec(dllexport)" und "Extern" sind bei einer expliziten Instanziierung nicht kompatibel  
  
 Die explizite Vorlageninstanziierung namens  *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Explizite Instantiierung](../../cpp/explicit-instantiation.md)   
 [Dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)