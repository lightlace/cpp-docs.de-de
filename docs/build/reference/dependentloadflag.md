---
title: / DEPENDENTLOADFLAG (festgelegte Standardwert abhängiger Ladevorgang Flags)
description: Die /DEPENDENTLOADFLAG Optionssätze Standardflags für DLLs, die mit LoadLibrary geladen
ms.custom: ''
ms.date: 05/18/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- dependentloadflag
dev_langs:
- C++
helpviewer_keywords:
- LINK tool [C++], dependent load flags
- -DEPENDENTLOADFLAG linker option
- linker [C++], DEPENDENTLOADFLAG
- DEPENDENTLOADFLAG linker option
- /DEPENDENTLOADFLAG linker option
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94f7667d7da8d8e9cd7ef38cb01d0f03b0da82e3
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/16/2018
ms.locfileid: "42571704"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (festgelegte Standardwert abhängiger Ladevorgang Flags)

Legt die Standard-Load-Flags verwendet wird, wenn `LoadLibrary` wird verwendet, um das Laden von DLLs.

## <a name="syntax"></a>Syntax

> **/ DEPENDENTLOADFLAG**[**:**_Loadflags_]

### <a name="arguments"></a>Argumente

|||
|-|-|
*loadflags*|Ein optionaler "C"-Style-16-Bit-Ganzzahl-Wert in Dezimal, mit einer führenden Null Oktal- oder Hexadezimalformat, mit einem vorangestellten `0x`, die angibt, dass die abhängiger Ladevorgang-Flags, die auf alle anwenden [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) aufrufen. Der Standardwert ist 0.

## <a name="remarks"></a>Hinweise

Diese Option ist neu in Visual Studio 2017, und gilt nur für apps, die auf Windows 10 RS1 oder höher ausgeführt wird. Diese Option wird von anderen Betriebssystemen ignoriert, die die app ausführen.

Auf unterstützten Betriebssystemen, diese Option hat die Auswirkungen der Änderung Aufrufe `LoadLibrary("dependent.dll")` , der die Entsprechung `LoadLibraryEx("dependent.dll", 0, loadflags)`. Aufrufe von [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) sind davon nicht betroffen. Diese Option gilt nicht rekursiv auf DLLs, die von Ihrer app geladen werden.

Dieses Flag kann verwendet werden, um DLL Pflanzen Angriffe zu verhindern. Wenn eine app verwendet z. B. `LoadLibrary` um eine abhängige DLL zu laden, ein Angreifer eine DLL mit dem gleichen Namen in den Suchpfad, der von verwendeten generieren kann `LoadLibrary`, z. B. das aktuelle Verzeichnis, das möglicherweise werden vor dem überprüft Systemverzeichnisse, wenn der sichere Modus der DLL-Suche ist deaktiviert. Abgesicherter Modus von DLL-Suche wird der aktuelle Verzeichnis des Benutzers weiter unten in den Suchergebnissen, und ist auf Windows XP SP2 und höher standardmäßig aktiviert. Weitere Informationen finden Sie unter [Dynamic Link Library Search Order](/windows/desktop/Dlls/dynamic-link-library-search-order).

Wenn Sie die Linkoption angeben `/DEPENDENTLOADFLAG:0xA00` (der Wert der kombinierte Flags `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), und selbst wenn Abgesicherter Modus von DLL-Suche auf dem Computer des Benutzers deaktiviert ist, die DLL-Suchpfad auf geschützte Verzeichnisse beschränkt ist, die für einen Angreifer schwieriger sind Ändern Sie. Weitere Informationen zu den verfügbaren Flags und deren Werte von numerischen und symbolischen, finden Sie unter den *DwFlags* parameterbeschreibung in [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie die DEPENDENTLOADFLAG-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option in **zusätzliche Optionen**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](setting-linker-options.md)
- [Linkeroptionen](linker-options.md)
- [Implizit mit einer DLL verknüpfen](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Bestimmen Sie welche Verknüpfungsmethode verwendet werden](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [Dynamic Link Library Search Order](/windows/desktop/Dlls/dynamic-link-library-search-order)
