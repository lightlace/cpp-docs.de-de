---
title: "/Gs (Stapel-&#220;berpr&#252;fungsaufrufe kontrollieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/GS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/GS (Compileroption) [C++]"
  - "Deaktivieren von Stapelüberprüfungen"
  - "GS (Compileroption) [C++]"
  - "-GS (Compileroption) [C++]"
  - "Stapelüberprüfungsaufrufe"
  - "Stapelüberprüfungen"
  - "Stapel, Stapelüberprüfungen"
ms.assetid: 40daed7c-f942-4085-b872-01e12b37729e
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# /Gs (Stapel-&#220;berpr&#252;fungsaufrufe kontrollieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Steuert Stapelüberprüfungen  
  
## Syntax  
  
```  
/Gs[size]  
```  
  
## Argumente  
 `size`  
 \(Optional\) Die Anzahl von Bytes, die von lokalen Variablen belegt werden können, bevor eine Stapelüberprüfung initiiert wird.  Wenn Sie Option **\/Gs** ohne ein `size`\-Argument angegeben wird, entspricht das dem Angeben von **\/Gs0**.  
  
## Hinweise  
 Eine Stapelüberprüfung ist eine Codesequenz, die der Compiler in jeden Funktionsaufruf einfügt.  Sobald die Stapelüberprüfung initiiert ist, belegt sie im Speicher so viel Platz, wie zum Speichern der lokalen Variablen der Funktion nötig ist.  
  
 Wenn durch eine Funktion mehr als `size` Bytes an Stapelspeicher für lokale Variablen anfordert, wird für diese Funktion die Stapelüberprüfung initiiert.  Standardmäßig generiert der Compiler Code, der eine Stapelüberprüfung initiiert, wenn für eine Funktion mehr als eine Seite Stapelspeicher erforderlich ist.  Dies entspricht der Compileroption **\/Gs4096** für x86\-, [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]\- und ARM\-Plattformen.  Mit diesem Wert sind eine Anwendung und der Speichermanager von Windows in der Lage, den für den Programmstapel reservierten Arbeitsspeicher zur Laufzeit dynamisch zu erhöhen.  
  
> [!NOTE]
>  Der Standardwert **\/Gs4096** ermöglicht, dass der Programmstapel von Windows\-Anwendungen zur Laufzeit ordnungsgemäß vergrößert wird.  Wir empfehlen, den Standardwert nur dann zu ändern, wenn Sie genau wissen, warum Sie ihn ändern müssen.  
  
 Für einige Programme, beispielsweise virtuelle Gerätetreiber, ist dieser Standardmechanismus zum Vergrößern des Stapels nicht erforderlich.  In solchen Fällen sind die Stapelüberprüfungen nicht erforderlich, und Sie können verhindern, dass der Compiler diese generiert, indem Sie `size` auf einen Wert festlegen, der so groß ist, wie ihn keine Funktion zum Speichern ihrer lokalen Variablen benötigt.  Zwischen **\/Gs** und `size` darf kein Leerzeichen stehen.  
  
 **\/Gs0** aktiviert Stapelüberprüfungen für jeden Funktionsaufruf, der Speicher für lokale Variablen benötigt.  Das kann sich negativ auf die Leistung auswirken.  
  
 Stapelüberprüfungen können mit [check\_stack](../../preprocessor/check-stack.md) aktiviert oder deaktiviert werden.  **\/Gs** und das `check_stack`\-Pragma haben keine Auswirkungen auf standardmäßige C\-Bibliotheksroutinen und betreffen lediglich die von Ihnen kompilierten Funktionen.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Wählen Sie den Ordner **C\/C\+\+** aus.  
  
3.  Wählen Sie die Eigenschaftenseite **Befehlszeile** aus.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions*>.  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)