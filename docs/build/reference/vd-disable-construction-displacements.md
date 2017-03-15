---
title: "/vd (Konstruktionsverschiebungen deaktivieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/vd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/vd0 (Compileroption) [C++]"
  - "/vd1 (Compileroption) [C++]"
  - "/vdn (Konstruktionsverschiebungen deaktivieren) (Compileroption)"
  - "Konstruktionsverschiebungen"
  - "Konstruktionsverschiebungen deaktivieren (Compileroption)"
  - "Verschiebungen (Compileroption)"
  - "vd0 (Compileroption) [C++]"
  - "-vd0 (Compileroption) [C++]"
  - "vd1 (Compileroption) [C++]"
  - "-vd1 (Compileroption) [C++]"
  - "vtordisp-Felder"
ms.assetid: 93258964-14d7-4b1c-9cbc-d6f4d74eab69
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /vd (Konstruktionsverschiebungen deaktivieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Syntax  
  
```  
/vdn  
```  
  
## Argumente  
 `0`  
 Unterdrückt die **vtordisp**\-Member zur Konstruktor\-\/Destruktorverschiebung.  Wählen Sie diese Option nur dann, wenn Sie sicher sind, dass alle Klassenkonstruktoren und \-destruktoren virtuelle Funktionen virtuell aufrufen.  
  
 `1`  
 Ermöglicht das Erstellen ausgeblendeter **vtordisp**\-Member zur Konstruktor\-\/Destruktorverschiebung. Dieses ist die Standardeinstellung.  Diese Option ist die Standardoption.  
  
 `2`  
 Ermöglicht es, [dynamic\_cast\-Operator](../../cpp/dynamic-cast-operator.md) für ein zu erstellendes Objekt zu verwenden.  Beispielsweise kann dynamic\_cast für die Typumwandlung von einer virtuellen Basisklasse zu einer abgeleiteten Klasse verwendet werden.  
  
 **\/vd2** fügt ein vtordisp\-Feld hinzu, wenn Sie eine virtuelle Basisklasse mit virtuellen Funktionen haben.  **\/vd1** sollte ausreichen.  Im häufigsten Fall, in dem **\/vd2** erforderlich ist, ist die einzige virtuelle Funktion in der virtuellen Basisklasse ein Destruktor.  
  
## Hinweise  
 Diese Optionen betreffen nur C\+\+\-Code mit virtuellen Basisklassen.  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] implementiert die Unterstützung der C\+\+\-Konstruktionsverschiebung in Situationen mit virtueller Vererbung.  Mit Konstruktionsverschiebung wird das Problem gelöst, das auftritt, wenn ein Konstruktor während der Konstruktion einer weiteren abgeleiteten Klasse eine virtuelle Funktion aufruft, die in einer virtuellen Basisklasse deklariert und in einer abgeleiteten Klasse überschrieben wird.  
  
 Das Problem besteht darin, dass der virtuellen Funktion als Folge von Diskrepanzen zwischen den Verschiebungen zu den virtuellen Basisklassen einer Klasse und den Verschiebungen zu ihren abgeleiteten Klassen ein falscher `this`\-Zeiger übergeben werden könnte.  Bei dieser Lösung wird für jede virtuelle Basisklasse einer Klasse eine einzige Justierung der Konstruktionsverschiebung bereitgestellt, das so genannte **vtordisp**\-Feld.  
  
 Standardmäßig werden vtordisp\-Felder eingeführt, wenn der Code benutzerdefinierte Konstruktoren und Destruktoren definiert und auch virtuelle Funktionen virtueller Klassen überschreibt.  
  
 Diese Optionen beeinflussen ganze Quelltextdateien.  Verwenden Sie [vtordisp](../../preprocessor/vtordisp.md), um vtordisp\-Felder zu unterdrücken und dann klassenweise wieder zu aktivieren.  
  
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