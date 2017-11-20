---
title: NULL und Undefinierte Makros | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, undefined macros
- Null macros in NMAKE
- macros, null and undefined
- undefined macros and NMAKE
- NMAKE program, null macros
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee85d6959536d2845d7b6e6ccf7f07924e46143f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="null-and-undefined-macros"></a>NULL-Makros und undefinierte Makros
Null und nicht definiert-Makros erweitert, um null-Zeichenfolgen, jedoch ein Makro definiert als eine null-Zeichenfolge in vorverarbeitungsausdrücke definierten berücksichtigt. Um ein Makro als null-Zeichenfolge zu definieren, geben Sie keine Zeichen außer Leerzeichen oder Tabstopps hinter dem Gleichheitszeichen (=) in einer Befehlszeile oder Befehlsdatei, und schließen Sie die null-Zeichenfolge oder der Definition in doppelte Anführungszeichen (""). Um ein Makro aufzuheben, verwenden Sie **! UNDEF.** Weitere Informationen finden Sie unter [Makefile-Vorverarbeitung Direktiven](../build/makefile-preprocessing-directives.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Definieren eines NMAKE-Makros](../build/defining-an-nmake-macro.md)