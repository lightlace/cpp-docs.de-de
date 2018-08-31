---
title: -GA (für Windows-Anwendung optimieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
dev_langs:
- C++
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 61bf8844a5471a97214ca6f3d3b5b473c9cd6217
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43194662"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Für Windows-Anwendung optimieren)
Die Ergebnisse in eine effizientere Code für eine .exe-Datei für den Zugriff auf lokalen Threadspeicher (TLS) Variablen.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GA  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ GA** beschleunigt den Zugriff auf Daten, die mit deklariert [__declspec(thread)](../../cpp/declspec.md) in einem Windows-Programm. Wenn diese Option festgelegt ist, die [__tls_index](/windows/desktop/ProcThread/thread-local-storage) Makro wird davon ausgegangen, dass 0 sein.  
  
 Mithilfe von **/GA** für eine DLL-Datei in die Generierung von fehlerhaftem Code führen kann.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Working with Project Properties (Arbeiten mit Projekteigenschaften)](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)