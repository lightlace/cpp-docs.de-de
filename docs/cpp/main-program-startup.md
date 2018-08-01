---
title: 'main: Programmstart | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d78ca2a195ac60e31e01bbe271b7f92536cc1a05
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401481"
---
# <a name="main-program-startup"></a>main: Programmstart
Eine spezielle Funktion mit dem Namen **main** ist der Ausgangspunkt der Ausführung von C- und C++-Programme. Wenn Sie das Schreiben von Code sind, die entspricht, der [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] Programmiermodell, können Sie `wmain`, dies ist die Breitzeichen-Version von **main**.  
  
 Die **main** Funktion wird vom Compiler nicht vordefiniert. Sie muss im Programmtext angegeben werden.  
  
 Die Deklarationssyntax für **main** ist  
  
```cpp 
int main();  
```  
  
 oder optional  
  
```cpp 
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 Die Deklarationssyntax für `wmain` lautet wie folgt:  
  
```cpp 
int wmain( );  
```  
  
 oder optional  
  
```cpp 
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Sie können auch das in TCHAR.h definierte `_tmain` verwenden. `_tmain` Löst in **main** es sei denn, _UNICODE ist definiert. In diesem Fall wird `_tmain` in `wmain` aufgelöst.  
  
 Sie können auch die **main** und `wmain` Funktionen können deklariert werden, als Rückgabewert **"void"** (keinen Wert zurückgibt). Wenn Sie deklarieren **main** oder `wmain` als Rückgabewert **"void"**, Sie können nicht an den übergeordneten Prozess oder das Betriebssystem einen Exitcode zurückgeben, indem eine [zurückgeben](../cpp/return-statement-in-program-termination-cpp.md) Anweisung. Zurückzugebenden einen Exitcode beim **main** oder `wmain` wird deklariert als **"void"**, verwenden Sie die [beenden](../cpp/exit-function.md) Funktion.  
  
**Ende Microsoft-spezifisch**  
 Die Typen für `argc` und `argv` werden von der Programmiersprache definiert. Die Namen `argc`, `argv` und `envp` sind üblich, für den Compiler jedoch nicht erforderlich. Weitere Informationen und ein Beispiel finden Sie unter [Argumentdefinitionen](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Stichwörter](../cpp/keywords-cpp.md)   
 [Mithilfe von "wmain" anstelle von main](../cpp/using-wmain-instead-of-main.md)   
 [Einschränkungen der Main-Funktion](../cpp/main-function-restrictions.md)   
 [Analysieren von C-Befehlszeilenargumenten](../cpp/parsing-cpp-command-line-arguments.md)