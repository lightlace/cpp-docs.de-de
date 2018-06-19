---
title: -GL (Optimierung des ganzen Programms) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ce972b6e7254ad7454f8e8799283588f0fdd5270
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32376272"
---
# <a name="gl-whole-program-optimization"></a>/GL (Optimierung des ganzen Programms)
Aktiviert die Optimierung des gesamten Programms.  
  
## <a name="syntax"></a>Syntax  
  
```  
/GL[-]  
```  
  
## <a name="remarks"></a>Hinweise  
 Optimierung des gesamten Programms kann der Compiler Optimierungen mit Informationen zu allen Modulen im Programm ausführen. Ohne Optimierung des gesamten Programms Optimierungen durchgeführt werden, auf einer pro Modul (Kompiliereinheit).  
  
 Optimierung des gesamten Programms ist standardmäßig deaktiviert und muss explizit aktiviert werden. Allerdings ist es auch möglich, die explizit mit deaktiviert **/GL-**.  
  
 Mit Informationen zu allen Modulen kann der compiler  
  
-   Optimieren Sie die Verwendung von Registern Funktion hinweg.  
  
-   Führen Sie besser nachverfolgen von Änderungen an globalen Daten ermöglicht eine Reduzierung der Anzahl von Lade- und Speichervorgänge aus.  
  
-   Führen Sie besser nachverfolgen, die mögliche Gruppe von Elementen, die geändert, indem ein Zeiger dereferenziert, reduziert die Anzahl von Lade- und Speichervorgänge aus.  
  
-   Inline eine Funktion in einem Modul, auch wenn die Funktion in einem anderen Modul definiert ist.  
  
 OBJ-Dateien mit erzeugten **/GL** wird nicht als solche Linker-Dienstprogramme [EDITBIN](../../build/reference/editbin-reference.md) und [DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
 Wenn Sie das Programm mit Kompilieren **/GL** und [/c](../../build/reference/c-compile-without-linking.md), Sie sollten die/LTCG (Linkeroption) verwenden, um die Ausgabedatei zu erstellen.  
  
 [/ Zi](../../build/reference/z7-zi-zi-debug-information-format.md) kann nicht verwendet werden, mit   **/GL**  
  
 Das Format der Dateien mit erzeugten **/GL** in der aktuellen Version möglicherweise nicht von nachfolgenden Versionen von Visual C++ gelesen werden. Sie sollten eine LIB-Datei besteht aus der OBJ-Dateien, die mit erzeugt wurden nicht versenden **/GL** es sei denn, Sie so liefern Sie Kopien der LIB-Datei für alle Versionen von Visual C++ in Kauf zu nehmen Sie Ihre Benutzer verwenden, jetzt und in der Zukunft erwarten.  
  
 OBJ-Dateien mit erzeugten **/GL** und der vorkompilierten Headerdateien sollte nicht verwendet werden, um eine LIB-Datei zu erstellen, es sei denn, die LIB-Datei auf dem gleichen Computer verknüpft werden, die erstellt die **/GL** OBJ-Datei. Informationen aus der OBJ-Datei vorkompilierte Headerdatei ist zum Zeitpunkt der Verknüpfung erforderlich.  
  
 Weitere Informationen zu den Optimierungen mit verfügbar und die Einschränkungen der Optimierung des gesamten Programms, finden Sie unter [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **/ GL** auch macht Profil geführte Optimierung verfügbar; siehe/LTCG.  Beim Kompilieren für Profilgesteuerte Optimierungen und Funktion, die Reihenfolge von Ihrem Profilgesteuerte Optimierungen werden sollen, müssen Sie Kompilieren mit [/Gy](../../build/reference/gy-enable-function-level-linking.md) oder eine Compileroption, die/Gy impliziert.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Finden Sie unter [/LTCG (Link-Time Code Generation)](../../build/reference/ltcg-link-time-code-generation.md) Informationen zum angeben **/GL** in der Entwicklungsumgebung.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)