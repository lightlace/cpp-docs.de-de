---
title: -IDLOUT (Namen der MIDL-Ausgabedateien) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /idlout
- VC.Project.VCLinkerTool.MergedIDLBaseFileName
dev_langs:
- C++
helpviewer_keywords:
- MIDL, output file names
- .idl files, path
- MIDL
- /IDLOUT linker option
- IDL files, path
- -IDLOUT linker option
- IDLOUT linker option
ms.assetid: 10d00a6a-85b4-4de1-8732-e422c6931509
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7eeb7af3d19a57b6948f867df87b8d04d0397b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376061"
---
# <a name="idlout-name-midl-output-files"></a>/IDLOUT (Namen der MIDL-Ausgabedateien)
```  
/IDLOUT:[path\]filename  
```  
  
## <a name="parameters"></a>Parameter  
 *path*  
 Ein absoluter oder relativer Pfad-Spezifikation. Durch Angabe eines Pfads, wirkt sich auf lediglich der Speicherort der IDL-Datei; Alle anderen Dateien befinden sich im Projektverzeichnis.  
  
 *filename*  
 Gibt den Namen der IDL-Datei, die vom MIDL-Compiler erstellt. Keine Dateierweiterung wird davon ausgegangen, dass; Geben Sie *Filename*IDL gegebenenfalls eine IDL-Erweiterung.  
  
## <a name="remarks"></a>Hinweise  
 Die Option/IDLOUT gibt den Namen und die Erweiterung der IDL-Datei.  
  
 MIDL-Compiler wird durch die Visual C++-Linker aufgerufen, wenn Verknüpfen von Projekten mit der [Modul](../../windows/module-cpp.md) Attribut.  
  
 / IDLOUT gibt auch an die Dateinamen der anderen Ausgabedateien der MIDL-Compiler zugeordnet:  
  
-   *FileName*TLB-Datei  
  
-   *FileName*_p.c  
  
-   *FileName*_i.c  
  
-   *FileName*h  
  
 *FileName* ist der Parameter, die an/IDLOUT übergeben. Wenn [/TLBOUT](../../build/reference/tlbout-name-dot-tlb-file.md) angegeben ist, wird die TLB-Datei erhalten den Namen vom/TLBOUT *Filename*.  
  
 Wenn Sie weder/IDLOUT noch/TLBOUT angeben, wird der Linker vc70.tlb, vc70.idl, vc70_p.c, vc70_i.c und vc70.h erstellt.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **eingebettete IDL** Eigenschaftenseite.  
  
4.  Ändern der **Merge IDL-Basisdateiname** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.MergedIDLBaseFileName%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Optionen des Linkers](../../build/reference/linker-options.md)   
 [/ IGNOREIDL (Attribute nicht in verarbeiten "MIDL")](../../build/reference/ignoreidl-don-t-process-attributes-into-midl.md)   
 [/ MIDL (Optionen für MIDL-Befehlszeile festlegen)](../../build/reference/midl-specify-midl-command-line-options.md)   
 [Erstellen eines attributierten Programms](../../windows/building-an-attributed-program.md)