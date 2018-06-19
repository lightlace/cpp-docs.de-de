---
title: / FUNCTIONPADMIN (erstellen Hotpatch-fähiges Abbild) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /functionpadmin
dev_langs:
- C++
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d0a5ecfcc336e198de0adcc2393f740072d70cae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376753"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Erstellen eines Hotpatch-fähigen Abbildes)

Bereitet ein Image für Hotpatching vor.

## <a name="syntax"></a>Syntax

> **/ FUNCTIONPADMIN**[**:**_Speicherplatz_]  

### <a name="arguments"></a>Argumente

*space*<br/>
Die den Abstand für die hinzuzufügende am Anfang jeder Funktion in Bytes. Auf X86 standardmäßig 5 Bytes Abstand und auf X64 standardmäßig 6 Bytes. Für andere Ziele muss ein Wert angegeben werden.

## <a name="remarks"></a>Hinweise

Damit der Linker ein Hotpatch-fähiges Abbild erstellt werden kann, die OBJ-Dateien müssen wurden kompiliert mit [/hotpatch (Erstellen eines Hotpatch-fähigen Abbildes)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Wenn Sie kompilieren und verknüpfen ein Bild mit einem einzelnen Aufruf von cl.exe, **/hotpatch** impliziert **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Wählen Sie die **Konfigurationseigenschaften** > **Linker** > **Befehlszeile** Eigenschaftenseite.

1. Geben Sie die **/FUNCTIONPADMIN** option **Zusatzoptionen**. Wählen Sie **OK** zum Speichern der Änderungen.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
