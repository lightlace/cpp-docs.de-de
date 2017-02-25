---
title: "/c (Kompilieren ohne Verkn&#252;pfen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/c"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/c (Compileroption) [C++]"
  - "c (Compileroption) [C++]"
  - "-c (Compileroption) [C++]"
  - "cl.exe-Compiler, Kompilieren ohne Verknüpfen"
  - "Unterdrücken der Verknüpfung"
ms.assetid: 8017fc3d-e5dd-4668-a1f7-3120daa95d20
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /c (Kompilieren ohne Verkn&#252;pfen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Mit dieser Option wird der automatische LINK\-Aufruf verhindert.  
  
## Syntax  
  
```  
/c  
```  
  
## Hinweise  
 Beim Kompilieren mit **\/c** werden nur OBJ\-Dateien erstellt.  Sie müssen **LINK** explizit mit den entsprechenden Dateien und Optionen aufrufen, um die Verknüpfungsphase des Erstellungsvorgangs auszuführen.  
  
 Alle in der Entwicklungsumgebung erstellten internen Projekte verwenden standardmäßig die Option **\/c**.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
-   Diese Option ist in der Entwicklungsumgebung nicht verfügbar.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Weitere Informationen zur programmgesteuerten Festlegung dieser Compileroption finden Sie unter <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.CompileOnly*>.  
  
## Beispiel  
 Mit dem folgenden Befehl werden die Objektdateien FIRST.obj und SECOND.obj erstellt.  Die Datei THIRD.obj wird ignoriert.  
  
```  
CL /c FIRST.C SECOND.C THIRD.OBJ  
```  
  
 Um eine ausführbare Datei zu erstellen, müssen Sie **LINK** aufrufen:  
  
```  
LINK firsti.obj second.obj third.obj /OUT:filename.exe  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)