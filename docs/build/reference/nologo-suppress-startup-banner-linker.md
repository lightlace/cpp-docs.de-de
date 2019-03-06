---
title: /NOLOGO (Startbanner unterdrücken) (Linker)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SuppressStartupBanner
- /nologo
helpviewer_keywords:
- suppress startup banner linker option
- -NOLOGO linker option
- /NOLOGO linker option
- copyright message
- version numbers, preventing linker display
- banners, suppressing startup
- NOLOGO linker option
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
ms.openlocfilehash: 1b966c1f7af556a85aadcafaa8ed43da5b3f75df
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57422155"
---
# <a name="nologo-suppress-startup-banner-linker"></a>/NOLOGO (Startbanner unterdrücken) (Linker)

```
/NOLOGO
```

## <a name="remarks"></a>Hinweise

Die/nologo-Option verhindert die Anzeige der Copyrightmeldung und der Versionsnummer.

Diese Option unterdrückt die Anzeige von Befehlsdateien. Weitere Informationen finden Sie unter [LINK-Befehlsdateien](../../build/reference/link-command-files.md).

Standardmäßig werden diese Informationen durch den Linker an, das Fenster "Ausgabe" gesendet. In der Befehlszeile es wird an die Standardausgabe gesendet und kann in eine Datei umgeleitet werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Diese Option sollte nur über die Befehlszeile verwendet werden.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

1. Diese Linkeroption kann nicht programmgesteuert geändert werden.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)
