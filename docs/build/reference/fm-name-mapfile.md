---
title: -Fm (Name der Zuordnungsdatei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
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
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a5111291ea92b8650896faf3117f0056510e5ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
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