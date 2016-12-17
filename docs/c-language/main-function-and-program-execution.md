---
title: "main-Funktion und Programmausf&#252;hrung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "Einstiegspunkte, Programm"
  - "main-Funktion"
  - "main-Funktion, Programmausführung"
  - "Programmstart [C++]"
  - "Programme [C++], Terminieren"
  - "Startcode, main-Funktion"
ms.assetid: 5984f1bd-072d-4e06-8640-122fb1454401
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# main-Funktion und Programmausf&#252;hrung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jedes C\-Programm verfügt über eine primäre \(main\) Funktion, die mit **main** benannt werden muss.  Wenn der Code dem Unicode\-Programmiermodell entspricht, können Sie die Breitzeichenversion von **main**, **wmain**, verwenden.  Die **main**\-Funktion ist der Ausgangspunkt für die Programmausführung.  Es steuert in der Regel die Programmausführung durch Verweisen der Aufrufe an andere Funktionen im Programm.  Ein Programm hält normalerweise die Ausführung am Ende von **main** an, obwohl es an anderen Punkten im Programm aus mehreren Gründen beendet werden kann.  Manchmal sollten Sie u. U. die Beendigung eines Programms erzwingen, wenn ein bestimmter Fehler erkannt wird.  Verwenden Sie dazu die **exit**\-Funktion.  Weitere Informationen und ein Beispiel für die Verwendung der [exit](../c-runtime-library/reference/exit-exit-exit.md)\-Funktion finden Sie in der *Laufzeitbibliotheksreferenz*.  
  
## Syntax  
  
```  
main( int argc, char *argv[ ], char *envp[ ] )  
```  
  
## Hinweise  
 Funktionen innerhalb des Quellprogramms führen eine oder mehrere bestimmte Aufgaben aus.  Die **main**\-Funktion ruft diese Funktionen auf, um die jeweiligen Aufgaben auszuführen.  Wenn **main** eine andere Funktion aufruft, übergibt sie die Ablaufsteuerung an die Funktion, sodass die Ausführung bei der ersten Anweisung in der Funktion beginnt.  Eine Funktion gibt die Steuerung an **main** zurück, wenn eine `return`\-Anweisung ausgeführt wird, oder wenn das Ende der Funktion erreicht ist.  
  
 Sie können beliebige Funktionen, einschließlich **main** mit Parametern deklarieren.  Der Begriff "Parameter" oder "formaler Parameter" bezieht sich auf den Bezeichner, der einen Wert empfängt, der an eine Funktion übergeben wird.  Informationen zum Übergeben von Argumenten an Parameter finden Sie unter [Parameter](../c-language/parameters.md).  Wenn eine Funktion eine andere Funktion aufruft, empfängt die aufgerufene Funktion Werte für ihre Parameter von der aufrufenden Funktion.  Diese Werte werden als "Argumente" bezeichnet. Sie können formale Parameter für **main** so deklarieren, dass es mit diesem Format Argumente in der Befehlszeile empfangen kann:  
  
 Wenn Sie Informationen an die **main**\-Funktion übergeben möchten, werden die Parameter in der Regel `argc` und `argv` genannt, obwohl der C\-Compiler diese Namen nicht benötigt.  Die Typen für `argc` und `argv` werden von der Programmiersprache C definiert.  Normalerweise wird bei Übergabe eines dritten Parameters an **main** der betreffende Parameter `envp` benannt.  Beispiele weiter unten in diesem Abschnitt beschrieben, wie diese drei Parameter verwendet werden können, um auf Befehlszeilenargumente zuzugreifen.  Diese Parameter werden in den folgenden Abschnitten erläutert.  
  
 Eine Beschreibung der Breitzeichenversion von **main** finden Sie unter [Verwenden von wmain](../c-language/using-wmain.md).  
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)