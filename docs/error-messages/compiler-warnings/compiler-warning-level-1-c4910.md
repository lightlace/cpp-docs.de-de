---
title: Compilerwarnung (Stufe 1) C4910 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f758e2e15d5492724e9b819622202831d4e9f5d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910
"\<Bezeichner >": "__declspec(dllexport)" und "Extern" sind bei einer expliziten Instanziierung nicht kompatibel  
  
 Die explizite Vorlageninstanziierung namens  *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Explizite Instantiierung](../../cpp/explicit-instantiation.md)   
 [Dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)