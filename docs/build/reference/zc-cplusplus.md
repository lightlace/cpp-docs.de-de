---
title: /Zc:__cplusplus (Aktivieren der aktualisierte __cplusplus-Makro)
ms.custom: ''
ms.date: 05/30/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /Zc:__cplusplus
dev_langs:
- C++
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a796794c0086b09c15ee88442e0fea4d1b114d98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/01/2018
ms.locfileid: "34705713"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (Aktivieren der aktualisierte __cplusplus-Makro)

Die **/Zc:__cplusplus** Compiler Option ermöglicht die  **\_ \_Cplusplus** Präprozessor-Makro, um einen aktualisierten Wert für den aktuellen C++-Standards sprachunterstützung zu melden. Standardmäßig Visual Studio immer gibt den Wert "199711L" für die  **\_ \_Cplusplus** Präprozessormakro.

## <a name="syntax"></a>Syntax

> **/Zc:__cplusplus**[**-**]

## <a name="remarks"></a>Hinweise

Die  **\_ \_Cplusplus** Präprozessormakro wird häufig verwendet, um Unterstützung für eine bestimmte Version des C++-Standards. Da viele von vorhandenem Code angezeigt wird, hängen von den Wert dieses Makros "199711 L" entsprechen, der Compiler ändert nicht den Wert des Makros, wenn Sie explizit mit teilnehmen die **/Zc:__cplusplus** -Compileroption. Die **/Zc:__cplusplus** Option steht in Visual Studio 2017 Version 15.7 ab und ist standardmäßig deaktiviert. In früheren Versionen von Visual Studio, und standardmäßig oder wenn **/Zc:__cplusplus-** angegeben wird, Visual Studio gibt den Wert "199711 L" für die  **\_ \_Cplusplus** Präprozessor-Makro. Die [/ liberalen-](permissive-standards-conformance.md) Option ermöglicht keine **/Zc:__cplusplus**.

Wenn der **/Zc:__cplusplus** Option aktiviert ist, der Wert von gemeldeten der  **\_ \_Cplusplus** Makro richtet sich nach der [/std](std-specify-language-standard-version.md) Version Switch festlegen. Diese Tabelle zeigt die möglichen Werte für das Makro:

|/Zc:__cplusplus switch|/Std:c++ switch|__cplusplus-Wert|
|-|-|-|
Zc:__cplusplus|/Std:c ++ 14 (Standard)|201402L
Zc:__cplusplus|/Std:c ++ 17|201703L
Zc:__cplusplus|/Std:c ++ neueste|201704L
Zc:__cplusplus-(deaktiviert)|Beliebiger Wert|199711L
Nicht angegeben|Beliebiger Wert|199711L

Der Compiler unterstützt nicht Switches Standards für C ++ 98, C ++ 03 oder C ++ 11.

Verwenden Sie bei der Erkennung von Änderungen, die das Compilertoolset differenziertere der [_MSC_VER](../../preprocessor/predefined-macros.md) vorkompiliertes Makro. Bei jedem Update Toolset in Visual Studio 2017 und höheren Versionen wird der Wert dieses integrierte Makros erhöht. Die [_MSVC_LANG](../../preprocessor/predefined-macros.md) vordefiniertes Makro meldet die Standardversion gibt an, ob die **/Zc:__cplusplus** Option aktiviert oder deaktiviert ist. Wenn **/Zc:__cplusplus** aktiviert ist, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen **/Zc:__cplusplus** oder **/Zc:__cplusplus-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

- [/Zc (Übereinstimmung)](zc-conformance.md)
- [/Std (Geben Sie standard Sprachversion)](std-specify-language-standard-version.md)
- [Vordefinierte Makros](../../preprocessor/predefined-macros.md)
