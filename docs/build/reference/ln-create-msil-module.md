---
title: -LN (Erstellen von MSIL-Modul) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /LN
dev_langs:
- C++
helpviewer_keywords:
- -LN compiler option [C++]
- /LN compiler option [C++]
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 918b3857c2e6f26a7f2e11614a00049e9b615ea8
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="ln-create-msil-module"></a>/LN (Erstellen eines MSIL-Moduls)
Legt fest, dass ein Assemblymanifest nicht in die Ausgabedatei eingefügt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
/LN  
```  
  
## <a name="remarks"></a>Hinweise  
 Standardmäßig **/ln** ist nicht aktiv (ein Assemblymanifest in die Ausgabedatei eingefügt wird).  
  
 Wenn **/ln** verwendet wird, eines der [/CLR (Common Language Runtime-Kompilierung)](../../build/reference/clr-common-language-runtime-compilation.md) Optionen müssen auch verwendet werden.  
  
 Ein verwaltetes Programm, das keine Assemblymetadaten im Manifest aufweist, wird ein Modul aufgerufen. Beim Kompilieren mit [/c (Kompilieren ohne Verknüpfen)](../../build/reference/c-compile-without-linking.md) und **/ln**, geben Sie [/NOASSEMBLY (Erstellen eines MSIL-Moduls)](../../build/reference/noassembly-create-a-msil-module.md) in der Linkerphase zum Erstellen der Ausgabedatei.  
  
 Sie sollten Protokollierungsmodule erstellen, wenn Sie einen komponentenbasierter Ansatz zum Erstellen von Assemblys möchten.  D. h. können Sie Typen erstellen und diese in Module kompilieren.  Anschließend können Sie eine Assembly aus einem oder mehreren Modulen generieren.  Weitere Informationen zum Erstellen von Assemblys aus Modulen finden Sie unter [NETMODULE-Dateien als Linkereingabe](../../build/reference/netmodule-files-as-linker-input.md) oder [Al.exe (Assembly Linker)](/dotnet/framework/tools/al-exe-assembly-linker).  
  
 Die standarddateierweiterung für ein Modul ist NETMODULE-Datei.  
  
 In [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] Versionen vor Visual C++ 2005 wurde ein Modul mit **/CLR: noAssembly**.  
  
 Der Visual C++-Linker NETMODULE-Dateien als Eingabe akzeptiert und die vom Linker generierte Ausgabedatei ist eine Assembly oder eine NETMODULE-Datei mit keine Abhängigkeit zur Laufzeit auf die NETMODULE-Dateien, die an den Linker eingegeben wurden.  Weitere Informationen finden Sie unter [NETMODULE-Dateien als Eingabe für den Linker](../../build/reference/netmodule-files-as-linker-input.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
-   Geben Sie [/NOASSEMBLY (Erstellen eines MSIL-Moduls)](../../build/reference/noassembly-create-a-msil-module.md) in der Linkerphase zum Erstellen der Ausgabedatei.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Diese Compileroption kann programmgesteuert geändert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)