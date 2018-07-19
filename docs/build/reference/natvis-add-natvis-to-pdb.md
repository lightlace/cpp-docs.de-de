---
title: -NATVIS (PDB-Datei Natvis hinzu) | Microsoft Docs
ms.date: 08/10/2017
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /natvis
- VC.Project.VCLinkerTool.ImportLIbrary
dev_langs:
- C++
helpviewer_keywords:
- NATVIS linker option
- /NATVIS linker option
- -NATVIS linker option
- Add Natvis file to PDB
ms.assetid: 8747fc0c-701a-4796-bb4d-818ab4465cca
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3bce34095aec1558d2466447770a8ac4c46528f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32377101"
---
# <a name="natvis-add-natvis-to-pdb"></a>/ NATVIS (PDB-Datei Natvis hinzu)
  
> / NATVIS:*Dateiname*  
  
## <a name="parameters"></a>Parameter  
  
*filename*  
Eine Natvis-Datei der PDB-Datei hinzu. Der Debugger-Visualisierungen wird in der Natvis-Datei in die PDB-Datei eingebettet.  
  
## <a name="remarks"></a>Hinweise  
  
Die Option /NATVIS bettet die Debugger-Visualisierungen, die in der Natvis-Datei definierten *Filename* in der PDB-Datei, die von LINK generierte. Dadurch kann der Debugger die Visualisierungen unabhängig von der natvis-Datei angezeigt werden. Sie können mehrere /NATVIS-Optionen verwenden, um mehr als eine Natvis-Datei in der generierten PDB-Datei einzubetten.  
  
"LINK" berücksichtigt /NATVIS nicht Erstellung eine PDB-Datei mithilfe einer [/DEBUG](../../build/reference/debug-generate-debug-info.md) Option. Informationen bei der Erstellung und Verwendung von natvis-Dateien finden Sie unter [erstellen benutzerdefinierte Ansichten von systemeigenen Objekten in Visual Studio-Debugger](/visualstudio/debugger/create-custom-views-of-native-objects).  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **Befehlszeile** Eigenschaftenseite in der **Linker** Ordner.  
  
3.  Fügen Sie der /NATVIS-Option aus, um die **Zusatzoptionen** Textfeld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Diese Option muss keine programmatische Entsprechung.  
  
## <a name="see-also"></a>Siehe auch  
  
[Erstellen Sie benutzerdefinierte Ansichten von systemeigenen Objekten in Visual Studio-debugger](/visualstudio/debugger/create-custom-views-of-native-objects)  
[Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)  
[Linkeroptionen](../../build/reference/linker-options.md)