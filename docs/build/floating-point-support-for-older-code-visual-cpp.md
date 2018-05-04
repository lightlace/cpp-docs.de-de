---
title: Gleitkommaunterstützung für älteren Code (Visual C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cd7cbf955fbf795d06d9cd2448d0736dc435f3b5
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Gleitkommaunterstützung für älteren Code (Visual C++)
MMX und Gleitkomma-Stack-Register (MM0-MM7/ST0-ST7) werden über Kontextwechsel beibehalten.  Es ist keine explizite Aufrufkonvention für diese Register.  Die Verwendung von diese Register ist streng in Kernelmoduscode nicht zulässig.  
  
## <a name="see-also"></a>Siehe auch  
 [Aufrufkonvention](../build/calling-convention.md)