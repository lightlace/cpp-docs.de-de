---
title: -DEBUG (Debuginfo generieren) | Microsoft Docs
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
ms.openlocfilehash: f93c47a0f96cf0b75b453bcea97212d4ab2fd6d3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="debug-generate-debug-info"></a>/DEBUG (Debuginfo generieren)
```  
/DEBUG[:{FASTLINK|FULL|NONE}]  
```  
  
## <a name="remarks"></a>Hinweise  

Die **/DEBUG** Option werden Debuginformationen für die ausführbare Datei erstellt.    
  
Der Linker stellt die Debuginformationen in einer Programmdatenbankdatei (PDB). Aktualisiert die PDB-Datei bei nachfolgenden Builds des Programms.  
  
Eine ausführbare Datei (.exe-Datei oder DLL) erstellt, die für das Debuggen enthält den Namen und Pfad der entsprechenden PDB. Der Debugger liest den eingebetteten Namen und die PDB-Datei verwendet, wenn Sie das Programm debuggen. Der Linker verwendet den Basisnamen des Programms und die Erweiterung PDB-Datei auf die Programmdatenbank benennen und bettet den Pfad, in dem es erstellt wurde. Um diese Standardeinstellung zu überschreiben, legen [/PDB](../../build/reference/pdb-use-program-database.md) , und geben Sie einen anderen Dateinamen an.  

Die **Fastlink** Option private Symbolinformationen in den einzelnen Kompilierung Produkten verwendet, um die ausführbare Datei erstellt wird. Es wird eine begrenzte PDB-Datei, die in der Debuginformationen in den Objektdateien und Bibliotheken, die zum Erstellen der ausführbaren Datei, anstatt eine vollständige Kopie Indizes generiert. Diese Option, die zwischen zwei und vier Mal so schnell wie das vollständige PDB-Generierung verknüpfen kann, und es wird empfohlen, wenn Sie lokal debuggen, und die Build-Produkten zur Verfügung haben. Diese eingeschränkte PDB kann nicht verwendet werden, für das Debuggen, wenn die erforderlichen Build Produkte sind nicht verfügbar, z. B. wenn die ausführbare Datei auf einem anderen Computer bereitgestellt wird. In einem Developer-Eingabeaufforderung können Sie die mspdbcmf.exe-Tool verwenden, um eine vollständige PDB-Datei aus dieser eingeschränkten PDB zu generieren. Verwenden Sie in Visual Studio die Menüelemente Projekt- oder Build zum Generieren von vollständige PDB-Datei um eine vollständige PDB-Datei für das Projekt oder die Projektmappe zu erstellen.  
  
Die **/Debug: Full** Option verschiebt alle privaten Symbolinformationen aus einzelnen Kompilierung Produkten (Objektdateien und Bibliotheken) in eine einzelne PDB-Datei und kann die zeitaufwändigsten Teil des Links. Allerdings kann die vollständige PDB-Datei verwendet werden, um die ausführbare Datei zu debuggen, wenn keine anderen Build Produkte sind verfügbar, z. B. wenn die ausführbare Datei bereitgestellt wird.  
  
Die **/DEBUG: keine** Option werden keine PDB-Datei generiert.  
  
Geben Sie bei **/DEBUG** ohne zusätzliche Optionen der Linker standardmäßig **/Debug: Full** für Befehlszeilen- und Makefile Builds für Version erstellt, in der Visual Studio-IDE und für die Debug- und Release in Visual Studio 2015 und frühere Versionen erstellt. In Visual Studio 2017 ab, das Buildsystem in der IDE standardmäßig **Fastlink** beim Angeben der **/DEBUG** option für Debugbuilds. Um Abwärtskompatibilität zu gewährleisten, werden anderen Standardeinstellungen unverändert.  
  
Des Compilers [C7-kompatibel](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Z7) Option veranlasst den Compiler, lassen Sie die Debuginformationen in den OBJ-Dateien. Sie können auch die [Programmdatenbank](../../build/reference/z7-zi-zi-debug-information-format.md) (/ Zi)-Compileroption, um die Debuginformationen in eine PDB-Datei für die OBJ-Datei zu speichern. Der Linker sucht nach der objektspezifischen PDB zuerst in den absoluten Pfad, der in der OBJ-Datei geschrieben, und klicken Sie dann in das Verzeichnis, die die OBJ-Datei enthält. Sie können keine PDB-Dateinamen oder den Speicherort, an den Linker ein Objekt angeben.  
  
[/ INCREMENTAL](../../build/reference/incremental-link-incrementally.md) wird impliziert, wenn "/ Debug" angegeben wird.  
  
/ DEBUG ändert die Standardwerte für die [/OPT](../../build/reference/opt-optimizations.md) Option von REF in NOREF und ICF in NOICF, damit Sie ggf. die ursprünglichen Standardwerte müssen Sie explizit/OPT: REF "oder" / OPT: ICF angeben.  
  
Es ist nicht möglich, erstellen Sie eine .exe oder .dll, die Debuginformationen enthält. Debuggen von Informationen stets in eine OBJ- oder PDB-Datei gespeichert ist.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Linkeroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [Einstellung von Visual C++-Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **Debuggen** Eigenschaftenseite.  
  
4.  Ändern der **Debuginfo generieren** Eigenschaft, um die Generierung der PDB-Datei zu aktivieren. Dadurch werden Fastlink standardmäßig in Visual Studio 2017.  
  
4.  Ändern der **generieren vollständige Programmdatenbankdatei** Eigenschaft/Debug: full für die vollständige PDB-Generierung für alle inkrementellen Build aktivieren.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.GenerateDebugInformation%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Festlegen von Linkeroptionen](../../build/reference/setting-linker-options.md)   
 [Linkeroptionen](../../build/reference/linker-options.md)
