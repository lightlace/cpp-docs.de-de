---
title: / DEPENDENTLOADFLAG (festgelegte Standardwert abhängiges Laden Flags)
description: Die /DEPENDENTLOADFLAG-Option wird die Standardflags für DLLs, die über LoadLibrary geladen
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
ms.openlocfilehash: 5a171f3c2edbbbf614a986ff78dd2405e734a1d1
ms.sourcegitcommit: d1f576a0f59678edc3d93508cf46485138332178
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "34753709"
---
# <a name="dependentloadflag-set-default-dependent-load-flags"></a>/ DEPENDENTLOADFLAG (festgelegte Standardwert abhängiges Laden Flags)

Legt die Standard-Load-Flags verwendet wird, wenn `LoadLibrary` wird verwendet, um das Laden von DLLs.

## <a name="syntax"></a>Syntax

> **/ DEPENDENTLOADFLAG**[**:**_Loadflags_]

### <a name="arguments"></a>Argumente

|||
|-|-|
*loadflags*|Ein optionaler "C"-Style-16-Bit-Ganzzahl-Wert in decimal, mit einer führenden Null oktale oder hexadezimale mit einem vorangestellten Schrägstrich `0x`, angibt, dass die abhängigen Load-Flags, die für alle gelten [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187) aufrufen. Der Standardwert ist 0.

## <a name="remarks"></a>Hinweise

Diese Option ist neu in Visual Studio 2017 und gilt nur für apps, die unter Windows 10 RS1 und höheren Versionen ausgeführt. Diese Option wird von anderen Betriebssystemen ignoriert, die die app auszuführen.

Auf unterstützten Betriebssystemen, diese Option hat die Auswirkungen der Änderung Aufrufe `LoadLibrary("dependent.dll")` auf das Äquivalent `LoadLibraryEx("dependent.dll", 0, loadflags)`. Aufrufe von [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091) sind davon nicht betroffen. Diese Option gilt nicht rekursiv für DLLs, die von Ihrer app geladen werden.

Dieses Flag kann verwendet werden, um DLL Pflanzen Angriffe zu verhindern. Wenn eine app verwendet z. B. `LoadLibrary` um eine abhängige DLL zu laden, könnte ein Angreifer eine DLL mit dem gleichen Namen im Suchpfad von verwendet Pflanze `LoadLibrary`, z. B. das aktuelle Verzeichnis der kann überprüft werden vor den Dateisystemverzeichnissen ist sicheren DLL-Suchmodus deaktiviert. Sichere DLL-Suchmodus hält aktuellen Verzeichnis des Benutzers weiter unten in der Suchreihenfolge und ist unter Windows XP SP2 und höheren Versionen standardmäßig aktiviert. Weitere Informationen finden Sie unter [Dynamic Link Library-Suchreihenfolge](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

Wenn Sie angeben, dass die Option zum Verknüpfen `/DEPENDENTLOADFLAG:0xA00` (der Wert der kombinierte Flags `LOAD_LIBRARY_SEARCH_APPLICATION_DIR | LOAD_LIBRARY_SEARCH_SYSTEM32`), handelt, auch wenn sichere DLL-Suchmodus auf dem Computer des Benutzers deaktiviert ist, die DLL-Suchpfad auf geschützten Verzeichnisse beschränkt, die für Angreifer schwieriger sind ändern. Informationen zu den verfügbaren Flags und ihre symbolischen und numerische Werte finden Sie in der *DwFlags* parameterbeschreibung in [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091).

### <a name="to-set-the-dependentloadflag-linker-option-in-the-visual-studio-development-environment"></a>Um die DEPENDENTLOADFLAG-Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die Option im **Zusatzoptionen**.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

- [Festlegen von Linkeroptionen](setting-linker-options.md)
- [Linkeroptionen](linker-options.md)
- [Gewusst wie: implizit mit einer DLL verknüpfen](../linking-an-executable-to-a-dll.md#linking-implicitly)
- [Welche Verknüpfungsmethode ermitteln](../linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)
- [LoadLibrary](https://go.microsoft.com/fwlink/p/?LinkID=259187)
- [LoadLibraryEx](https://go.microsoft.com/fwlink/p/?LinkID=236091)
- [Dynamic Link Library-Suchreihenfolge](https://msdn.microsoft.com/library/windows/desktop/ms682586.aspx)
