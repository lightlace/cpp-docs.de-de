---
title: "-GZ (Aktivieren der Stapel Frame-Fehlerprüfungen zur Laufzeit überprüft) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /gz
dev_langs: C++
helpviewer_keywords:
- -GZ compiler option [C++]
- release-build errors
- /GZ compiler option [C++]
- GZ compiler option [C++]
- debug builds, catch release-build errors
ms.assetid: b3efeeff-d5e3-4057-91c9-f6fc73d0270c
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f3e4dc59154d64d79db0f4d15471b51ce67bed58
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="gz-enable-stack-frame-run-time-error-checking"></a>/GZ (Laufzeitfehlerüberprüfung für Stapelrahmen aktivieren)
Führt die gleichen Vorgänge wie die [/RTC (Run-Time Checks Fehler)](../../build/reference/rtc-run-time-error-checks.md) Option. Veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GZ  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ GZ** ist nur für die Verwendung in einer nicht optimierten ([/Od (deaktivieren (Debuggen))](../../build/reference/od-disable-debug.md)) erstellen.  
  
 **/ GZ** ist veraltet, da Visual Studio 2005; verwenden Sie [/RTC (Run-Time Checks Fehler)](../../build/reference/rtc-run-time-error-checks.md) stattdessen. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
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