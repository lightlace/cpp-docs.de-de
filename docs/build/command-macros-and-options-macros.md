---
title: Befehlsmakros und Optionsmakros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7c66295a42fff6a2e6dde5205fb5d9139e6eceb6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705535"
---
# <a name="command-macros-and-options-macros"></a>Befehlsmakros und Optionsmakros

Befehlsmakros sind für Microsoft-Produkten vordefiniert. Optionsmakros stellt Optionen für diese Produkte dar und sind standardmäßig nicht definiert. Beide in vordefinierten Rückschlussregeln werden verwendet, und können in Beschreibungsblöcke oder eine benutzerdefinierte Rückschlussregeln verwendet werden. Befehlsmakros können neu definiert werden, um teilweise oder vollständig eine Befehlszeile, einschließlich Optionen darzustellen. Optionsmakros generiert eine null-Zeichenfolge an, wenn Links nicht definiert.

|Microsoft-Produkt|Befehls-Makro|Definiert als|Optionen-Makro|
|-----------------------|-------------------|----------------|-------------------|
|Macro Assembler|**ALS**|ml|**AFLAGS**|
|Basic-Compiler|**BC**|BC|**BFLAGS**|
|C-Compiler|**CC**|CL|**CFLAGS**|
|C++ Compiler|**CPP**|CL|**CPPFLAGS**|
|C++ Compiler|**CXX AUFWEISEN**|CL|**CXXFLAGS**|
|Ressourcencompiler|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](../build/special-nmake-macros.md)