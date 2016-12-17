---
title: "Compilerwarnung (Stufe 1) C4503"
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
  - "C4503"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4503"
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
caps.handback.revision: "8"
ms.author: "corob"
manager: "ghogen"
---
# Compilerwarnung (Stufe 1) C4503
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'Bezeichner': Die Länge des ergänzten Namens wurde überschritten. Der Name wurde gekürzt.  
  
 Der ergänzte Name war länger als maximal vom Compiler erlaubt \(4096\) und wurde deshalb gekürzt.  Sie vermeiden diese Warnung und die Kürzung, indem Sie die Anzahl der Argumente oder die Namenslänge der verwendeten Bezeichner verringern.  
  
 Diese Warnung wird u. a. ausgegeben, wenn der Code wiederholt Vorlagen enthält, die auf Vorlagen spezialisiert sind:   Zum Beispiel eine Zuordnung von Zuordnungen \(in der Standard\-C\+\+\-Bibliothek\).  In diesem Fall können Sie die Typdefinitionen zu einem Typ \(z. B. eine Struktur\) umwandeln, der die Zuordnung enthält.  
  
 Unter Umständen können Sie sich jedoch auch dazu entschließen, den Code nicht umzustrukturieren.  Es ist möglich, eine Anwendung weiterzugeben, die C4503 generiert. Wenn jedoch zur Verknüpfungszeit Fehler für ein gekürztes Symbol ausgegeben werden, treten beim Ermitteln des in der Fehlermeldung enthaltenen Symboltyps zusätzliche Schwierigkeiten auf.  Debuggen wird ebenfalls erschwert: Der Debugger ist nicht mehr ohne weiteres in der Lage, einem Typnamen einen Symbolnamen zuzuweisen.  Die ordnungsgemäße Ausführung des Programms wird durch den gekürzten Namen jedoch nicht beeinflusst.  
  
 Im folgenden Beispiel wird C4503 generiert:  
  
```  
// C4503.cpp  
// compile with: /W1 /EHsc /c  
// C4503 expected  
#include <string>  
#include <map>  
  
class Field{};  
  
typedef std::map<std::string, Field> Screen;  
typedef std::map<std::string, Screen> WebApp;  
typedef std::map<std::string, WebApp> WebAppTest;  
typedef std::map<std::string, WebAppTest> Hello;  
Hello MyWAT;  
```  
  
 Im folgenden Beispiel wird eine Möglichkeit dargestellt, den Code umzuschreiben, sodass C4503 vermieden wird:  
  
```  
// C4503b.cpp  
// compile with: /W1 /EHsc /c  
#include <string>  
#include <map>  
  
class Field{};  
struct Screen2 {  
   std::map<std::string, Field> Element;  
};  
  
struct WebApp2 {  
   std::map<std::string, Screen2> Element;  
};  
  
struct WebAppTest2 {  
   std::map<std::string, WebApp2> Element;  
};  
  
struct Hello2 {  
   std::map<std::string, WebAppTest2> Element;  
};  
  
Hello2 MyWAT2;  
```