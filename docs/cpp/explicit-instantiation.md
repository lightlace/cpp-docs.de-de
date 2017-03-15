---
title: "Explizite Instantiierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vorlagen, Instanziierung"
  - "Explizite Instantiierung"
  - "Instantiierung, explizite"
ms.assetid: 8b0d4e32-45a6-49d5-8041-1ebdd674410e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Explizite Instantiierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Mit expliziter Instanziierung können Sie eine Instanziierung einer auf Vorlagen basierenden Klasse oder Funktion erstellen, ohne sie tatsächlich im Code zu verwenden.  Da dies nützlich ist, wenn Sie Bibliotheksdateien \(LIB\-Dateien\) erstellen, die Vorlagen zur Verteilung verwenden, werden nicht instanziierte Vorlagendefinitionen nicht in Objektdateien \(OBJ\-Dateien\) abgelegt.  
  
 Dieser Code instanziiert `MyStack` explizit für `int`\-Variablen und sechs Elemente:  
  
```cpp  
template class MyStack<int, 6>;  
```  
  
 Diese Anweisung erstellt eine Instanziierung von `MyStack`, ohne Speicher für ein Objekt zu reservieren.  Code wird für alle Member generiert.  
  
 Die nächste Zeile instanziiert explizit nur die Konstruktormemberfunktion:  
  
```cpp  
template MyStack<int, 6>::MyStack( void );  
```  
  
 Sie können Funktionsvorlagen explizit instanziieren, indem Sie ein bestimmtes Typargument verwenden, um sie erneut zu deklarieren, wie im Beispiel unter [Funktionsvorlageninstanziierung](../cpp/function-template-instantiation.md) dargestellt.  
  
 Sie können das `extern`\-Schlüsselwort verwenden, um die automatische Instanziierung von Membern zu verhindern.  Beispiel:  
  
```cpp  
extern template class MyStack<int, 6>;  
```  
  
 Entsprechend können Sie bestimmte Member als nicht instanziiert und extern kennzeichnen:  
  
```cpp  
extern template MyStack<int, 6>::MyStack( void );  
```  
  
 Sie können das Schlüsselwort `extern` verwenden, um den Compiler daran zu hindern, den gleichen Instanziierungscode in mehr als einem Objektmodul zu generieren.  Sie müssen die Vorlagenfunktion instanziieren, indem Sie die angegebenen expliziten Vorlagenparameter in mindestens einem verknüpften Modul verwenden, wenn die Funktion aufgerufen wird. Andernfalls erhalten Sie einen Linkerfehler, wenn das Programm erstellt wird.  
  
> [!NOTE]
>  Das Schlüsselwort `extern` in der Spezialisierung gilt nur für Memberfunktionen, die außerhalb des Texts der Klasse definiert wurden.  Die Funktionen, die in der Klassendeklaration definiert werden, gelten als Inlinefunktionen und werden immer instanziiert.  
  
## Siehe auch  
 [Funktionsvorlagen](../cpp/function-templates.md)