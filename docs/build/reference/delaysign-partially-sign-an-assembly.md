---
title: -DELAYSIGN (Assembly teilweise Signieren) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /delaysign
- VC.Project.VCLinkerTool.DelaySign
dev_langs:
- C++
helpviewer_keywords:
- /DELAYSIGN linker option
- DELAYSIGN linker option
- -DELAYSIGN linker option
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eda1f426f24dd63684fd6831e2efef6838c43a3d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="delaysign-partially-sign-an-assembly"></a>/DELAYSIGN (Assembly teilweise signieren)
```  
/DELAYSIGN[:NO]  
```  
  
## <a name="remarks"></a>Hinweise  
 wobei  
  
 NEIN  
 Gibt an, dass die Assembly nicht teilweise signiert werden soll.  
  
## <a name="remarks"></a>Hinweise  
 Verwendung **/delaysign /** Wenn nur den öffentlichen Schlüssel in die Assembly eingefügt werden soll. Die Standardeinstellung ist **/delaysign: No**.  
  
 Die **/delaysign /** Option hat keine Auswirkung, wenn nicht mit [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) oder [/keycontainer](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md).  
  
 Wenn Sie eine vollständig signierte Assembly anfordern, wird vom Compiler der Hash der Datei mit dem Manifest (Assemblymetadaten) erstellt und mit dem privaten Schlüssel signiert. Die sich ergebende digitale Signatur wird in der Datei mit dem Manifest gespeichert. Wenn eine Assembly verzögert signiert wird, wird der Linker nicht berechnen und speichern die Signatur, sondern reserviert Speicherplatz in der Datei, damit die Signatur später hinzugefügt werden kann.  
  
 Beispiel für die Verwendung **/delaysign /** können Tester die Assembly im globalen Cache ablegen. Nach dem Testen können Sie die Assembly vollständig signieren, den privaten Schlüssel in der Assembly platziert.  
  
 Finden Sie unter [Assemblys mit starken Namen (Assembly signieren) (C + c++ / CLI)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md) und [Verzögertes Signieren einer Assembly](/dotnet/framework/app-domains/delay-sign-assembly) für Weitere Informationen zum Signieren einer Assemblys.  
  
 Andere Optionen des Linkers, die beeinflussen Generieren der Assembly sind:  
  
-   [/ASSEMBLYDEBUG](../../build/reference/assemblydebug-add-debuggableattribute.md)  
  
-   [/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Option in der **Zusatzoptionen** Feld.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)