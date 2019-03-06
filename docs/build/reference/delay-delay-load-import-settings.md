---
title: /DELAY (Laden von Importeinstellungen verzögern)
ms.date: 11/04/2016
f1_keywords:
- /delay
- VC.Project.VCLinkerTool.DelayNoBind
- VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL
- VC.Project.VCLinkerTool.DelayUnload
helpviewer_keywords:
- delayed loading of DLLs, /DELAY option
- DELAY linker option
- /DELAY linker option
- -DELAY linker option
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
ms.openlocfilehash: 56f019e99eb9a54b83f6b070d769efa2b94f5621
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57426375"
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
