---
title: -Doc (Verarbeiten von Dokumentationskommentaren) (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.GenerateXMLDocumentationFiles
- /doc
- VC.Project.VCCLCompilerTool.XMLDocumentationFileName
dev_langs:
- C++
helpviewer_keywords:
- /doc compiler option [C++]
- comments, C++ code
- XML documentation, comments in source files
- -doc compiler option [C++]
ms.assetid: b54f7e2c-f28f-4f46-9ed6-0db09be2cc63
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 899ff6b774c365ce9df3019ef5ba6d08d0d7b93d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32371280"
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