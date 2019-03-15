---
title: Befehlsmakros und Optionsmakros
ms.date: 11/04/2016
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
ms.openlocfilehash: c6dad7b50d265a1460a98747665d48051078163a
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2019
ms.locfileid: "57826006"
---
# <a name="command-macros-and-options-macros"></a>Befehlsmakros und Optionsmakros

Befehlsmakros sind für Microsoft-Produkten vordefiniert. Optionsmakros stellt Optionen für diese Produkte dar und sind standardmäßig nicht definiert. Beide in vordefinierten Rückschlussregeln werden verwendet, und können in Beschreibungsblöcke oder eine benutzerdefinierte Rückschlussregeln verwendet werden. Befehlsmakros können neu definiert werden, um teilweise oder vollständig eine Befehlszeile, einschließlich Optionen darzustellen. Optionsmakros generiert eine null-Zeichenfolge an, wenn Links nicht definiert.

|Microsoft-Produkt|Befehls-Makro|Definiert als|Optionen-Makro|
|-----------------------|-------------------|----------------|-------------------|
|Macro Assembler|**AS**|ml|**AFLAGS**|
|Basic-Compiler|**BC**|bc|**BFLAGS**|
|C-Compiler|**CC**|cl|**CFLAGS**|
|C++ Compiler|**CPP**|cl|**CPPFLAGS**|
|C++ Compiler|**CXX**|cl|**CXXFLAGS**|
|Ressourcencompiler|**RC**|rc|**RFLAGS**|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
