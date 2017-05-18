---
title: Compiler (Stufe 1) C4503 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: f999fcb73860bfd2fabb3484e78f313a32240dee
ms.contentlocale: de-de
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4503"></a>Compilerwarnung (Stufe 1) C4503
'Bezeichner': ergänzter Name zu lang, Name wurde abgeschnitten.  
  
 Der ergänzte Name war länger als maximal vom Compiler erlaubt (4096) und wurde abgeschnitten. Um diese Warnung und die Kürzung zu vermeiden, verringern Sie die Anzahl der Argumente oder die Namenslänge der verwendeten Bezeichner.  
  
 Eine Situation, in dem diese Warnung ausgegeben wird, ist, wenn der Code wiederholt Vorlagen auf Vorlagen spezialisiert.  Z. B. eine Zuordnung von Zuordnungen (in der C++-Standardbibliothek).  In diesem Fall können Sie den Typdefinitionen an einen Typ (z. B. "Struct"), mit der Zuordnung.  
  
 Sie können jedoch nicht den Code umstrukturieren.  Es ist möglich, eine Anwendung, die C4503 generiert ist, wenn Sie auf ein Symbol abgeschnittene Link Fehler erhalten, es jedoch schwieriger, den Typ des Symbols in den Fehler zu ermitteln.  Debuggen wird auch schwieriger sein. der Debugger ist difficultly Zuordnung Symbolname Namen vorhanden.  Die Richtigkeit des Programms, ist jedoch nicht betroffen, durch den gekürzten Namen.  
  
 Im folgende Beispiel wird C4503 generiert:  
  
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
  
 Das folgende Beispiel zeigt eine Möglichkeit, Schreiben Sie den Code, um C4503 zu beheben:  
  
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
