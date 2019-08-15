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
ms.openlocfilehash: ef6f5f768cf86f470d1322fa2a7bee6db794c2ef
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493010"
---
# <a name="delay-delay-load-import-settings"></a>/DELAY (Laden von Importeinstellungen verzögern)

```
/DELAY:UNLOAD
/DELAY:NOBIND
```

## <a name="remarks"></a>Hinweise

Die Option/Delay steuert das [verzögerte Laden](linker-support-for-delay-loaded-dlls.md) von DLLs:

- Der UNLOAD-Qualifizierer weist die Hilfsfunktion für das verzögerte Laden an, das explizite Entladen der DLL zu unterstützen. Die Importadresstabelle (IAT) wird in ihre ursprüngliche Form zurückgesetzt, wodurch IAT-Zeiger ungültig und überschrieben werden.

   Wenn Sie nicht entladen auswählen, tritt beim Abrufen von [funloaddelta ayloadeddll](explicitly-unloading-a-delay-loaded-dll.md) ein Fehler auf.

- Der NOBIND-Qualifizierer weist den Linker an, keine bindungsfähige IAT in das endgültige Image einzuschließen. Das Standardverhalten ist, die bindungsfähige IAT für verzögert geladene DLLs zu erstellen. Das daraus resultierende Image kann nicht statisch gebunden werden. (Images mit bindungsfähigen IATs können vor der Ausführung statisch gebunden werden.) Siehe [/Bind](bind.md).

   Wenn die dll gebunden ist, versucht die Hilfsfunktion, die gebundenen Informationen zu verwenden, anstatt [GetProcAddress](/windows/win32/api/libloaderapi/nf-libloaderapi-getprocaddress) für jeden der referenzierten Importe abzurufen. Wenn entweder der Zeitstempel oder die bevorzugte Adresse nicht mit denen der geladenen DLL übereinstimmt, geht die Hilfsfunktion davon aus, dass die gebundene IAT veraltet ist, und fährt fort, als würde die gebundene IAT nicht existieren.

   NOBIND führt dazu, dass Ihr Programmimage größer ist, kann aber die Ladezeit der DLL beschleunigen. Wenn Sie nicht beabsichtigen, die DLL zu binden, verhindert NOBIND, dass die gebundene IAT erstellt wird.

Verwenden Sie die Option [/DELAYLOAD](delayload-delay-load-import.md) , um DLLs zum verzögerten Laden anzugeben.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie [unter C++ Festlegen von Compiler-und Buildeigenschaften in Visual Studio](../working-with-project-properties.md).

1. Erweitern Sie **Konfigurations Eigenschaften**, **Linker**, und wählen Sie dann **erweitert**aus.

1. Ändern Sie die Eigenschaft **verzögert geladene DLL** .

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
