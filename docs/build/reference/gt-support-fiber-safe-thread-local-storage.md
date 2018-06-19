---
title: -GT (Fiber-sicheren lokalen Thread Speicher unterstützen) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.EnableFiberSafeOptimizations
- /gt
dev_langs:
- C++
helpviewer_keywords:
- /GT compiler option [C++]
- GT compiler option [C++]
- thread-local storage
- static thread-local storage and fiber safety
- -GT compiler option [C++]
- fiber-safe static thread-local storage compiler option [C++]
ms.assetid: 071fec79-c701-432b-9970-457344133159
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 493199cf4d5e66a866fbaa87aafc4098c3114cf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32373828"
---
# <a name="gt-support-fiber-safe-thread-local-storage"></a>/GT (Fiber-sicheren lokalen Thread-Speicher unterstützen)
Unterstützt Fiber-Sicherheit für Daten, die mithilfe von statischen lokalen Threadspeicher, d. h. mit zugeordneten Daten zugeordnet, `__declspec(thread)`.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GT  
```  
  
## <a name="remarks"></a>Hinweise  
 Daten mit deklariert `__declspec(thread)` durch einen lokalen Threadspeicher (TLS)-Array verwiesen wird. Das TLS-Array ist ein Array von Adressen, die das System für jeden Thread beibehält. Jede Adresse in diesem Array gibt den Speicherort der lokalen Thread-Speicher.  
  
 Eine Fiber ist ein einfaches Objekt, das besteht aus einem Stapel und einem Registerkontext und kann in verschiedenen Threads geplant werden. Eine Fiber kann auf einen beliebigen Thread ausgeführt. Da eine Fiber ausgelagert abrufen kann und höher auf einen anderen Thread neu gestartet, die Adresse des TLS-Arrays muss nicht zwischengespeichert oder optimiert werden als gemeinsamen Teilausdrucks über einen Funktionsaufruf hinweg (finden Sie unter der [/Og (globale Optimierungen)](../../build/reference/og-global-optimizations.md) option Details). **/ Gt** verhindert diese Optimierungen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die **Optimierung** Eigenschaftenseite.  
  
4.  Ändern der **Fiber-sicheren Optimierungen aktivieren** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnableFiberSafeOptimizations%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)