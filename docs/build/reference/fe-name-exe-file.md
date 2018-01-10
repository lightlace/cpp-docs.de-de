---
title: -Fe (Name der EXE-Datei) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /fe
dev_langs: C++
helpviewer_keywords:
- -Fe compiler option [C++]
- executable files, renaming
- rename file compiler option [C++]
- /Fe compiler option [C++]
- Fe compiler option [C++]
ms.assetid: 49f594fd-5e94-45fe-a1bf-7c9f2abb6437
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 83965ef2bf64f77dbcb1eb9832e7178c30260d16
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="fe-name-exe-file"></a>/Fe (Name der EXE-Datei)
Gibt einen Namen und ein Verzeichnis für die .exe-Datei oder DLL, die vom Compiler erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
/Fepathname  
```  
  
## <a name="remarks"></a>Hinweise  
 Ohne diese Option weist der Compiler der Datei einen Standardnamen, der mit den Basisnamen der ersten Quelle oder das Objekt Datei in der Befehlszeile und der Erweiterung .exe oder .dll angegeben.  
  
 Bei Angabe der[/c (Kompilieren ohne Verknüpfen)](../../build/reference/c-compile-without-linking.md)zum Kompilieren ohne verknüpfen, **/FE** hat keine Auswirkungen.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Weitere Informationen finden Sie unter [arbeiten mit Projekteigenschaften](../../ide/working-with-project-properties.md).  
  
2.  Klicken Sie auf die **Linker** Ordner.  
  
3.  Klicken Sie auf die **allgemeine**Eigenschaftenseite.  
  
4.  Ändern der **Ausgabedatei** Eigenschaft.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.OutputFile%2A>.  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile kompiliert und verknüpft alle C#-Quelldateien im aktuellen Verzeichnis. Die resultierende ausführbare Datei heißt PROCESS.exe und wird im Verzeichnis C:\BIN erstellt.  
  
```  
CL /FeC:\BIN\PROCESS *.C  
```  
  
## <a name="example"></a>Beispiel  
 Die folgende Befehlszeile erstellt eine ausführbare Datei in `C:\BIN` mit den gleichen Basisnamen wie die erste Quelle oder das Objekt Datei:  
  
```  
CL /FeC:\BIN\ *.C  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Ausgabedatei (/ F) Optionen](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)