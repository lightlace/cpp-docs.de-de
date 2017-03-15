---
title: "once | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-pragma.once"
  - "once_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "once-Pragma"
  - "Pragmas, once"
ms.assetid: c7517556-6403-4b16-8898-f2aa0a6f685f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# once
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gibt an, dass die Datei beim Kompilieren einer Quellcodedatei nur einmal vom Compiler eingefügt \(geöffnet\) wird.  
  
## Syntax  
  
```  
  
#pragma once  
  
```  
  
## Hinweise  
 Durch Verwendung von `#pragma once` kann die Builderstellungsdauer verringert werden, da der Compiler die Datei nicht nach dem ersten \#include\-Befehl der Datei in der Übersetzungseinheit öffnet und liest.  Dies wird als *multiple\-include\-Optimierung* bezeichnet.  Sie hat eine ähnliche Wirkung wie das Idiom *\#include\-Schutz*, das Präprozessormakrodefinitionen verwendet,um mehrere Einschlüsse der Inhalte der Datei zu verhindern.  Dies trägt auch dazu bei, Verletzungen von *Regeln mit einer Definition* zu verhindern – die Anforderung, dass alle Vorlagen, Typen, Funktionen und Objekte nicht mehr als eine Definition im Code haben.  
  
 Zum Beispiel:  
  
```  
// header.h  
#pragma once  
// Code placed here is included only once per translation unit  
  
```  
  
 Wir empfehlen die `#pragma once`\-Richtlinie für neuen Code, da sie den globalen Namespace nicht mit einem Präprozessorsymbol verunreinigt.  Sie erfordert weniger Eingaben, ist weniger verwirrend und kann keine Symbolkonflikte verursachen – Fehler, die verursacht werden, wenn unterschiedliche Headerdateien das gleiche Präprozessorsymbol als Schutzwert verwenden.  Sie ist nicht Teil des C\+\+\-Standards, wird jedoch portabel durch mehrere allgemeine Compiler implementiert.  
  
 Die gleichzeitige Verwendung von \#include\-Schutz\-Idiom und `#pragma once` in derselben Datei bietet keinen Vorteil.  Der Compiler erkennt das \#include\-Schutz\-Idiom und implementiert die multiple\-include\-Optimierung genauso wie die `#pragma once`\-Richtlinie, wenn kein Nicht\-Kommentarcode oder keine Präprozessordirektive vor oder nach der Standardform des Idioms steht:  
  
```  
// header.h  
// Demonstration of the #include guard idiom.  
// Note that the defined symbol can be arbitrary.  
#ifndef HEADER_H_     // equivalently, #if !defined HEADER_H_  
#define HEADER_H_  
// Code placed here is included only once per translation unit  
#endif // HEADER_H_  
  
```  
  
 Wir empfehlen das \#include\-Schutz\-Idiom, wenn Code für Compiler portabel sein muss, die die `#pragma once`\-Richtlinie nicht implementieren, um die Konsistenz mit vorhandenem Code aufrechtzuerhalten, oder wenn die multiple\-include\-Optimierung nicht möglich ist.  Dies kann bei komplexen Projekten passieren, wenn Dateisystemaliasing oder Alias\-Includepfade verhindern, dass der Compiler identische Includedateien über den kanonischen Pfad identifiziert.  
  
 Achten Sie darauf, dass Sie `#pragma once` oder das \#include\-Schutz\-Idiom nicht in Headerdateien verwenden, die auf ein mehrmaliges Einschließen ausgelegt sind, indem Präprozessorsymbole zum Steuern ihrer Effekte verwendet werden.  Ein Beispiel für diesen Entwurf finden Sie in der Headerdatei \<assert.h\>.  Achten Sie auch darauf, Includepfade zu verwalten, um zu vermeiden, mehrere Pfade für eingeschlossene Dateien zu erstellen, was die multiple\-include\-Optimierung für \#include\-Schutz und `#pragma once` verhindern kann.  
  
## Siehe auch  
 [Pragma\-Direktiven und das \_\_Pragma\-Schlüsselwort](../preprocessor/pragma-directives-and-the-pragma-keyword.md)