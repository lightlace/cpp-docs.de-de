---
title: Argumentdefinitionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e0c42478e5e6ce3c9efe66c45ed32292f2040a83
ms.sourcegitcommit: 3a141cf07b5411d5f1fdf6cf67c4ce928cf389c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/11/2018
ms.locfileid: "49084151"
---
# <a name="argument-definitions"></a>Argumentdefinitionen

Argumente im Prototyp:

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

Mit den genannten Argumenten können Sie einfache Befehlszeilenanalysen von Argumenten ausführen und optional auf Umgebungsvariablen zugreifen. Die Argumentdefinitionen sind wie folgt:

*argc*<br/>
Eine ganze Zahl, die die Anzahl der Argumente, die enthält in folgen *Argv*. Die *Argc* Parameter ist immer größer als oder gleich 1.

*argv*<br/>
Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß der Konvention `argv` **[0]** ist der Befehl, mit denen das Programm aufgerufen wird, `argv` **[1]** ist das erste Befehlszeilenargument, und So weiter, bis `argv`  **[**`argc`**]**, die immer NULL ist. Finden Sie unter [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md) Informationen zum Unterdrücken der befehlszeilenverarbeitung.

Das erste Befehlszeilenargument ist immer `argv` **[1]** und das letzte ist `argv` **[** `argc` - 1 **]**.

> [!NOTE]
>  Gemäß der Konvention ist `argv`**[0]** der Befehl, mit dem das Programm aufgerufen wird.  Es ist jedoch möglich, einen Prozess mit [CreateProcess](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea) und bei der Verwendung der ersten und zweiten Argument (*LpApplicationName* und *LpCommandLine*), `argv` **[0]** möglicherweise nicht die ausführbare Datei benennen; verwenden Sie [GetModuleFileName](/windows/desktop/api/libloaderapi/nf-libloaderapi-getmodulefilenamea) Name der ausführbaren Datei und den vollständig qualifizierten Pfad abrufen.

## <a name="microsoft-specific"></a>Microsoft-spezifisch

*envp*<br/>
Die *Envp* Array, das eine verbreitete Erweiterung in vielen UNIX-Systemen ist, wird in Microsoft C++ verwendet. Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Das Array wird mit einem NULL-Eintrag beendet. Sie können deklariert werden, als ein Array von Zeigern auf **Char (Char** \*Envp []**)** oder als Zeiger auf Zeiger **Char (Char** \* \* Envp **)**. Wenn das Programm `wmain` anstelle von `main`, verwenden Sie die `wchar_t` -Datentyp anstelle von **Char**. Der Umgebungsblock, die an `main` und `wmain` ist eine "fixierte" Kopie der aktuellen Umgebung. Wenn Sie später, die Umgebung durch einen Aufruf von ändern `putenv` oder `_wputenv`, der aktuellen Umgebung (wie vom `getenv` / `_wgetenv` und `_environ` /  `_wenviron` Variable) wird ändern, aber der verweist Envp Block wird nicht geändert. Finden Sie unter [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md) Informationen zum Unterdrücken der umgebungsverarbeitung. Dieses Argument ist in C ANSI-kompatibel, aber nicht in C++.

**Ende Microsoft-spezifisch**

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Sie mit der *Argc*, *Argv*, und *Envp* Argumente `main`:

```cpp
// argument_definitions.cpp
// compile with: /EHsc
#include <iostream>
#include <string.h>

using namespace std;
int main( int argc, char *argv[], char *envp[] ) {
    int iNumberLines = 0;    // Default is no line numbers.

    // If /n is passed to the .exe, display numbered listing
    // of environment variables.

    if ( (argc == 2) && _stricmp( argv[1], "/n" ) == 0 )
         iNumberLines = 1;

    // Walk through list of strings until a NULL is encountered.
    for( int i = 0; envp[i] != NULL; ++i ) {
        if( iNumberLines )
            cout << i << ": " << envp[i] << "\n";
    }
}
```

## <a name="see-also"></a>Siehe auch

[main: Programmstart](../cpp/main-program-startup.md)