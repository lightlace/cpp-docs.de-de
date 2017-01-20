---
title: "C-Speicherklassenattribute (erweitert)"
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
  - "__declspec-Schlüsselwort [C]"
  - "Erweiterte Attribute"
  - "Erweiterte Speicherklassenattribute"
  - "Speicherklassenspezifizierer, C-Speicherklassen"
ms.assetid: 2580735c-f5bf-46ab-9468-0696893d82be
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# C-Speicherklassenattribute (erweitert)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft\-spezifisch**  
  
 Weitere aktuelle Informationen über dieses Thema finden Sie unter [\_\_declspec \(C\+\+\-Verweis\)](../cpp/declspec.md).  
  
 Die erweiterte Attributsyntax vereinfacht und standardisiert Microsoft\-spezifische Erweiterungen der Programmiersprache C.  Zu den Speicherklassenattributen, die die erweiterte Attributsyntax verwenden, gehören Thread, naked, dllimport und dllexport.  
  
 Der erweiterte Attributsyntax zur Bezeichnung von Speicherklasseninformation verwendet das \_declspec\-Schlüsselwort, welches angibt, dass eine Instanz eines gegebenen Typs mit einem Microsoft\-spezifischen Speicherklassenattribut \(thread, naked, dllimport oder dllexport\) gespeichert werden muss.  Beispiele anderer Speicherklassenmodifizierer umfassen die statischen und externen Schlüsselwörter.  Allerdings sind diese Schlüsselwörter Teil des ANSI C\-Standards und werden somit nicht von der erweiterten Attributsyntax abgedeckt.  
  
## Syntax  
 *storage\-class\-specifier*:  
 `__declspec` \( *extended\-decl\-modifier\-seq* \) \/\* Microsoft\-spezifisch \*\/  
  
 *extended\-decl\-modifier\-seq*:  
 *extended\-decl\-modifier*  opt  
  
 *extended\-decl\-modifier\-seq extended\-decl\-modifier*  
  
 *extended\-decl\-modifier*:  
 **thread**  
  
 **naked**  
  
 **dllimport**  
  
 `dllexport`  
  
 Die Deklarationsmodifizierer sind durch Leerzeichen getrennt.  Beachten Sie, dass *extended\-decl\-modifier\-seq* leer sein darf. \_\_declspec hat in diesem Fall keine Auswirkungen.  
  
 Die Speicherklassenattribute thread, naked, dllimport und dllexport sind nur Eigenschaften für die Daten\- oder Funktionsdeklaration, auf die sie angewendet werden. Sie definieren nicht die Typattribute der Funktion selbst neu.  Das Threadattribut wirkt sich nur auf Daten aus.  Das naked\-Attribut wirkt sich nur auf Funktionen aus.  Die Attribute dllimport und dllexport wirken sich auf Funktionen und Daten aus.  
  
 **END Microsoft\-spezifisch**  
  
## Siehe auch  
 [Deklarationen und Typen](../c-language/declarations-and-types.md)