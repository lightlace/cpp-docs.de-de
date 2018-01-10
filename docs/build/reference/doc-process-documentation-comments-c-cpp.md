---
title: -Doc (Verarbeiten von Dokumentationskommentaren) (C/C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs: C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8737c0e33d33fe062d9a07f18d9005e58463f5b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="doc-process-documentation-comments-cc"></a>/doc (Verarbeiten von Dokumentationskommentaren) (C/C++)
Bewirkt, dass der Compiler Dokumentationskommentare in Quellcodedateien und eine XDC-Datei für jede Quelldatei zu erstellen, die Dokumentationskommentare verfügt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/doc[name]  
```  
  
## <a name="arguments"></a>Argumente  
 `name`  
 Der Name der XDC-Datei, die der Compiler erstellt. Nur gültig, wenn in der Kompilierung eine CPP-Datei übergeben wird.  
  
## <a name="remarks"></a>Hinweise  
 Der XDC-Dateien werden in eine XML-Datei mit xdcmake.exe verarbeitet. Weitere Informationen finden Sie unter [XDCMake-Verweis](../../ide/xdcmake-reference.md).  
  
 Sie können den Quellcodedateien Dokumentationskommentare hinzufügen. Weitere Informationen finden Sie unter [empfohlene Tags für Dokumentationskommentare](../../ide/recommended-tags-for-documentation-comments-visual-cpp.md).  
  
 Um die generierte XML-Datei mit IntelliSense verwenden, stellen Sie den Dateinamen der XML-Datei, die die Assembly, die Sie verwenden möchten, zu unterstützen, und fügen Sie die XML-Datei im gleichen Verzeichnis wie die Assembly übereinstimmt. Wenn die Assembly in Visual Studio-Projekt verwiesen wird, wird auch die XML-Datei gefunden. Weitere Informationen finden Sie unter [Verwenden von IntelliSense](/visualstudio/ide/using-intellisense) und [XML-Codekommentaren](/visualstudio/ide/supplying-xml-code-comments).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Erweitern Sie die **Konfigurationseigenschaften** Knoten.  
  
3.  Erweitern Sie die **C/C++-** Knoten.  
  
4.  Wählen Sie die **Ausgabedateien** Eigenschaftenseite.  
  
5.  Ändern der **Generieren von XML-Dokumentationsdateien** Eigenschaft.  
  
### <a name="to-set-this-linker-option-programmatically"></a>So legen Sie diese Linkeroption programmgesteuert fest  
  
1.  Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GenerateXMLDocumentationFiles%2A>.  
  
## <a name="see-also"></a>Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)