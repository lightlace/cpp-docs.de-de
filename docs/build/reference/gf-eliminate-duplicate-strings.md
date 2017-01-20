---
title: "/GF (Doppelte Zeichenfolgen beseitigen)"
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
  - "VC.Project.VCCLCompilerTool.StringPooling"
  - "VC.Project.VCCLWCECompilerTool.StringPooling"
  - "/gf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GF (Compileroption) [C++]"
  - "Doppelte Zeichenfolgen"
  - "Eliminieren doppelter Zeichenfolgen (Compileroption) [C++]"
  - "GF (Compileroption) [C++]"
  - "-GF (Compileroption) [C++]"
  - "Stringpooling (Compileroption) [C++]"
  - "Zeichenfolgen [C++], Pooling"
ms.assetid: bb7b5d1c-8e1f-453b-9298-8fcebf37d16c
caps.latest.revision: 17
caps.handback.revision: "17"
ms.author: "corob"
manager: "ghogen"
---
# /GF (Doppelte Zeichenfolgen beseitigen)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es dem Compiler, eine einzige Kopie identischer Zeichenfolgen im Programmabbild und im Arbeitsspeicher während der Ausführung zu erstellen.  Dies ist eine Optimierung namens *Stringpooling*, die kleinere Programme erstellen kann.  
  
## Syntax  
  
```  
/GF  
```  
  
## Hinweise  
 Wenn Sie **\/GF** verwenden, vertauscht das Betriebssystem den Zeichenfolgenteil des Speichers nicht und kann die Zeichenfolgen erneut aus der Abbilddatei auslesen.  
  
 **\/GF** aktiviert das schreibgeschützte Stringpooling.  Beim Versuch, Zeichenfolgen unter **\/GF** zu ändern, tritt ein Anwendungsfehler auf.  
  
 Stringpooling macht aus den ursprünglich mehreren Zeigern auf mehrere Puffer mehrere Zeiger auf einen einzigen Puffer.  Im folgenden Codebeispiel werden `s` und `t` mit derselben Zeichenfolge initialisiert.  Aufgrund des Stringpoolings zeigen sie auf denselben Speicherbereich:  
  
```  
char *s = "This is a character buffer";  
char *t = "This is a character buffer";  
```  
  
> [!NOTE]
>  Die zum Bearbeiten und Fortsetzen des Vorgangs verwendete [\/ZI](../../build/reference/z7-zi-zi-debug-information-format.md)\-Option legt automatisch die **\/GF**\-Option fest.  
  
> [!NOTE]
>  Die **\/GF**\-Compileroption erstellt einen adressierbaren Abschnitt für jede eindeutige Zeichenfolge.  In der Standardeinstellung kann eine Objektdatei außerdem bis zu 65.536 adressierbare Abschnitte enthalten.  Wenn das Programm mehr als 65.536 Zeichenfolgen enthält, verwenden Sie die [\/bigobj\-](../../build/reference/bigobj-increase-number-of-sections-in-dot-obj-file.md)\-Compileroption, um mehr Abschnitte zu erstellen.  
  
 **\/GF** ist gültig, wenn [\/O1](../../build/reference/o1-o2-minimize-size-maximize-speed.md) oder **\/O2** verwendet wird.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Codegenerierung**.  
  
4.  Ändern Sie die Eigenschaft **Stringpooling aktivieren**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.StringPooling*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)