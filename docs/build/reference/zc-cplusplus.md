---
title: /Zc:__cplusplus (Aktivieren des aktualisierten Makros __cplusplus)
ms.date: 05/16/2019
f1_keywords:
- /Zc:__cplusplus
helpviewer_keywords:
- -Zc:__cplusplus compiler option (C++)
- __cplusplus macro (C++)
ms.openlocfilehash: 43392438eabc7cc7f6decb1349d112a0ce5bd0f5
ms.sourcegitcommit: a10c9390413978d36b8096b684d5ed4cf1553bc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65837547"
---
# <a name="zccplusplus-enable-updated-cplusplus-macro"></a>/Zc:__cplusplus (Aktivieren des aktualisierten Makros __cplusplus)

Die Compileroption **/Zc:__cplusplus** ermöglicht es dem Präprozessormakro **\_\_cplusplus**, einen aktualisierten Wert für die Unterstützung der aktuellen C++-Sprachstandards zu melden. Standardmäßig gibt Visual Studio für das Präprozessormakro **\_\_cplusplus** immer den Wert „199711L“ zurück.

## <a name="syntax"></a>Syntax

> **/Zc:__cplusplus**[ **-** ]

## <a name="remarks"></a>Anmerkungen

Das Präprozessormakro **\_\_cplusplus** wird allgemein verwendet, um die Unterstützung für eine bestimmte Version des C++-Standards zu melden. Da anscheinend viel bestehender Code davon abhängig ist, dass der Wert dieses Makros mit „199711L“ übereinstimmt, ändert der Compiler den Wert des Makros nicht, sofern Sie sich nicht durch Verwenden der Compileroption **/Zc:__cplusplus** explizit dafür entscheiden. Die Option **/Zc:__cplusplus** ist von Visual Studio 2017, Version 15.7, an verfügbar und standardmäßig deaktiviert. In früheren Versionen von Visual Studio und standardmäßig oder wenn **/Zc:__cplusplus-** angegeben ist, gibt Visual Studio den Wert „199711L“ für das Präprozessormakro **\_\_cplusplus** zurück. **/Zc:__cplusplus** wird nicht mithilfe der Option [/permissive-](permissive-standards-conformance.md) aktiviert.

Wenn die Option **/Zc:__cplusplus** aktiviert ist, hängt der vom Makro **\_\_cplusplus** gemeldete Wert von der Einstellung des Versionsschalters [/std](std-specify-language-standard-version.md) ab. Diese Tabelle zeigt die möglichen Werte für das Makro:

|/Zc:__cplusplus-Schalter|/std:c++-Schalter|__cplusplus-Wert|
|-|-|-|
Zc:__cplusplus|/std:c++14 (Standardwert)|201402L
Zc:__cplusplus|/std:c++17|201703L
Zc:__cplusplus|/std:c++latest|201704L
Zc:__cplusplus- (deaktiviert)|Beliebiger Wert|199711L
Nicht angegeben|Beliebiger Wert|199711L

Der Compiler unterstützt keine Standardschalter für C++98, C++03 oder C++11.

Um eine detailliertere Erkennung von Änderungen am Compilertoolset zu ermöglichen, verwenden Sie das vordefinierte Makro [_MSC_VER](../../preprocessor/predefined-macros.md). Der Wert dieses integrierten Makros wird für jedes Toolsetupdate in Visual Studio 2017 und höheren Versionen heraufgesetzt. Das vordefinierte Makro [_MSVC_LANG](../../preprocessor/predefined-macros.md) meldet die Standardversion unabhängig davon, ob die Option **/Zc:__cplusplus** aktiviert oder deaktiviert ist. Wenn **/Zc:__cplusplus** aktiviert ist, `__cplusplus == _MSVC_LANG`.

### <a name="to-set-this-compiler-option-in-visual-studio"></a>So legen Sie diese Compileroption in Visual Studio fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen erhalten Sie unter [Set C++ compiler and build properties in Visual Studio (Festlegen der Compiler- und Buildeigenschaften (C++) in Visual Studio)](../working-with-project-properties.md).

1. Klicken Sie auf der Eigenschaftenseite auf **Konfigurationseigenschaften** > **C/C++** > **Befehlszeile**.

1. Fügen Sie im Bereich **Zusätzliche Optionen** **/Zc:__cplusplus** oder **/Zc:__cplusplus-** hinzu.

## <a name="see-also"></a>Siehe auch

- [/Zc (Übereinstimmung)](zc-conformance.md)
- [/std (Standardversion für die Sprache festlegen)](std-specify-language-standard-version.md)
- [Vordefinierte Makros](../../preprocessor/predefined-macros.md)
