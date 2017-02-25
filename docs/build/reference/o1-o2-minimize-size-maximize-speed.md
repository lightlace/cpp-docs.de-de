---
title: "/O1, /O2 (Gr&#246;&#223;e minimieren, Geschwindigkeit maximieren) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/o2"
  - "/o1"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/O1-Compileroption [C++]"
  - "/O2-Compileroption [C++]"
  - "Schneller Code"
  - "Geschwindigkeit maximieren (Compileroption) [C++]"
  - "Größe minimieren (Compileroption) [C++]"
  - "O1-Compileroption [C++]"
  - "-O1-Compileroption [C++]"
  - "O2-Compileroption [C++]"
  - "-O2-Compileroption [C++]"
  - "Kompakter Code"
ms.assetid: 2d1423f5-53d9-44da-8908-b33a351656c2
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# /O1, /O2 (Gr&#246;&#223;e minimieren, Geschwindigkeit maximieren)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wählt einen vordefinierten Satz von Optionen aus, der die Größe und Geschwindigkeit von Dateien beeinflusst.  
  
## Syntax  
  
```  
/O1  
/O2  
```  
  
## Hinweise  
 In der folgenden Tabelle werden **\/O1** und **\/O2** erläutert.  
  
|Option|Entspricht|Kommentar|  
|------------|----------------|---------------|  
|**\/O1** \(Größe minimieren\)|**\/Og \/Os \/Oy \/Ob2 \/Gs \/GF \/Gy**|Erstellt in den meisten Fällen den kleinstmöglichen Code.|  
|**\/O2** \(Geschwindigkeit maximieren\)|**\/Og \/Oi \/Ot \/Oy \/Ob2 \/Gs \/GF \/Gy**|Erstellt den schnellsten Code im Großteil der Fälle. \(Standardeinstellung für Releasebuilds\)|  
  
 Mit **\/O1** und **\/O2** wird außerdem die Optimierung des benannten Rückgabewerts aktiviert. Kopierkonstruktor und \-destruktor eines stapelbasierten Rückgabewerts werden dadurch eliminiert.  Betrachten Sie das folgende Beispiel.  Von der `Test`\-Funktion wird kein Kopierkonstruktor oder \-destruktor generiert.  Fügen Sie Ausgabeanweisungen dem Konstruktor, Destruktor und dem im Kopierkonstruktor hinzu, um den Effekt der benannten Rückgabewert\-Optimierung anzuzeigen, wenn Sie das Programm aus.  Weitere Informationen finden Sie unter [Benannte Rückgabewert\-Optimierung in Visual C\+\+ 2005](http://go.microsoft.com/fwlink/?linkid=131571).  
  
```  
// O1_O2_NRVO.cpp  
// compile with: /O1  
struct A {  
   A() {}  
   ~A() {}  
   A(const A& aa) {}  
};  
  
A Test() {  
   A a;  
   return a;  
}  
int main() {  
   A aa;  
   aa = Test();  
}  
```  
  
 **x86\-spezifisch**  
  
 Diese Optionen implizieren die Verwendung der Option Framezeiger unterdrücken \([\/Oy](../../build/reference/oy-frame-pointer-omission.md)\).  
  
 **END x86\-spezifisch**  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Optimierung**.  
  
4.  Ändern Sie die Eigenschaft **Optimierung**.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.Optimization*>.  
  
## Siehe auch  
 [\/O\-Optionen \(Code optimieren\)](../../build/reference/o-options-optimize-code.md)   
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)   
 [\/EH \(Ausnahmebehandlungsmodell\)](../../build/reference/eh-exception-handling-model.md)