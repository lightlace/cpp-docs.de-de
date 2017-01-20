---
title: "Schwerwiegender Fehler C1004"
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
  - "C1004"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1004"
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "corob"
manager: "ghogen"
---
# Schwerwiegender Fehler C1004
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unerwartetes Dateiende gefunden  
  
 Der Compiler hat das Ende einer Quelldatei erreicht, ohne ein Konstrukt aufzulösen.  Eines der folgenden Elemente fehlt u. U. im Code:  
  
-   Eine schließende geschweifte Klammer  
  
-   Eine schließende runde Klammer  
  
-   Ein schließendes Kommentarzeichen \(\*\/\)  
  
-   Ein Semikolon  
  
 Überprüfen Sie zur Behebung dieses Fehlers die folgenden Punkte:  
  
-   Das Standardlaufwerk bietet nicht genügend Kapazität für temporäre Dateien, die etwa den doppelten Speicherplatz der Quelldatei benötigen.  
  
-   Einer `#if`\-Direktive, die mit **False** ausgewertet wird, fehlt eine schließende `#endif`\-Direktive.  
  
-   Eine Quelldatei endet nicht mit einem Wagenrücklauf und Zeilenvorschub.  
  
 Im folgenden Beispiel wird C1004 generiert:  
  
```  
// C1004.cpp  
#if TEST  
int main() {}  
// C1004  
```  
  
 Mögliche Lösung:  
  
```  
// C1004b.cpp  
#if TEST  
#endif  
  
int main() {}  
```