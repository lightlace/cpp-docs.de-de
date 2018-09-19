---
title: -Gm (minimale Neuerstellung aktivieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.MinimalRebuild
- /Gm
- /FD
- VC.Project.VCCLWCECompilerTool.MinimalRebuild
dev_langs:
- C++
helpviewer_keywords:
- /Gm compiler option [C++]
- minimal rebuild
- enable minimal rebuild compiler option [C++]
- Gm compiler option [C++]
- -Gm compiler option [C++]
ms.assetid: d8869ce0-d2ea-40eb-8dae-6d2cdb61dd59
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0f18881e79a3f82941f04dccbde210b2c62dcbca
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725763"
---
# <a name="gm-enable-minimal-rebuild"></a>/Gm (Minimale Neuerstellung aktivieren)

Aktiviert die minimale Neuerstellung, die bestimmt, ob C++-Quelldateien, die geänderte C++-Klassendefinitionen enthalten (gespeichert in Headerdateien (.h)) neu kompiliert werden müssen.

## <a name="syntax"></a>Syntax

```
/Gm
```

## <a name="remarks"></a>Hinweise

Der Compiler speichert Abhängigkeitsinformationen zwischen Quelldateien und Klassendefinitionen während der ersten Kompilierung in der .idb-Datei des Projekts. (Abhängigkeitsinformationen Teilen mit der Quelldatei von welcher Klassendefinition abhängt und welcher .h-Datei die Definition befindet sich im.) Nachfolgende Kompilierungen verwenden die in der .idb-Datei gespeicherte Informationen um zu bestimmen, ob eine Quelldatei kompiliert werden muss, auch wenn es sich um eine geänderte .h-Datei enthält.

> [!NOTE]
>  Die minimale Neuerstellung basiert auf Klassendefinitionen, die sich zwischen Includedateien nicht ändern. Klassendefinitionen müssen für ein Projekt global sein (es sollte nur eine Definition für eine bestimmte Klasse vorhanden sein), da die Abhängigkeitsinformationen in der .idb-Datei für das gesamte Projekt erstellt werden. Wenn Sie mehr als eine Definition für eine Klasse in Ihrem Projekt haben, deaktivieren Sie die minimale Neuerstellung.

Da der incremental Linker die Windows-Metadaten in OBJ-Dateien enthalten sind, mithilfe von nicht unterstützt. die [/ZW (Windows-Runtime-Kompilierung)](../../build/reference/zw-windows-runtime-compilation.md) -Option der **/GM** inkompatibel mit  **/ ZW**.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest

1. Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).

1. Klicken Sie auf den Ordner **C/C++** .

1. Klicken Sie auf die **Codegenerierung** Eigenschaftenseite.

1. Ändern der **minimale Neuerstellung aktivieren** Eigenschaft.

### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest

- Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.MinimalRebuild%2A>.

## <a name="see-also"></a>Siehe auch

[Compileroptionen](../../build/reference/compiler-options.md)<br/>
[Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)