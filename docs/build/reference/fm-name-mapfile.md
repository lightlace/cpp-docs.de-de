---
title: -Fm (Name der Zuordnungsdatei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /fm
dev_langs:
- C++
helpviewer_keywords:
- -Fm compiler option [C++]
- mapfiles [C++], creating linker
- files [C++], creating map
- Fm compiler option [C++]
- /Fm compiler option [C++]
ms.assetid: 8154448a-93a7-4546-8e4c-5c44d0aff45d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94a499b943fcd3213aa76876c65c3aac2dd79060
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32374276"
---
# <a name="fm-name-mapfile"></a>/Fm (Name der Zuordnungsdatei)
Weist den Linker erstellen eine Zuordnungsdatei mit einer Liste von Segmenten in der Reihenfolge, in der sie in der entsprechenden .exe-Datei oder DLL angezeigt werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Fmpathname  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig erhält die Zuordnungsdatei den Basisnamen der entsprechenden C- oder C++-Quelldatei mit ein. Ordnen Sie die Erweiterung.  
  
 Angeben von **/FM** hat denselben Effekt, als ob Sie angegeben hatten die [/Map (Zuordnungsdatei generieren)](../../build/reference/map-generate-mapfile.md) (Linkeroption).  
  
 Bei Angabe von [/c (Kompilieren ohne Verknüpfen)](../../build/reference/c-compile-without-linking.md) unterdrücken Sie verknüpfen, **/FM** hat keine Auswirkungen.  
  
 Globale Symbole in eine Zuordnungsdatei befinden sich normalerweise eine oder mehrere führende Unterstriche, da der Compiler einen führenden Unterstrich Variablennamen hinzufügt. Viele globale Symbole, die in die Zuordnungsdatei ein angezeigt werden, werden intern vom Compiler und die Standardbibliotheken verwendet.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)