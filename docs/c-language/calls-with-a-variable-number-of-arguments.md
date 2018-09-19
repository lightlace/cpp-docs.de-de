---
title: Aufrufe mit einer variablen Anzahl von Argumenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- arguments [C++], variable number of
- VARARGS.H
- ellipses (...), variable number of arguments
- STDARGS.H
- function calls, arguments
- '... ellipsis'
- function calls, variable number of arguments
ms.assetid: 8808fb26-4822-42f5-aba3-ac64b54e151b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec70da7259ce0b04334bf9c0e1f529e76b46c6c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46028219"
---
# <a name="calls-with-a-variable-number-of-arguments"></a>Aufrufe mit einer variablen Anzahl von Argumenten

Eine partielle Parameterliste kann durch die Auslassungsnotation – ein Komma, dem drei Punkte folgen (**, ...**) – beendet werden, um anzugeben, dass möglicherweise weitere Argumente an die Funktion übergeben werden, aber keine weiteren Informationen über diese angegeben werden. Für solche Argumente wird keine Typüberprüfung ausgeführt. Mindestens ein Parameter muss der Auslassungsnotation vorausgehen, und diese muss das letzte Token in der Parameterliste sein. Ohne die Auslassungsnotation ist das Verhalten einer Funktion nicht definiert, wenn sie Parameter zusätzlich zu den in der Parameterliste deklarierten empfängt.

Um eine Funktion mit einer variablen Anzahl von Argumenten aufzurufen, geben Sie einfach eine beliebige Anzahl von Argumenten im Funktionsaufruf an. Ein Beispiel ist die `printf`-Funktion aus der C-Laufzeitbibliothek. Der Funktionsaufruf muss ein Argument für jeden Typnamen enthalten, der in der Parameterliste oder der Liste der Argumenttypen deklariert ist.

Alle Argumente, die im Funktionsaufruf angegeben sind, werden auf dem Stapel abgelegt, es sei denn, die `__fastcall`-Aufrufkonvention wird angegeben. Die Anzahl von Parametern, die für die Funktion deklariert werden, bestimmt, wie viele Argumente vom Stapel genommen und den Parametern zugewiesen werden. Sie haben die Aufgabe, alle zusätzlichen Argumente vom Stapel abzurufen und zu bestimmen, wie viele Argumente vorhanden sind. Die STDARG.H-Datei enthält Makros im ANSI-Format für den Zugriff auf Funktionsargumente, die eine variable Anzahl von Argumenten akzeptieren. Außerdem wird in "VARARGS.H" weiterhin das XENIX-Format von Makros unterstützt.

Diese Beispieldeklaration ist für eine Funktion, die eine variable Anzahl von Argumenten aufruft:

```
int average( int first, ...);
```

## <a name="see-also"></a>Siehe auch

[Funktionsaufrufe](../c-language/function-calls.md)