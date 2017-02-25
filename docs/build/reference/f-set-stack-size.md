---
title: "/F (Stapelgr&#246;&#223;e festlegen) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/f"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/F (Compileroption) [C++]"
  - "F (Compileroption) [C++]"
  - "-F (Compileroption) [C++]"
  - "Stapelgröße festlegen (Compileroption)"
  - "Stapel, Festlegen der Größe"
ms.assetid: 17320b6f-8305-445b-9ec2-75833f4b29e0
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /F (Stapelgr&#246;&#223;e festlegen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Legt die Programmstapelgröße in Byte fest.  
  
## Syntax  
  
```  
/F number  
```  
  
## Argumente  
 `number`  
 die Stapelgröße in Bytes.  
  
## Hinweise  
 Ohne diese Option beträgt die Stapelgröße standardmäßig 1 MB.  Das Argument *number* kann dezimal oder in C\-Notation angegeben werden.  Das Argument muss zwischen 1 und der maximalen vom Linker zugelassenen Stapelgröße liegen.  Der Linker rundet den angegebenen Wert auf die nächsten 4 Bytes auf.  Das Leerzeichen zwischen **\/F** und `number`ist optional.  
  
 Es kann sich als notwendig erweisen, die Stapelgröße zu erhöhen, wenn für Ihr Programm ein Stapelüberlauf gemeldet wird.  
  
 Sie können die Stapelgröße auch wie folgt festlegen:  
  
-   Verwenden der **\/STACK**\-Linkeroption.  Weitere Informationen finden Sie unter [\/STACK](../../build/reference/stack.md).  
  
-   Verwenden von EDITBIN für die EXE\-Datei.  Weitere Informationen finden Sie unter [EDITBIN\-Referenz](../../build/reference/editbin-reference.md).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)