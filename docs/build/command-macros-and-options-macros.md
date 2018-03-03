---
title: Befehlsmakros und Optionsmakros | Microsoft Docs
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
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 06f5d48395c0395a85c90096bf2dbad8627ac41a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="command-macros-and-options-macros"></a>Befehlsmakros und Optionsmakros
Befehlsmakros sind für Microsoft-Produkte vordefiniert. Optionenmakros stellen die Optionen für diese Produkte dar und sind standardmäßig nicht definiert. Beide werden in vordefinierten Rückschlussregeln verwendet und können in Beschreibungsblöcken oder benutzerdefinierten Rückschlussregeln verwendet werden. Befehlsmakros können neu definiert werden, um über die Befehlszeile, einschließlich Optionen ganz oder teilweise darzustellen. Optionenmakros generieren eine null-Zeichenfolge an, wenn bleiben undefiniert.  
  
|Microsoft-Produkt|Befehl-Makro|Definiert als|Optionen-Makro|  
|-----------------------|-------------------|----------------|-------------------|  
|Macro Assembler|**ALS**|ml|**AFLAGS**|  
|Basic-Compiler|**BC**|BC|**BFLAGS**|  
|C-Compiler|**CC**|CL|**CFLAGS**|  
|C++ Compiler|**CPP**|CL|**CPPFLAGS**|  
|C++ Compiler|**CXX AUFWEISEN**|CL|**CXXFLAGS**|  
|Ressourcencompiler|**RC**|RC|**RFLAGS**|  
  
## <a name="see-also"></a>Siehe auch  
 [Besondere NMAKE-Makros](../build/special-nmake-macros.md)