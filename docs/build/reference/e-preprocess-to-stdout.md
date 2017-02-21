---
title: "/E (Vorverarbeitung an &quot;stdout&quot;) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/e"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/E (Compileroption) [C++]"
  - "-E (Compileroption) [C++]"
  - "Präprozessorausgabe"
  - "Präprozessorausgabe, Kopieren nach stdout"
ms.assetid: ddbb1725-d950-4978-ab2f-30a5cd7b778c
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /E (Vorverarbeitung an &quot;stdout&quot;)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Verarbeitet C\- und C\+\+\-Quelldateien vor und übermittelt die vorverarbeiteten Dateien an das Standardausgabegerät.  
  
## Syntax  
  
```  
/E  
```  
  
## Hinweise  
 Bei diesem Prozess werden alle Präprozessordirektiven und Makroerweiterungen ausgeführt sowie Kommentare entfernt.  Um Kommentare in der vorverarbeiteten Ausgabe beizubehalten, verwenden Sie zusätzlich die [\/C \(Kommentare bei der Vorverarbeitung beibehalten\)](../../build/reference/c-preserve-comments-during-preprocessing.md)\-Compileroption.  
  
 **\/E** fügt der Ausgabe `#line`\-Direktiven am Anfang und Ende jeder eingeschlossenen Datei sowie vor und hinter den Zeilen hinzu, die von den Präprozessordirektiven zur bedingten Kompilierung entfernt wurden.  Diese Direktiven ändern die Zeilennummerierung der vorverarbeiteten Datei.  Deshalb beziehen sich Fehlermeldungen in späteren Verarbeitungsstufen auf die Zeilennummern der ursprünglichen Quelldatei, nicht auf die Zeilen in der vorverarbeiteten Datei.  
  
 Mit der **\/E**\-Option wird die Kompilierung unterdrückt.  Sie müssen die vorverarbeitete Datei erneut zum Kompilieren übergeben.  **\/E** unterdrückt auch die Ausgabedateien der Optionen **\/FA**, **\/Fa** und **\/Fm**.  Weitere Informationen finden Sie unter [\/FA, \/Fa \(Listendatei\)](../../build/reference/fa-fa-listing-file.md) und [\/Fm \(Name der Zuordnungsdatei\)](../../build/reference/fm-name-mapfile.md).  
  
 Verwenden Sie die [\/EP \(Vorverarbeitung an "stdout" ohne \#line\-Direktiven\)](../../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md)\-Option zum Unterdrücken der `#line`\-Direktiven.  
  
 Um die vorverarbeitete Ausgabe in eine Datei statt an `stdout` zu übergeben, verwenden Sie stattdessen die [\/P \(Vorverarbeitung in eine Datei\)](../../build/reference/p-preprocess-to-a-file.md)\-Option.  
  
 Zum Unterdrücken der `#line`\-Direktiven und Übergeben der vorverarbeiteten Ausgabe in eine Datei verwenden Sie **\/P** und **\/EP** zusammen.  
  
 Vorkompilierte Header können nicht mit der **\/E**\-Option verwendet werden.  
  
 Beachten Sie, dass beim Vorverarbeiten in eine separate Datei nach Tokens keine Leerzeichen eingefügt werden.  Das kann zu einem ungültigen Programm oder unbeabsichtigten Nebeneffekten führen.  Das folgende Programm wird erfolgreich kompiliert:  
  
```  
#define m(x) x  
m(int)main( )  
{  
   return 0;  
}  
```  
  
 Wenn Sie jedoch mit dem folgenden Code kompilieren:  
  
```  
cl -E test.cpp > test2.cpp  
```  
  
 wird `int main` fehlerhaft als `intmain` an **test2.cpp** übergeben.  
  
### So legen Sie diese Compileroption in der Visual Studio\-Entwicklungsumgebung fest  
  
1.  Öffnen Sie das Dialogfeld **Eigenschaftenseiten** des Projekts.  Ausführliche Informationen finden Sie unter [Gewusst wie: Öffnen von Projekteigenschaftenseiten](../../misc/how-to-open-project-property-pages.md).  
  
2.  Klicken Sie auf den Ordner **C\/C\+\+**.  
  
3.  Klicken Sie auf die Eigenschaftenseite **Befehlszeile**.  
  
4.  Geben Sie die Compileroption im Feld **Zusätzliche Optionen** ein.  
  
### So legen Sie diese Compileroption programmgesteuert fest  
  
-   Siehe <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.GeneratePreprocessedFile*>.  
  
## Beispiel  
 Die folgende Befehlszeile führt eine Vorverarbeitung von `ADD.C` durch, übernimmt die Kommentare, fügt `#line`\-Direktiven hinzu und zeigt das Ergebnis auf dem Standardausgabegerät an:  
  
```  
CL /E /C ADD.C  
```  
  
## Siehe auch  
 [Compileroptionen](../../build/reference/compiler-options.md)   
 [Festlegen von Compileroptionen](../../build/reference/setting-compiler-options.md)