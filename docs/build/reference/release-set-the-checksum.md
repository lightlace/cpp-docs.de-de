---
title: /RELEASE (Prüfsumme festlegen)
ms.date: 11/04/2016
f1_keywords:
- /release
- VC.Project.VCLinkerTool.SetChecksum
helpviewer_keywords:
- -RELEASE linker option
- /RELEASE linker option
- checksum setting
- RELEASE linker option
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
ms.openlocfilehash: 6a45e6caa94054d4d485476786ecc5149545ed8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478807"
---
# <a name="release-set-the-checksum"></a>/RELEASE (Prüfsumme festlegen)

```
/RELEASE
```

## <a name="remarks"></a>Hinweise

Die/Release-Option wird die Prüfsumme im Header der .exe-Datei.

Das Betriebssystem ist die Prüfsumme für Gerätetreiber erforderlich. Legen Sie die Prüfsumme für Releaseversionen der Gerätetreiber, um die Kompatibilität mit zukünftigen Betriebssystemen sicherzustellen.

Die/Release-Option ist standardmäßig eingestellt, wenn die [/Subsystem: native](../../build/reference/subsystem-specify-subsystem.md) angegeben wird.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die **erweitert** Eigenschaftenseite.

1. Ändern der **Prüfsumme setzen** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)