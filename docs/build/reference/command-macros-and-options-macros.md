---
title: Befehlsmakros und Optionsmakros
description: Beschreibt die vordefinierten NMAKE-Makros für Buildtools und deren Optionen.
ms.date: 11/20/2019
helpviewer_keywords:
- options macros
- command macros in NMAKE
- macros, options macros
- macros, command macros
ms.assetid: 50dff03c-0dc3-4a8a-9a17-57e0e4ea9bac
no-loc:
- AS
- AFLAGS
- CC
- CFLAGS
- CPP
- CPPFLAGS
- CXX
- CXXFLAGS
- RC
- RFLAGS
- ias
- ml
- ml64
- cl
- rc
ms.openlocfilehash: d5c4477fd97e2a6c48dbac4d0ce83f7fd5f12ad6
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303172"
---
# <a name="command-macros-and-options-macros"></a>Befehlsmakros und Optionsmakros

Befehls Makros sind für Microsoft-Produkte vordefiniert. Options Makros stellen Optionen für diese Produkte dar und sind standardmäßig nicht definiert. Beide werden in vordefinierten Inferenz Regeln verwendet und können in Beschreibungs Blöcken oder benutzerdefinierten Inferenz Regeln verwendet werden. Befehls Makros können neu definiert werden, um den Teil oder die gesamte Befehlszeile darzustellen, einschließlich der Optionen. Options Makros generieren eine NULL-Zeichenfolge, wenn Sie nicht definiert ist.

|Microsoft-Produkt|Befehls Makro|Definiert als|Options-Makro|
|-----------------------|-------------------|----------------|-------------------|
|Makro Assembler|**AS**|ml, ias oder ml64|**AFLAGS**|
|C-Compiler|**CC**|cl|**CFLAGS**|
|C++ Compiler|**CPP**|cl|**CPPFLAGS**|
|C++ Compiler|**CXX**|cl|**CXXFLAGS**|
|Ressourcencompiler|**RC**|RC|**RFLAGS**|

## <a name="see-also"></a>Siehe auch

[Besondere NMAKE-Makros](special-nmake-macros.md)
