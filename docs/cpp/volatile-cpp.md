---
title: "volatile (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
f1_keywords: 
  - "volatile_cpp"
  - "volatile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Interrupthandler und volatile-Schlüsselwort"
  - "Objekte [C++], volatile"
  - "volatile-Schlüsselwort [C++]"
  - "Flüchtige Objekte"
ms.assetid: 81db4a85-ed5a-4a2c-9a53-5d07a771d2de
caps.latest.revision: 43
caps.handback.revision: "43"
ms.author: "mblome"
manager: "ghogen"
---
# volatile (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ein Typqualifizierer, den Sie verwenden können, um zu deklarieren, dass ein Objekt im Programm von der Hardware geändert werden kann.  
  
## Syntax  
  
```  
  
volatile declarator ;  
```  
  
## Hinweise  
 Sie können den [\/volatile](../build/reference/volatile-volatile-keyword-interpretation.md)\-Compilerschalter verwenden, um die Art und Weise zu ändern, wie der Compiler dieses Schlüsselwort interpretiert.  
  
 Visual Studio interpretiert das `volatile`\-Schlüsselwort je nach Zielarchitektur unterschiedlich.  In ARM, wenn keine **\/volatile**\-Compileroption angegeben ist, führt der Compiler den Vorgang aus, als ob **\/volatile:iso** angegeben wurde.  In anderen Architekturen als ARM, wenn keine **\/volatile**\-Compileroption angegeben ist, führt der Compiler den Vorgang aus, als ob **\/volatile:ms** angegeben wurde. Daher wird für andere Architekturen als ARM dringend empfohlen, **\/volatile:iso** anzugeben und explizite Synchronisierungsprimitiven und systeminterne Compilerfunktionen zu verwenden, wenn Sie mit Arbeitsspeicher arbeiten, der threadübergreifend bereitgestellt wird.  
  
 Sie können den `volatile`\-Qualifizierer verwenden, um den Zugriff auf die Speicherbereiche zu ermöglichen, die von asynchronen Prozessen wie Interrupthandlern verwendet werden.  
  
 Wenn `volatile` in einer Variable verwendet wird, die auch das [\_\_restrict](../cpp/extension-restrict.md)\-Schlüsselwort aufweist, hat `volatile` Vorrang.  
  
 Wenn ein `struct`\-Member als `volatile` gekennzeichnet ist, dann wird `volatile` an die gesamte Struktur weitergegeben.  Wenn eine Struktur nicht über eine Länge verfügt, die mithilfe einer Anweisung in der aktuellen Architektur kopiert werden kann, geht `volatile` in dieser Struktur möglicherweise vollständig verloren.  
  
 Das `volatile`\-Schlüsselwort hat möglicherweise keine Auswirkungen auf ein Feld, wenn eine der folgenden Bedingungen zutrifft:  
  
-   Die Länge des flüchtigen Felds überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anweisung kopiert werden kann.  
  
-   Die Länge der äußersten enthaltenen `struct` – oder wenn es sich um einen Member einer möglicherweise geschachtelten `struct` handelt – überschreitet die maximale Größe, die in der aktuellen Architektur mithilfe einer Anwendung kopiert werden kann.  
  
 Obwohl der Prozessor Speicherzugriffe, die nicht zwischengespeichert werden können, nicht neu anordnet, müssen Variablen, die nicht zwischengespeichert werden können, als `volatile` gekennzeichnet werden, um sicherzustellen, dass der Compiler die Speicherzugriffe nicht neu anordnet.  
  
 Objekte, die als `volatile` deklariert werden, werden in bestimmten Optimierungen nicht verwendet, da sich ihre Werte jederzeit ändern können.  Das System liest bei jeder Anforderung den aktuellen Wert eines flüchtigen Objekts, selbst wenn eine vorherige Anweisung bereits den Wert des gleichen Objekts abgefragt hatte.  Außerdem wird der Wert des Objekts sofort durch Zuweisung geschrieben.  
  
## ISO\-Kompatibilität  
 Wenn Sie mit dem [C\# volatile](../Topic/volatile%20\(C%23%20Reference\).md)\-Schlüsselwort oder mit dem Verhalten von `volatile` in früheren Versionen von Visual C\+\+ vertraut sind, beachten Sie, dass das `volatile`\-Schlüsselwort des ISO\-Standards C\+\+11 unterschiedlich ist und in Visual Studio unterstützt wird, wenn die [\/volatile:iso](../build/reference/volatile-volatile-keyword-interpretation.md)\-Compileroption angegeben wird. \(In ARM ist es standardmäßig festgelegt\).  Das `volatile`\-Schlüsselwort im ISO\-Standardcode C\+\+11 wird nur für Hardwarezugriffe verwendet. Verwenden Sie es nicht für die Kommunikation zwischen Threads.  Verwenden Sie für die Kommunikation zwischen Threads Mechanismen wie [std::atomic\<T\>](../standard-library/atomic.md) aus der [C\+\+\-Standardvorlagenbibliothek](../standard-library/cpp-standard-library-reference.md).  
  
## Ende ISO\-Kompatibilität  
  
## Microsoft\-spezifisch  
 Wenn die **\/volatile:ms**\-Compileroption verwendet wird – dies ist der Standard, wenn andere Architekturen als ARM adressiert werden – erzeugt der Compiler zusätzlichen Code, um die Reihenfolge der Verweise auf flüchtige Objekte zusätzlich zum Erhalt der Reihenfolge von Verweisen auf andere globale Objekte zu erhalten.  Insbesondere:  
  
-   Das Schreiben in ein flüchtiges Objekt \(auch als flüchtiger Schreibvorgang bezeichnet\) weist Release\-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das vor einem Schreibvorgang in ein flüchtiges Objekt in der Anweisungsabfolge auftritt, vor diesem flüchtigen Schreibvorgang in der kompilierten Binärdatei auftritt.  
  
-   Das Lesen eines flüchtigen Objekts \(auch als flüchtiger Lesevorgang bezeichnet\) weist Acquire\-Semantik auf. Das heißt, dass ein Verweis auf ein globales oder statisches Objekt, das nach dem Lesevorgang eines flüchtigen Arbeitsspeichers in der Anweisungsabfolge auftritt, nach dem flüchtigen Lesevorgang in der kompilierten Binärdatei auftritt.  
  
 Dadurch können flüchtige Objekte für Arbeitsspeichersperren und \-freigaben in Multithreadanwendungen verwendet werden.  
  
> [!NOTE]
>  Wenn er auf der erweiterten Garantie beruht, die gegeben ist, wenn die **\/volatile:ms**\-Compileroption verwendet wird, ist der Code nicht portabel.  
  
## Ende Microsoft\-spezifisch  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [const](../cpp/const-cpp.md)   
 [const\- und volatile\-Zeiger](../cpp/const-and-volatile-pointers.md)