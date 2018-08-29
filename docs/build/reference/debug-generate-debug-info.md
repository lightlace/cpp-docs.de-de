---
title: -DEBUG (Debuginfo generieren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCLinkerTool.GenerateDebugInformation
- /debug
dev_langs:
- C++
helpviewer_keywords:
- DEBUG linker option
- /DEBUG linker option
- -DEBUG linker option
- PDB files
- debugging [C++], debug information files
- generate debug info linker option
- pdb files, generating debug info
- .pdb files, generating debug info
- debugging [C++], linker option
- program databases [C++]
ms.assetid: 1af389ae-3f8b-4d76-a087-1cdf861e9103
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 11b3799447e160a56d73441b60215f1dfcb3e227
ms.sourcegitcommit: f7703076b850c717c33d72fb0755fbb2215c5ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2018
ms.locfileid: "43132134"
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Debuginfo generieren)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>Hinweise  

Die **/DEBUG** Option werden Debuginformationen für die ausführbare Datei erstellt.    
  
Der Linker stellt die Debuginformationen in einer Programmdatenbankdatei (PDB). Aktualisiert die PDB-Datei bei nachfolgenden Builds des Programms.  
  
Eine ausführbare Datei (.exe-Datei oder DLL) erstellt, die für das Debuggen enthält den Namen und Pfad der entsprechenden PDB. Der Debugger liest der eingebettete Name und die PDB-Datei verwendet, wenn Sie das Programm zu debuggen. Der Linker den Basisnamen des Programms und der Dateierweiterung ".pdb" verwendet, um die Programm-Datenbankname und bettet den Pfad, in dem es erstellt wurde. Um diese Standardeinstellung zu überschreiben, legen [/PDB](../../build/reference/pdb-use-program-database.md) , und geben Sie einen anderen Dateinamen an.  

Die **/Debug: Fastlink** Option ist in Visual Studio 2017 und höher verfügbar. Durch diese Option wird die private Symbolinformationen in die Kompilierung der einzelnen Produkte verwendet, um die ausführbare Datei zu erstellen. Es wird eine eingeschränkte PDB-Datei, die Indizes in die Debuginformationen in den Objektdateien und Bibliotheken, die zum Erstellen der ausführbaren Datei, anstatt eine vollständige Kopie generiert. Diese Option kann zwei bis vier Mal so schnell wie die vollständige PDB-Generierung verknüpfen, und es wird empfohlen, wenn Sie lokal debuggen, und die Build-Produkte zur Verfügung haben. Diese eingeschränkte PDB kann nicht verwendet werden, für das Debuggen, wenn die erforderlichen Build-Produkte sind nicht verfügbar, z. B. wenn die ausführbare Datei auf einem anderen Computer bereitgestellt wird. Das mspdbcmf.exe-Tool können Sie in einer Developer-Eingabeaufforderung um eine vollständige PDB-Datei aus dieser begrenzte PDB-Datei zu generieren. Verwenden Sie in Visual Studio die Menüelemente Projekt oder Build zum Generieren von einer vollständigen PDB-Datei, um eine vollständige PDB-Datei für das Projekt oder Projektmappe zu erstellen.  
  
Die **/Debug: Full** Option alle privaten Symbolinformationen aus einzelnen Kompilierung-Produkten (Objektdateien und Bibliotheken) in einer einzelnen PDB-Datei verschoben, und kann der zeitaufwändigste Teil des Links. Allerdings kann die vollständige PDB-Datei verwendet werden, um die ausführbare Datei zu debuggen, wenn keine anderen Build-Produkte sind verfügbar, z. B. wenn die ausführbare Datei bereitgestellt wird.  
  
Die **/DEBUG: keine** Option erzeugt eine PDB-Datei nicht.  
  
Beim Angeben von **/DEBUG** mit keine zusätzlichen Optionen, der Linker standardmäßig **/Debug: Full** für Befehlszeilen- und Makefile-Builds, die Daten für Version erstellt werden sollen, in der Visual Studio-IDE, und für Debug und Release in Visual Studio 2015 und früheren Versionen erstellt. Ab Visual Studio 2017 ist das Buildsystem in der IDE standardmäßig **/Debug: Fastlink** beim Angeben der **/DEBUG** option für Debugbuilds. Um Abwärtskompatibilität zu gewährleisten, werden anderen Standardwerte unverändert.  
  
Des Compilers [C7-kompatibel](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Z7) Option veranlasst den Compiler an, die Debuginformationen in die OBJ-Dateien zu belassen. Sie können auch die [Programmdatenbank](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Zi)-Compileroption, um die Debuginformationen in eine PDB-Datei für die OBJ-Datei zu speichern. Der Linker sucht des Objekts PDB-Datei zuerst in den absoluten Pfad, in der OBJ-Datei geschrieben, und klicken Sie dann in das Verzeichnis, die die OBJ-Datei enthält. Sie können nicht die PDB-Dateinamen oder den Speicherort, an den Linker angeben.  
  
[/ INCREMENTAL](../../build/reference/incremental-link-incrementally.md) wird impliziert, wenn "/ Debug" angegeben wird.  
  
/ DEBUG werden die Standardwerte für die ["/ OPT"](../../build/reference/opt-optimizations.md) können von REF in NOREF und von ICF NOICF, damit Sie die ursprünglichen Standardwerte können Sie explizit/OPT: REF "oder" / OPT: ICF angeben müssen.  
  
Es ist nicht möglich, erstellen eine .exe oder .dll, die Debuginformationen enthält. Debuggen von Informationen wird immer in eine OBJ- oder PDB-Datei platziert.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Debuggen** Eigenschaftenseite.  
  
4.  Ändern der **Debuginfo generieren** Eigenschaft, um PDB-Generierung zu aktivieren. Dies ermöglicht die/Debug: Fastlink standardmäßig in Visual Studio 2017.  
  
4.  Ändern der **vollständige Programmdatenbankdatei erstellen** Eigenschaft/Debug: full für vollständige PDB-Generierung für jede inkrementelle Builds aktivieren.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
