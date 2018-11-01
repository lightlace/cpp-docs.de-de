---
title: Kompilierung (Aktivieren der aktualisierten __cplusplus-Makro)
ms.date: 05/30/2018
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 8e73d93ae0618a04bdcc8476fadb6cc2aab595b4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50623989"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>Kompilierung (Aktivieren der aktualisierten __cplusplus-Makro)

Die **Kompilierung** Compiler-Option ermöglicht die  **\_ \_Cplusplus** Präprozessor-Makro, um einen aktualisierten Wert für die aktuelle Unterstützung der C++-Sprache-Standards zu melden. Standardmäßig Visual Studio stets den Wert zurückgibt "199711L" für die  **\_ \_Cplusplus** Präprozessor-Makro.

## <a name="syntax"></a>Syntax

> **Kompilierung**[**-**]

## <a name="remarks"></a>Hinweise

Die  **\_ \_Cplusplus** Präprozessor-Makro wird häufig verwendet, die Unterstützung für eine bestimmte Version des C++-Standards. Da viele von vorhandenem Code angezeigt wird, hängt von den Wert dieses Makros, die übereinstimmende "199711 L", der Compiler ändert nicht den Wert des Makros, wenn Sie explizit mit sich die **Kompilierung** -Compileroption. Die **Kompilierung** Option steht in Visual Studio 2017 Version 15.7 ab und ist standardmäßig deaktiviert. In früheren Versionen von Visual Studio, und klicken Sie in der Standardeinstellung oder wenn **/Zc:__cplusplus-** angegeben ist, Visual Studio gibt den Wert "199711 L" für die  **\_ \_Cplusplus** Präprozessor-Makro. Die [/ PERMISSIVE--](permissive-standards-conformance.md) Option ermöglicht keine **Kompilierung**.

Wenn die **Kompilierung** Option aktiviert ist, von gemeldeten Wert handelt es die  **\_ \_Cplusplus** Makro hängt von der [/Std](std-specify-language-standard-version.md) Version wechseln die Einstellung. Diese Tabelle zeigt die möglichen Werte für das Makro:

|Kompilierung|/Std:c++ switch|__cplusplus-Wert|
|-|-|-|
Zc:__cplusplus|/ Std: c ++ 14 (Standard)|201402L
Zc:__cplusplus|/ Std: c ++ 17|201703L
Zc:__cplusplus|/ Std: c ++ neueste|201704L
Zc:__cplusplus-(deaktiviert)|Beliebiger Wert|199711L
Nicht angegeben|Beliebiger Wert|199711L

Der Compiler unterstützt nicht den Standards Switches für C ++ 98, C ++ 03 und C ++ 11.

Verwenden Sie für die eine umfassendere Erkennung von Änderungen an den Compiler-Toolset, das [_MSC_VER](../../preprocessor/predefined-macros.md) vordefiniertes Makro. Der Wert des integrierten Makro wird für jedes Update in Visual Studio 2017 und höheren Versionen des Toolsets erhöht. Die [_MSVC_LANG](../../preprocessor/predefined-macros.md) vordefiniertes Makro meldet die standard-Version gibt an, ob die **Kompilierung** Option aktiviert oder deaktiviert ist. Wenn **Kompilierung** aktiviert ist, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **C/C++-** > **Befehlszeile** Eigenschaftenseite.

1. Hinzufügen **Kompilierung** oder **/Zc:__cplusplus-** auf die **zusätzliche Optionen:** Bereich.

## <a name="see-also"></a>Siehe auch

- [/Zc (Übereinstimmung)](zc-conformance.md)
- [/ Std (Geben Sie Language standard Version)](std-specify-language-standard-version.md)
- [Vordefinierte Makros](../../preprocessor/predefined-macros.md)
