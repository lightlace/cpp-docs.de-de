---
title: "/Fp (Name der PCH-Datei)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.PrecompiledHeaderFile"
  - "/fp"
  - "VC.Project.VCCLWCECompilerTool.PrecompiledHeaderFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".pch-Dateien, Benennen"
  - "/Fp (Compileroption) [C++]"
  - "Fp (Compileroption) [C++]"
  - "-Fp (Compileroption) [C++]"
  - "Namen [C++], PCH"
  - "Benennen von vorkompilierten Headerdateien"
  - "PCH-Dateien, Benennen"
  - "Vorkompilierte Headerdateien, Benennen"
ms.assetid: 0fcd9cbd-e09f-44d3-9715-b41efb5d0be2
caps.latest.revision: 12
caps.handback.revision: "12"
ms.author: "corob"
manager: "ghogen"
---
# /Fp (Name der PCH-Datei)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt einen Pfadnamen für einen vorkompilierten Header bereit, der anstelle des Standardpfadnamens verwendet wird.  
  
## Syntax  
  
```  
/Fppathname  
```  
  
## Hinweise  
 Verwenden Sie diese Option zusammen mit [\/Yc \(Datei der vorkompilierten Header erstellen\)](../../build/reference/yc-create-precompiled-header-file.md) oder [\/Yu \(Vorkompilierte Headerdatei verwenden\)](../../build/reference/yu-use-precompiled-header-file.md), um für einen vorkompilierten Header statt des Standardpfadnamens einen eigenen Pfadnamen anzugeben.  Sie können auch **\/Fp** zusammen mit **\/Yc** verwenden, um die Verwendung einer vorkompilierten Headerdatei festzulegen, die vom `filename`\-Argument der **\/Yc**\-Option und vom Basisnamen der Quelldatei abweicht.  
  
 Wenn Sie keine Erweiterung als Teil des Pfadnamens angeben, wird die Erweiterung **.pch** angenommen.  Wenn Sie ein Verzeichnis ohne Dateinamen angeben, lautet der Dateiname standardmäßig VC`x`0.pch., wobei `x` die Hauptversion des verwendeten Visual C\+\+ angibt.  
  
 Sie können auch die **\/Fp**\-Option zusammen mit **\/Yu** verwenden.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Vorkompilierte Header**.  
  
4.  Ändern Sie die Eigenschaft **Vorkompilierte Headerdatei**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.PrecompiledHeaderFile*>.  
  
## Beispiel  
 Wenn Sie eine vorkompilierte Headerdatei für eine Debugversion Ihres Programms erstellen möchten und sowohl Headerdateien als auch Quellcode kompilieren, können Sie einen Befehl wie den Folgenden angeben:  
  
```  
CL /DDEBUG /Zi /Yc /FpDPROG.PCH PROG.CPP  
```  
  
## Beispiel  
 Durch den folgenden Befehl wird die Verwendung einer vorkompilierten Headerdatei mit der Bezeichnung MYPCH.pch erstellt.  Der Compiler geht davon aus, dass der Quellcode in PROG.cpp mit MYAPP.h vorkompiliert wurde und dass sich der vorkompilierte Code in MYPCH.pch befindet.  Er verwendet den Inhalt von MYPCH.pch und kompiliert den Rest von PROG.cpp, um eine OBJ\-Datei zu erstellen.  Die Ausgabedatei dieses Beispiels trägt den Namen **PROG.exe**.  
  
```  
CL /YuMYAPP.H /FpMYPCH.PCH PROG.CPP  
```  
  
## Siehe auch  
 [\/F\-Optionen \(Ausgabedateioptionen\)](../../build/reference/output-file-f-options.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [Festlegen des Pfadnamens](../../build/reference/specifying-the-pathname.md)