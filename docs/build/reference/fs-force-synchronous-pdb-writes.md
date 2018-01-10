---
title: "-FS (erzwingen synchroner PDB-Schreibvorgänge) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /FS
dev_langs: C++
helpviewer_keywords:
- -FS compiler option [C++]
- /FS compiler option [C++]
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cec8aa3d1b3417b6bfcb35757ac4a4a51961e16b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fs-force-synchronous-pdb-writes"></a>/FS (Erzwingen synchroner PDB-Schreibvorgänge)
Erzwingt, dass Schreibvorgänge an die Programmdatenbankdatei (PDB) – erstellt durch [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md) oder [/Zi](../../build/reference/z7-zi-zi-debug-information-format.md)– über MSPDBSRV serialisiert werden soll. EXE-DATEI.  
  
## <a name="syntax"></a>Syntax  
  
```  
/FS  
```  
  
## <a name="remarks"></a>Hinweise  
 In der Standardeinstellung Wenn **/Zi** oder **/Zi** angegeben ist, wird der Compiler sperrt PDB-Dateien, um Typinformationen und symbolische Debuginformationen zu schreiben. Dadurch kann der Compiler bei einer großen Anzahl von Typen die Typinformationen erheblich schneller generieren. Wenn ein anderer Prozess, beispielsweise ein Antivirenprogramm, die PDB Datei vorübergehend sperrt, können Schreibvorgänge des Compilers möglicherweise nicht ausgeführt werden, sodass ein schwerer Fehler auftritt. Dieses Problem kann auch auftreten, wenn mehrere Kopien von cl.exe auf dieselbe PDB Datei zugreifen. Das kann der Fall sein, wenn die Projektmappe unabhängige Projekte enthält, welche die gleichen Zwischenverzeichnisse oder Ausgabeverzeichnisse verwenden, während parallele Builds aktiviert sind. Die **/FS** -Compileroption verhindert, dass den Compiler die PDB-Datei zu sperren und erzwingt, dass Schreibvorgänge MSPDBSRV durchlaufen. EXE-Datei, die Zugriff serialisiert. Dadurch werden aber nicht alle Fehler verhindert, die auftreten können, wenn mehrere Instanzen von cl.exe gleichzeitig auf die PDB-Datei zugreifen, und zudem dauern Builds erheblich länger. Es empfiehlt sich, die Projektmappe so zu ändern, dass unabhängige Projekte in getrennte Zwischen- und Ausgabeorte schreiben, oder eines der Projekte von den anderen abhängig zu machen, um serialisierte Projekt-Builds zu erzwingen.  
  
 Die [/MP](../../build/reference/mp-build-with-multiple-processes.md) -Option aktiviert **/FS** standardmäßig.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Wählen Sie die **C/C++-** Ordner.  
  
3.  Wählen Sie die **Befehlszeile** Eigenschaftenseite.  
  
4.  Ändern der **Zusatzoptionen** Eigenschaft einschließen `/FS` und wählen Sie dann **OK**.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)