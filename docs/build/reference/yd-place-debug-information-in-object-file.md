---
title: -Yd (Debuginformationen in Objektdatei) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /yd
dev_langs:
- C++
helpviewer_keywords:
- /Yd compiler option [C++]
- -Yd compiler option [C++]
- debugging [C++], debug information files
- Yd compiler option [C++]
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39b03b0faf975caba8c5a287c88afcdf53f7a71f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="yd-place-debug-information-in-object-file"></a>/Yd (Debuginformationen in Objektdatei ablegen)
Vollständige Debuginformationen in allen Objektdateien Leerzeichen aus einer vorkompilierten Headerdatei (PCH)-Datei bei Verwendung mit erstellt die ["/ Yc"](../../build/reference/yc-create-precompiled-header-file.md) und ["/ Z7"](../../build/reference/z7-zi-zi-debug-information-format.md) Optionen. Veraltet.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Yd  
```  
  
## <a name="remarks"></a>Hinweise  
 **/ Yd ablegen** ist veraltet. [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] unterstützt jetzt mehrere Objekte, die beim Schreiben in eine einzelne PDB-Datei verwenden **/Zi** stattdessen. Eine Liste der veralteten Compileroptionen, finden Sie unter **veraltete und entfernte Compileroptionen** in [Compileroptionen nach Kategorien sortiert](../../build/reference/compiler-options-listed-by-category.md).  
  
 Verwenden, es sei denn, Sie eine Bibliothek mit-Debuginformationen zu verteilen müssen, die [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) Option statt **"/ Z7"** und **/Yd ablegen**.  
  
 Vollständige Debuginformationen in jeder OBJ-Datei gespeichert ist nur erforderlich, um Bibliotheken zu verteilen, die Debuginformationen enthalten. Er verlangsamt die Kompilierung und erheblichen Speicherplatz benötigt. Wenn **"/ Yc"** und **"/ Z7"** werden verwendet, ohne **/Yd ablegen**, speichert der Compiler allgemeine Debuginformationen in der ersten OBJ-Datei aus der PCH-Datei erstellt. Der Compiler fügt diese Informationen nicht in OBJ-Dateien, die anschließend aus der PCH-Datei erstellt ein; Es fügt Querverweise auf die Informationen ein. Unabhängig davon, wie viele OBJ-Dateien die PCH-Datei verwenden enthält nur eine OBJ-Datei die allgemeinen Debuginformationen.  
  
 Obwohl diese Standardeinstellung führt zu Buildzeiten schneller und Speicherplatz Anforderungen reduziert, ist es nicht erwünscht, wenn eine kleine Änderung erfordert das Neuerstellen der OBJ-Datei mit allgemeinen Informationen über das Debuggen. In diesem Fall muss der Compiler alle OBJ-Dateien, die mit Querverweisen, in der ursprünglichen OBJ-Datei neu erstellen. Wenn eine gemeinsame PCH-Datei von verschiedenen Projekten verwendet wird, ist außerdem Abhängigkeit von Querverweisen auf einem einzelnen OBJ-Datei schwierig.  
  
 Weitere Informationen zu vorkompilierten Headern finden Sie unter:  
  
-   [/Y (Vorkompilierte Header)](../../build/reference/y-precompiled-headers.md)  
  
-   [Erstellen vorkompilierter Headerdateien](../../build/reference/creating-precompiled-header-files.md)  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf den Ordner **C/C++** .  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile** .  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="examples"></a>Beispiele  
 Angenommen, Sie haben zwei Bankdateien F.cpp und g.cpp zu, mit jeweils diese **#include** Anweisungen:  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 Der folgende Befehl erstellt den vorkompilierten Header ETC.pch und die Objektdatei F.obj:  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 Die Objektdatei F.obj enthält Typ und Symbolinformationen für WINDOWS.h und etc.h ein (und alle anderen darin enthaltenen Headerdateien). Jetzt können Sie den vorkompilierten Header ETC.pch verwenden, um die Quelldatei g.cpp zu kompilieren:  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 Die Objektdatei ein einfach verweist diese Informationen in der Datei F.obj jedoch enthält keine Debuginformationen für den vorkompilierten Header. Beachten Sie, dass Sie mit der Datei F.obj verknüpft werden müssen.  
  
 Wenn der vorkompilierte Header nicht mit kompiliert wurde **"/ Z7"**, noch können Sie sie in späteren Kompilierungen zusammen mit **"/ Z7"**. Allerdings wird die Debuginformationen in der aktuellen Objektdatei platziert, und lokale Symbole für Funktionen und in der vorkompilierten Headerdatei definierten Typen sind nicht verfügbar, die im Debugger.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)