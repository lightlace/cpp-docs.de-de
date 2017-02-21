---
title: "main: Programmstart | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc.main.startup"
  - "_tmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tmain-Funktion"
  - "Einstiegspunkte, Programm"
  - "main-Funktion, Programmstart"
  - "Programmstart [C++]"
  - "Startcode, main-Funktion"
  - "wmain-Funktion"
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# main: Programmstart
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Eine spezielle Funktion mit Namen `main` ist der Ausgangspunkt der Ausführung aller C\- und [!INCLUDE[TLA#tla_cpp](../cpp/includes/tlasharptla_cpp_md.md)]\-Programme.  Wenn Sie Code schreiben, der dem [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)]\-Programmiermodell entspricht, können Sie `wmain` verwenden. Dies ist die Breitzeichenversion von `main`.  
  
 Die `main`\-Funktion wird vom Compiler nicht vordefiniert.  Sie muss im Programmtext angegeben werden.  
  
 Die Deklarationssyntax für `main` lautet  
  
```  
int main();  
```  
  
 oder optional  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## Microsoft\-spezifisch  
 Die Deklarationssyntax für `wmain` lautet wie folgt:  
  
```  
int wmain( );  
```  
  
 oder optional  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Sie können auch das in TCHAR.h definierte `_tmain` verwenden.  `_tmain` wird in `main` aufgelöst, es sei denn, \_UNICODE ist definiert.  In diesem Fall wird `_tmain` in `wmain` aufgelöst.  
  
 Alternativ können die Funktionen `main` und `wmain` als Rückgabe von `void` \(kein Rückgabewert\) deklariert werden.  Wenn Sie `main` oder `wmain` als Rückgabe von `void` deklarieren, können Sie keinen Exitcode an den übergeordneten Prozess oder das Betriebssystem zurückgeben, indem Sie eine [return](../cpp/return-statement-in-program-termination-cpp.md)\-Anweisung verwenden.  Um einen Exitcode zurückzugeben, wenn `main` oder `wmain` als `void` deklariert wird, müssen Sie die [exit](../cpp/exit-function.md)\-Funktion verwenden.  
  
## END Microsoft\-spezifisch  
 Die Typen für `argc` und `argv` werden von der Programmiersprache definiert.  Die Namen `argc`, `argv` und `envp` sind üblich, für den Compiler jedoch nicht erforderlich.  Weitere Informationen und ein Beispiel finden Sie unter [Argumentdefinitionen](../cpp/argument-definitions.md).  
  
## Siehe auch  
 [C\+\+\-Schlüsselwörter](../cpp/keywords-cpp.md)   
 [Verwenden von "wmain" anstelle von "main"](../cpp/using-wmain-instead-of-main.md)   
 [Einschränkungen der main\-Funktion](../cpp/main-function-restrictions.md)