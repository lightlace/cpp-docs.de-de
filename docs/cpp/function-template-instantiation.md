---
title: Funktionsvorlageninstanziierung
ms.date: 11/04/2016
helpviewer_keywords:
- templates, instantiation
- function templates, instantiation
- instantiation, function templates
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
ms.openlocfilehash: c4667f5ae625468cdab428706ddaff92a1c1af33
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62154167"
---
# <a name="function-template-instantiation"></a>Funktionsvorlageninstanziierung

Wenn eine Funktionsvorlage für einen Typ das erste Mal aufgerufen wird, erstellt der Compiler eine Instanziierung. Jede Instanziierung ist eine Version der auf Vorlagen basierenden Funktion, die auf den Typ spezialisiert wurde. Diese Instanziierung wird jedes Mal aufgerufen, wenn die Funktion für den Typ verwendet wird. Wenn Sie über mehrere identische Instanziierungen verfügen (auch in verschiedenen Modulen), ist nur eine Kopie der Instanziierung in der ausführbaren Datei enthalten.

Konvertierung von Funktionsargumenten ist in den Funktionsvorlagen für alle Argument- und Parameterpaare zulässig, in denen der Parameter nicht von einem Vorlagenargument abhängt.

Funktionsvorlagen können explizit instanziiert werden, indem die Vorlage mit einem bestimmten Typ als Argument deklariert wird. Es ist beispielsweise der folgende Code zulässig:

```cpp
// function_template_instantiation.cpp
template<class T> void f(T) { }

// Instantiate f with the explicitly specified template.
// argument 'int'
//
template void f<int> (int);

// Instantiate f with the deduced template argument 'char'.
template void f(char);
int main()
{
}
```

## <a name="see-also"></a>Siehe auch

[Funktionsvorlagen](../cpp/function-templates.md)