---
title: "pimpl f&#252;r Compilierungszeitkapselung (Modern C++)"
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
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
caps.latest.revision: 11
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# pimpl f&#252;r Compilierungszeitkapselung (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das *pimpl Vorgehensweise* ist eine moderne C\+\+\-Technik, Implementierung, auszublenden Kopplung zu minimieren und Schnittstellen zu trennen.  Pimpl ist unmittelbar für "Zeiger der Implementierung." Sie bereits mit dem Konzept vertraut sein jedoch kennen kann es durch andere Namen wie Cheshire\-Katzen\- oder \-Compiler\-Firewallidiom.  
  
## Warum Verwendung pimpl?  
 Im Folgenden wird gezeigt, wie das pimpl Vorgehensweise den Lebenszyklus der Softwareentwicklung verbessern kann:  
  
-   Reduzierung von Kompilierungsabhängigkeiten.  
  
-   Trennung der Schnittstelle und der Implementierung.  
  
-   Portabilität.  
  
## Pimpl\-Kopfzeile  
  
```cpp  
  
// my_class.h  
class my_class {  
   //  ... all public and protected stuff goes here ...  
private:  
   class impl; unique_ptr<impl> pimpl; // opaque type here  
};  
  
```  
  
 Das pimpl Vorgehensweise vermeidet Wiederaufbauenkaskaden und spröde Objektlayouts.  Es ist für \(transitiv\) von Typen gut geeignet.  
  
## Pimpl\-Implementierung  
 Definieren Sie die `impl`\-Klasse in die CPP\-Datei.  
  
```cpp  
  
// my_class.cpp  
class my_class::impl {  // defined privately here  
  // ... all private data and functions: all of these  
  //     can now change without recompiling callers ...  
};  
my_class::my_class(): pimpl( new impl )  
{  
  // ... set impl values ...   
}  
```  
  
## Bewährte Methoden  
 Überlegen Sie, ob nicht\-auslösende Unterstützung für Austauschspezialisierung hinzufügt.  
  
## Siehe auch  
 [Willkommen zurück bei C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)   
 [C\+\+\-Standardbibliothek](../standard-library/cpp-standard-library-reference.md)