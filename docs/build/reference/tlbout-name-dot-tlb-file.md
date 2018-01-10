---
title: -TLBOUT (Name. TLB-Datei) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.TypeLibraryFile
- /tlbout
dev_langs: C++
helpviewer_keywords:
- tlb files, renaming
- TLBOUT linker option
- /TLBOUT linker option
- .tlb files, renaming
- -TLBOUT linker option
ms.assetid: 0df6d078-2e48-46c9-a1a5-02674d85dce8
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c898121a4ac29cc05022504ebfe33949b44eca7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tlbout-name-tlb-file"></a>/TLBOUT (TLB-Datei benennen)
```  
/TLBOUT:[path\]filename  
```  
  
## <a name="remarks"></a>Hinweise  
 Dabei gilt:  
  
 *path*  
 Eine absolute oder relative Pfadangabe für, in dem die TLB-Datei erstellt werden soll.  
  
 *filename*  
 Gibt den Namen der TLB-Datei, die vom MIDL-Compiler erstellt. Keine Dateierweiterung wird davon ausgegangen, dass; Geben Sie *Filename*tlb ggf. eine Erweiterung ".tlb".  
  
## <a name="remarks"></a>Hinweise  
 Die Option/TLBOUT gibt den Namen und die Erweiterung der TLB-Datei.  
  
 MIDL-Compiler wird durch die Visual C++-Linker aufgerufen, wenn Verknüpfen von Projekten mit der [Modul](../../windows/module-cpp.md) Attribut.  
  
 Wenn/TLBOUT nicht angegeben wird, erhalten die TLB-Datei den Namen von [/IDLOUT](../../build/reference/idlout-name-midl-output-files.md) *Filename*. / IDLOUT nicht angegeben ist, wird die TLB-Datei vc70.tlb aufgerufen werden.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.  
  
4.  Ändern der **Typbibliothek** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TypeLibraryFile%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (Attribute nicht in verarbeiten "MIDL")](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (Optionen für MIDL-Befehlszeile festlegen)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)