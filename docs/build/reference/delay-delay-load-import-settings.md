---
title: -DELAY (Laden von Importeinstellungen verzögern) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 086fab7d1d50f96ab05c38f2e6d524d7ff344e02
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49081915"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Laden von Importeinstellungen verzögern)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Hinweise

Die/Delay-Option steuert [das verzögerte Laden von](../../build/reference/linker-support-for-delay-loaded-dlls.md) von DLLs:

- Der UNLOAD-Qualifizierer weist die Hilfsfunktion für das verzögerte Laden an, das explizite Entladen der DLL zu unterstützen. Die Importadresstabelle (IAT) wird in ihre ursprüngliche Form zurückgesetzt, wodurch IAT-Zeiger ungültig und überschrieben werden.

   Wenn Sie UNLOAD nicht auswählen, jeden Aufruf von [FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) schlägt fehl.

- Der NOBIND-Qualifizierer weist den Linker an, keine bindungsfähige IAT in das endgültige Image einzuschließen. Das Standardverhalten ist, die bindungsfähige IAT für verzögert geladene DLLs zu erstellen. Das daraus resultierende Image kann nicht statisch gebunden werden. (Images mit bindungsfähigen IATs können vor der Ausführung statisch gebunden werden.) Finden Sie unter [/BIND](../../build/reference/bind.md).

   Wenn die DLL gebunden ist, versucht die Hilfsfunktion, die die gebundene Informationen zu verwenden, statt [GetProcAddress](/windows/desktop/api/libloaderapi/nf-libloaderapi-getprocaddress) auf jedem der referenzierten Importe. Wenn entweder der Zeitstempel oder die bevorzugte Adresse nicht mit denen der geladenen DLL übereinstimmt, geht die Hilfsfunktion davon aus, dass die gebundene IAT veraltet ist, und fährt fort, als würde die gebundene IAT nicht existieren.

   NOBIND führt dazu, dass Ihr Programmimage größer ist, kann aber die Ladezeit der DLL beschleunigen. Wenn Sie nicht beabsichtigen, die DLL zu binden, verhindert NOBIND, dass die gebundene IAT erstellt wird.

Verwenden Sie zum Angeben von DLLs, um das verzögerte Laden der [/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) Option.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).

1. Erweitern Sie **Konfigurationseigenschaften**, **Linker**, und wählen Sie dann **erweitert**.

1. Ändern der **verzögert geladene DLL** Eigenschaft.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Siehe auch

[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)<br/>
[Linkeroptionen](../../build/reference/linker-options.md)