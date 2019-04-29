---
title: /STUB (Name der MS-DOS-Stubdatei)
ms.date: 11/04/2016
f1_keywords:
- /stub
- VC.Project.VCLinkerTool.DosStub
helpviewer_keywords:
- Win32 [C++], attaching MS-DOS stub program
- STUB linker option
- MS-DOS stub file name linker option
- /STUB linker option
- Windows API [C++], attaching MS-DOS stub program
- -STUB linker option
ms.assetid: 65221ffe-4f9a-4a14-ac69-3cfb79b40b5f
ms.openlocfilehash: 7150d4ff8f35b00d96caa21fd5ea3754fec76030
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317873"
---
# <a name="stub-ms-dos-stub-file-name"></a>/STUB (Name der MS-DOS-Stubdatei)

```
/STUB:filename
```

## <a name="arguments"></a>Argumente

*filename*<br/>
Eine MS-DOS-Anwendung.

## <a name="remarks"></a>Hinweise

Die/Stub-Option Fügt ein MS-DOS-Stubprogramm an ein Win32-Programm.

Ein Stub-Programm wird aufgerufen, wenn die Datei in MS-DOS-ausgeführt wird. Dabei wird in der Regel eine entsprechende Meldung angezeigt. Allerdings kann jeder gültige MS-DOS-Anwendung ein Stub-Programm sein.

Geben Sie einen *Filename* für die Stub-Programm nach einem Doppelpunkt (:) in der Befehlszeile. Der Linker überprüft *Filename* und eine Fehlermeldung ausgegeben, wenn die Datei nicht ausführbar ist. Die Anwendung muss eine .exe-Datei sein. eine COM-Datei ist ungültig für ein Stubprogramm.

Wenn diese Option nicht verwendet wird, fügt der Linker ein Standard-Stub-Programm, das die folgende Meldung gibt:

```
This program cannot be run in MS-DOS mode.
```

Beim Erstellen eines virtuellen Gerätetreibers *Filename* ermöglicht dem Benutzer, die einen Dateinamen angeben, die eine Anweisung-Struktur (definiert in WINNT. enthält. H), die in der VXD, anstatt der Standardheader verwendet werden.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Festlegen von C++-Compiler und die Build-Eigenschaften in Visual Studio](../working-with-project-properties.md).

1. Klicken Sie auf die **Linker** Ordner.

1. Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .

1. Geben Sie die Option in der **zusätzliche Optionen** Feld.

### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Siehe auch

[MSVC-Linkerreferenz](linking.md)<br/>
[MSVC-Linkeroptionen](linker-options.md)
