---
title: "Funktionsvorlagen | Microsoft Docs"
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
  - "Funktionsvorlagen"
  - "Funktionsvorlagen, Informationen über Funktionsvorlagen"
  - "Vorlagen, Funktion"
ms.assetid: 59b56a4b-0689-4161-9c07-25021562e2a7
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Funktionsvorlagen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Klassenvorlagen definieren eine Gruppe von verwandten Klassen, die auf den Typargumenten basieren, die der Klasse nach der Instanziierung übergeben werden.  Funktionsvorlagen sind den Klassenvorlagen ähnlich, definieren jedoch eine Funktionsreihe.  Mit Funktionsvorlagen können Sie eine Gruppe von Funktionen angeben, die auf demselben Code basieren, jedoch auf unterschiedliche Typen oder Klassen reagieren.  Die folgende Funktionsvorlage tauscht zwei Elemente aus:  
  
```  
// function_templates1.cpp  
template< class T > void MySwap( T& a, T& b ) {  
   T c(a);   
   a = b;   
   b = c;  
}  
int main() {  
}  
```  
  
 Dieser Code definiert eine Gruppe von Funktionen, die die Werte der Argumente auslagern.  Aus dieser Vorlage können Sie Funktionen erstellen, die `int` und **long**\-Typen sowie benutzerdefinierte Typen auslagern.  `MySwap` tauscht sogar Klassen aus, wenn der Kopierkonstruktor und der Zuweisungsoperator der Klasse ordnungsgemäß definiert sind.  
  
 Darüber hinaus wird durch die Funktionsvorlage verhindert, dass Objekte unterschiedlicher Typen ausgetauscht werden, da der Compiler die Typen der `a` und `b`\-Parameter zur Kompilierungszeit nicht kennt.  
  
 Obwohl diese Aufgabe durch eine nicht auf Vorlagen basierende Funktion mithilfe von void\-Zeigern ausgeführt werden kann, ist die Vorlagenversion typsicher.  Betrachten Sie folgenden Aufruf:  
  
```  
int j = 10;  
int k = 18;  
CString Hello = "Hello, Windows!";  
MySwap( j, k );          //OK  
MySwap( j, Hello );      //error  
```  
  
 Der zweite Aufruf `MySwap` löst einen Kompilierungszeitfehler aus, da der Compiler keine `MySwap`\-Funktion mit Parametern verschiedener Typen generieren kann.  Wenn void\-Zeiger verwendet würden, würden beide Funktionsaufrufe ordnungsgemäß kompiliert, die Funktion würde zur Laufzeit jedoch nicht ordnungsgemäß funktionieren.  
  
 Die explizite Angabe der Vorlagenargumente für eine Funktionsvorlage ist zulässig.  Beispiel:  
  
```  
// function_templates2.cpp  
template<class T> void f(T) {}  
int main(int j) {  
   f<char>(j);   // Generate the specialization f(char).  
   // If not explicitly specified, f(int) would be deduced.  
}  
```  
  
 Wenn das Vorlagenargument explizit angegeben wird, werden normale implizite Konvertierungen durchgeführt, um das Funktionsargument in den Typ der entsprechenden Funktionsvorlagenparametern zu konvertieren.  Im Beispiel oben führt der Compiler \(`char j`\) eine Konvertierung in den Typ `int` durch.  
  
## Siehe auch  
 [Vorlagen](../cpp/templates-cpp.md)   
 [Funktionsvorlageninstanziierung](../cpp/function-template-instantiation.md)   
 [Explizite Instantiierung](../cpp/explicit-instantiation.md)   
 [Explizite Spezialisierung von Funktionsvorlagen](../cpp/explicit-specialization-of-function-templates.md)