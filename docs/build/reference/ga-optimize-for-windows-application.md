---
title: "-GA (für Windows-Anwendung optimieren) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
dev_langs: C++
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 611704120ec99280e0701e06e0e4bd45c95330d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Für Windows-Anwendung optimieren)
/ / Ergibt effizienteren Code für eine .exe-Datei für den Zugriff auf lokalen Threadspeicher (TLS) Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ GA** beschleunigt den Zugriff auf Daten mit deklariert [__declspec(thread)](../../cpp/declspec.md) in einem Windows-basierten Programm. Wenn diese Option festgelegt ist, die [__tls_index](http://msdn.microsoft.com/library/windows/desktop/ms686749) Makro wird davon ausgegangen, dass 0 sein.  
  
 Mit **/GA** für eine DLL-Datei in die Generierung von ungültigem Code führen kann.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)