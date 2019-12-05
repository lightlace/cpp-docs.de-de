---
title: Argumentdefinitionen
ms.date: 11/04/2016
helpviewer_keywords:
- envp argument
- main function, arguments
- arguments [C++], for main function
- argv argument
- argc argument
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
ms.openlocfilehash: aebd4800ad8d653d532708784ef0a5333211d46b
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857657"
---
# <a name="argument-definitions"></a>Argumentdefinitionen

Argumente im Prototyp:

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

Mit den genannten Argumenten können Sie einfache Befehlszeilenanalysen von Argumenten ausführen und optional auf Umgebungsvariablen zugreifen. Die Argumentdefinitionen sind wie folgt:

*argc*<br/>
Eine ganze Zahl, die die Anzahl von Argumenten enthält, die in *argv*befolgt werden. Der *argc* -Parameter ist immer größer als oder gleich 1.

*argv*<br/>
Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß der Konvention ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird, `argv[1]` ist das erste Befehlszeilenargument usw., bis `argv[argc]`, das immer NULL ist. Informationen zum Unterdrücken der Befehlszeilen Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) .

Das erste Befehlszeilenargument ist immer `argv[1]`, und das letzte ist `argv[argc - 1]`.

> [!NOTE]
> Gemäß der Konvention ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird.  Es ist jedoch möglich, einen Prozess mithilfe von " [deateprocess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) " zu erzeugen, und wenn Sie sowohl das erste als auch das zweite Argument (*lpApplicationName* und *lpCommandLine*) verwenden, ist `argv[0]` möglicherweise nicht der Name der ausführbaren Datei. Verwenden Sie [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) , um den Namen der ausführbaren Datei und den voll qualifizierten Pfad abzurufen.

**Microsoft-spezifisch**

*envp*<br/>
Das *envp* -Array, bei dem es sich um eine gemeinsame Erweiterung in vielen UNIX- C++Systemen handelt, wird in Microsoft verwendet. Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Das Array wird mit einem NULL-Eintrag beendet. Sie kann als ein Array von Zeigern auf **char** (`char *envp[]`) oder als Zeiger auf Zeiger auf **char** (`char **envp`) deklariert werden. Wenn das Programm anstelle von `main``wmain` verwendet, verwenden Sie den **wchar_t** -Datentyp anstelle von **char**. Der Umgebungsblock, der an `main` und `wmain` übermittelt wird, ist eine "fixierte" Kopie der aktuellen Umgebung. Wenn Sie anschließend die Umgebung mithilfe eines Aufrufes `putenv` oder `_wputenv`ändern, ändert sich die aktuelle Umgebung (wie von `getenv` oder `_wgetenv` und der `_environ`-oder `_wenviron` Variablen zurückgegeben), aber der Block, auf den von ' SVP ' verwiesen wird, ändert sich nicht. Informationen zum Unterdrücken der Umgebungs Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) . Dieses Argument ist in C ANSI-kompatibel, aber nicht in C++.

**Ende Microsoft-spezifisch**

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie *die Argumente* *argc*, *argv*und in der `main`-Argumente verwendet werden, um zu:

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