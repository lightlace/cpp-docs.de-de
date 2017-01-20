---
title: "Linkertoolfehler LNK2038"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "error-reference"
f1_keywords: 
  - "LNK2038"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2038"
ms.assetid: b8d0fb35-eee6-4f52-b3c4-239cb4f65656
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "corob"
manager: "ghogen"
---
# Linkertoolfehler LNK2038
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Konflikt ermittelt für "\<Name\>" : Der Wert "\<Wert 1\>" stimmt nicht mit dem Wert "\<Wert 2\>" in \<DATEINAME.OBJ\> überein.  
  
 Ein Symbolkonflikt wurde vom Linker erkannt.  Dieser Fehler gibt an, dass unterschiedliche Teile einer App – dazu zählen Bibliotheken oder anderer Objektcode, mit dem die App verknüpft ist – in Konflikt stehende Definitionen des Symbols verwenden.  Das [detect mismatch](../../preprocessor/detect-mismatch.md)\-Pragma wird verwendet, um diese Symbole zu definieren und ihre in Konflikt stehenden Werte zu erkennen.  
  
### So beheben Sie diesen Fehler  
  
-   Dieser Fehler kann auftreten, wenn eine Objektdatei im Projekt veraltet ist.  Bevor Sie andere Lösungen zur Fehlerbehebung ausprobieren, versuchen Sie, einen bereinigten Build auszuführen, um sicherzustellen, dass die Objektdateien aktuell sind.  
  
-   Visual Studio definiert die folgenden Symbole, um das Verknüpfen von nicht kompatiblem Code zu verhindern, der Laufzeitfehler oder anderes unerwartetes Verhalten verursachen kann.  
  
     `_MSC_VER`  
     Gibt die Haupt\- und Nebenversionsnummern des Visual C\+\+\-Compilers an, der verwendet wird, um eine App oder eine Bibliothek zu erstellen.  Code, der mit einer Version des Visual C\+\+\-Compilers kompiliert wird, ist nicht mit Code kompatibel, der mit einer Version kompiliert wird, die andere Haupt\- und Nebenversionsnummern hat.  Weitere Informationen finden Sie in [Vordefinierte Makros](../../preprocessor/predefined-macros.md) unter `_MSC_VER`.  
  
     Wenn Sie eine Bibliothek erstellen, die nicht mit der von Ihnen verwendeten Version des Visual C\+\+\-Compilers kompatibel ist, und keine kompatible Version der Bibliothek abgerufen oder erstellt werden kann, können Sie eine ältere Version des Compilers zum Erstellen des Projekts verwenden. Ändern Sie dazu einfach die Projekteigenschaft **Plattformtoolset**.  Weitere Informationen finden Sie unter [Gewusst wie: Ändern des Zielframeworks und des Plattformtoolsets](../../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
     `_ITERATOR_DEBUG_LEVEL`  
     Gibt die Ebene der Sicherheits\- und Debugfunktionen an, die in der C\+\+\-Standardbibliothek aktiviert werden.  Diese Funktionen können die Darstellung bestimmter C\+\+\-Standardbibliotheksobjekte ändern. Dadurch werden diese möglicherweise mit solchen Objekten inkompatibel, die andere Sicherheits\- und Debugfunktionen verwenden.  Weitere Informationen finden Sie unter [\_ITERATOR\_DEBUG\_LEVEL](../../standard-library/iterator-debug-level.md).  
  
     `RuntimeLibrary`  
     Gibt die Version der C\+\+\-Standardbibliothek und der C\-Laufzeit an, die von einer App oder einer Bibliothek verwendet wird.  Code, der eine Version der C\+\+\-Standardbibliothek oder C\-Laufzeit verwendet, ist nicht mit Code kompatibel, der eine andere Version verwendet.  Weitere Informationen finden Sie unter [\/MD, \/MT, \/LD \(Laufzeitbibliothek verwenden\)](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
     `_PPLTASKS_WITH_WINRT`  
     Gibt an, dass Code, der die [Parallel Patterns Library \(PPL\)](../../parallel/concrt/parallel-patterns-library-ppl.md) verwendet, mit Objekten verlinkt wird, die mit einer anderen Einstellung für die [\/ZW](../../build/reference/zw-windows-runtime-compilation.md)\-Compileroption kompiliert werden. \(**\/ZW** unterstützt C\+\+\/CX.\) Code, der die PPL verwendet oder davon abhängig ist, muss mit der gleichen **\/ZW**\-Einstellung kompiliert werden, der für die restliche App verwendet wird.  
  
     Stellen Sie sicher, dass die Werte dieser Symbole für alle Projekte in der Visual Studio\-Projektmappe konsistent sind, ebenso wie mit Code und Bibliotheken, mit denen die App verknüpft ist.  
  
## Siehe auch  
 [Fehler und Warnungen der Linkertools](../../error-messages/tool-errors/linker-tools-errors-and-warnings.md)