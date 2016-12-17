---
title: "Die Hilfsfunktion"
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
helpviewer_keywords: 
  - "__delayLoadHelper-Funktion"
  - "__delayLoadHelper2-Funktion"
  - "Verzögertes Laden von DLLs, Hilfsfunktion"
  - "delayhlp.cpp"
  - "delayimp.h"
  - "delayimp.lib"
  - "Hilfsfunktionen"
ms.assetid: 6279c12c-d908-4967-b0b3-cabfc3e91d3d
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Die Hilfsfunktion
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Hilfsfunktion für linkergestütztes verzögertes Laden stellt die Funktion dar, von der die DLL zur Laufzeit geladen wird.  Das Verhalten der Hilfsfunktion kann angepasst werden, indem eine eigene Funktion geschrieben und mit dem Programm verknüpft wird, anstatt die gelieferte Hilfsfunktion in Delayimp.lib zu verwenden.  Eine einzige Hilfsfunktion ist für alle verzögert geladenen DLLs verantwortlich.  
  
 Eine eigene Version der Hilfsfunktion kann bereitgestellt werden, um bestimmte Verarbeitungsschritte, die vom Namen der DLL oder Importe abhängen, durchzuführen.  
  
 Von der Hilfsfunktion werden die folgenden Aktionen durchgeführt:  
  
-   Das gespeicherte Handle auf die Bibliothek wird überprüft, um festzustellen, ob diese bereits geladen wurde.  
  
-   **LoadLibrary** wird aufgerufen, um die DLL zu laden.  
  
-   **GetProcAddress** wird aufgerufen, um die Prozeduradresse abzurufen.  
  
-   Es erfolgt eine Rückkehr zum verzögert geladenen Import\-Thunk, um den neu geladenen Einstiegspunkt aufzurufen.  
  
 Ein Benachrichtigungshook im Programm kann von der Hilfsfunktion nach jeder der folgenden Aktionen zurückgerufen werden:  
  
-   beim Starten der Hilfsfunktion  
  
-   unmittelbar vor dem Aufruf von **LoadLibrary** in der Hilfsfunktion  
  
-   unmittelbar vor dem Aufruf von **GetProcAddress** in der Hilfsfunktion  
  
-   bei fehlerhaftem Aufruf von **LoadLibrary** in der Hilfsfunktion  
  
-   bei fehlerhaftem Aufruf von **GetProcAddress** in der Hilfsfunktion  
  
-   nach Beendigung der Hilfsfunktion  
  
 Jeder solche Hookpunkt kann einen Wert zurückgeben, mit dem die normale Verarbeitung der Hilfsfunktion geändert wird, mit Ausnahme der Rückkehr zum verzögert geladenen Import\-Thunk.  
  
 Der Standardcode der Hilfsfunktion befindet sich in Delayhlp.cpp und Delayimp.h \(in vc\\include\) und ist in Delayimp.lib \(in vc\\lib\) kompiliert.  Diese Bibliothek muss beim Kompilieren eingeschlossen werden, es sei denn, eine eigene Hilfsfunktion wird geschrieben.  
  
 In den folgenden Themen wird die Hilfsfunktion beschrieben:  
  
-   [Änderungen an der Hilfsfunktion für das verzögerte Laden von DLLs seit Visual C\+\+ 6.0](../../build/reference/changes-in-the-dll-delayed-loading-helper-function-since-visual-cpp-6-0.md)  
  
-   [Aufrufkonventionen, Parameter und Rückgabetyp](../../build/reference/calling-conventions-parameters-and-return-type.md)  
  
-   [Struktur\- und Konstantendefinitionen](../../build/reference/structure-and-constant-definitions.md)  
  
-   [Berechnen der erforderlichen Werte](../../build/reference/calculating-necessary-values.md)  
  
-   [Entladen einer verzögert geladenen DLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md)  
  
## Siehe auch  
 [Linkerunterstützung für verzögertes Laden von DLLs](../../build/reference/linker-support-for-delay-loaded-dlls.md)