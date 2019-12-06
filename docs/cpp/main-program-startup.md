---
title: 'main: Programmstart'
ms.date: 11/04/2016
f1_keywords:
- vc.main.startup
- _tmain
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
ms.openlocfilehash: 29e1b77c2e36c66e4e6fc4ec30a73af4d57654a0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857436"
---
# <a name="main-program-startup"></a>main: Programmstart

Eine spezielle Funktion mit dem Namen " **Main** " ist der Ausgangspunkt der Ausführung C++ für alle C-und-Programme. Wenn Sie Code schreiben, der dem Unicode-Programmiermodell entspricht, können Sie `wmain`verwenden, bei dem es sich um die breit Zeichen Version von **Main**handelt.

Die **Main** -Funktion wird vom Compiler nicht vordefiniert. Sie muss im Programmtext angegeben werden.

Die Deklarations Syntax für " **Main** " lautet

```cpp
int main();
```

oder optional

```cpp
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft-spezifisch**

Die Deklarationssyntax für `wmain` lautet wie folgt:

```cpp
int wmain( );
```

oder optional

```cpp
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Sie können auch `_tmain`verwenden, das in Tchar. h definiert ist. `_tmain` wird in **Main** aufgelöst, es sei denn, _UNICODE ist definiert. In diesem Fall wird `_tmain` in `wmain` aufgelöst.

Alternativ können die **Main** -Funktion und die `wmain`-Funktion als Rückgabe von **void** (kein Rückgabewert) deklariert werden. Wenn Sie **Main** oder `wmain` als Rückgabe von **void**deklarieren, können Sie keinen Exitcode an den übergeordneten Prozess oder das Betriebssystem zurückgeben, indem Sie eine [Return](../cpp/return-statement-in-program-termination-cpp.md) -Anweisung verwenden. Um einen Exitcode zurückzugeben, wenn **Main** oder `wmain` als **void**deklariert ist, müssen Sie die [Exit](../cpp/exit-function.md) -Funktion verwenden.

**Ende Microsoft-spezifisch**

Die Typen für `argc` und `argv` werden von der Programmiersprache definiert. Die Namen `argc`, `argv` und `envp` sind üblich, für den Compiler jedoch nicht erforderlich. Weitere Informationen und ein Beispiel finden Sie unter [Argument Definitionen](../cpp/argument-definitions.md).

## <a name="see-also"></a>Siehe auch

[Stichwörter](../cpp/keywords-cpp.md)<br/>
[Verwenden von "wmain" anstelle von "main"](../cpp/using-wmain-instead-of-main.md)<br/>
[Einschränkungen der main-Funktion](../cpp/main-function-restrictions.md)<br/>
[Analysieren von C-Befehlszeilenargumenten](../cpp/parsing-cpp-command-line-arguments.md)
