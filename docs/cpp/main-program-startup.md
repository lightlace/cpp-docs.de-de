---
title: 'main: Programmstart | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 7d6bc27c3d0bca392aa83c7ac599bfe329d3037e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="main-program-startup"></a>main: Programmstart
Eine spezielle Funktion mit dem Namen `main` ist der Ausgangspunkt der Ausführung für C- und C++-Programme. Wenn Sie Code schreiben, der dem [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)]-Programmiermodell entspricht, können Sie `wmain` verwenden. Dies ist die Breitzeichenversion von `main`.  
  
 Die `main`-Funktion wird vom Compiler nicht vordefiniert. Sie muss im Programmtext angegeben werden.  
  
 Die Deklarationssyntax für `main` lautet  
  
```  
int main();  
```  
  
 oder optional  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die Deklarationssyntax für `wmain` lautet wie folgt:  
  
```  
int wmain( );  
```  
  
 oder optional  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Sie können auch das in TCHAR.h definierte `_tmain` verwenden. `_tmain` wird in `main` aufgelöst, es sei denn, _UNICODE ist definiert. In diesem Fall wird `_tmain` in `wmain` aufgelöst.  
  
 Alternativ können die Funktionen `main` und `wmain` als Rückgabe von `void` (kein Rückgabewert) deklariert werden. Wenn Sie deklarieren `main` oder `wmain` als Rückgabe `void`, Sie können nicht auf den übergeordneten Prozess oder dem Betriebssystem einen Exitcode zurückgeben, indem eine [zurückgeben](../cpp/return-statement-in-program-termination-cpp.md) Anweisung. Zurückzugebenden ein Exitcode Wenn `main` oder `wmain` wird deklariert als `void`, verwenden Sie die [beenden](../cpp/exit-function.md) Funktion.  
  
**Ende Microsoft-spezifisch**  
 Die Typen für `argc` und `argv` werden von der Programmiersprache definiert. Die Namen `argc`, `argv` und `envp` sind üblich, für den Compiler jedoch nicht erforderlich. Weitere Informationen und ein Beispiel finden Sie unter [Argumentdefinitionen](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Mithilfe von "wmain" anstelle von main](../cpp/using-wmain-instead-of-main.md)   
 [Einschränkungen der main-Funktion](../cpp/main-function-restrictions.md)
