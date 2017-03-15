---
title: "/Zg (Funktionsprototypen generieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/zg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zg (Compileroption) [C++]"
  - "Funktionsprototypen, Funktionsprototypen generieren (Compileroption)"
  - "Funktionsprototypen generieren (Compileroption)"
  - "Zg (Compileroption) [C++]"
  - "-Zg (Compileroption) [C++]"
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /Zg (Funktionsprototypen generieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Entfernt. Erstellt für jede in der Quelldatei definierte Funktion einen Funktionsprototyp, kompiliert die Quelldatei aber nicht.  
  
## Syntax  
  
```  
/Zg  
```  
  
## Hinweise  
 Diese Compileroption ist nicht mehr verfügbar. Sie wurde in Visual C\+\+ 2015 entfernt. Diese Seite ist für Benutzer von älteren Versionen von Visual C\+\+ vorgesehen.  
  
 Der Funktionsprototyp beinhaltet den Rückgabedatentyp der Funktion und eine Liste der Argumenttypen. Die Liste der Argumenttypen wird anhand der Typen der formalen Parameter der Funktion erstellt. Alle in der Quelldatei bereits vorhandenen Funktionsprototypen werden ignoriert.  
  
 Die Liste der Prototypen wird in die Standardausgabe geschrieben. Mithilfe dieser Liste können Sie prüfen, ob die tatsächlichen und formalen Parameter einer Funktion kompatibel sind. Sie können die Liste speichern, indem Sie die Standardausgabe in eine Datei umleiten. Dann können Sie **\#include** verwenden, um die Liste der Funktionsprototypen zu einem Bestandteil Ihrer Quelldatei zu machen. Dadurch wird der Compiler veranlasst, eine Argumenttypüberprüfung auszuführen.  
  
 Wenn Sie die **\/Zg**\-Option verwenden und Ihr Programm formale Parameter des Typs „struct“, „enum“ oder „union“ \(oder Zeiger auf solche Typen\) hat, muss die Deklaration für jeden „struct“\-, „enum“\- oder „union“\-Typ einen Tagnamen haben. Im folgenden Beispiel ist der Tagname `MyStruct`.  
  
```  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **\/Zg** ist veraltet. Für den Visual C\+\+\-Compiler ist geplant, älteren Code im C\-Stil nicht mehr zu unterstützen. Weitere Informationen finden Sie unter [Veraltete Compileroptionen in Visual C\+\+ 2005](assetId:///aa59fce3-50b8-4f66-9aeb-ce09a7a84cce).  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts. Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)