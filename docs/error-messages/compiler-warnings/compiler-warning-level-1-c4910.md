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
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: b8416e456a7d985eb7a3c40addb716ba5c30bf96
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4910"></a>Compilerwarnung (Stufe 1) C4910
"\<Bezeichner >": "__declspec(dllexport)" und "Extern" sind bei einer expliziten Instanziierung nicht kompatibel  
  
 Die explizite Vorlageninstanziierung namens *\<Bezeichner >* geändert wird, indem sowohl die `__declspec(dllexport)` und `extern` Schlüsselwörter. Die beiden Schlüsselwörter schließen sich jedoch gegenseitig aus. Das `__declspec(dllexport)` -Schlüsselwort soll die Instanziierung der Vorlagenklasse bewirken, während das `extern` -Schlüsselwort verhindern soll, dass die Vorlagenklasse automatisch instanziiert wird.  
  
## <a name="see-also"></a>Siehe auch  
 [Explizite Instantiierung](../../cpp/explicit-instantiation.md)   
 [Dllexport, dllimport](../../cpp/dllexport-dllimport.md)   
 [Allgemeine Regeln und Einschränkungen](../../cpp/general-rules-and-limitations.md)
