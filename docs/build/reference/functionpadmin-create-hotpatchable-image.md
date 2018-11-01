---
title: /FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: c1e84f308796eabcaea61518e3731f633c2f67e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474892"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)

Bereitet ein Image für Hotpatching vor.

## <a name="syntax"></a>Syntax

> **/ FUNCTIONPADMIN**[**:**_Speicherplatz_]

### <a name="arguments"></a>Argumente

*space*<br/>
Die Größe der Auffüllung, die am Anfang jeder Funktion in Bytes hinzugefügt werden soll. Auf X86 der Standardwert lautet 5 Byte-Auffüllung und standardmäßig auf X64 und 6 Bytes. Von anderen Zielen muss ein Wert angegeben werden.

## <a name="remarks"></a>Hinweise

In der Reihenfolge für den Linker an, ein Bild eines Hotpatch-fähigen zu erzeugen, die OBJ-Dateien müssen bereits kompiliert wurden mit [/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Wenn Sie kompilieren und verknüpfen ein Bild mit einem einzelnen Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/FUNCTIONPADMIN** option **zusätzliche Optionen**. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
