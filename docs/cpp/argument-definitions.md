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
ms.openlocfilehash: 14e5ea3a051d81828c5f88ac16df60b6ebb5b559
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69498817"
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
Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß der Konvention `argv[0]` ist der Befehl, mit dem das Programm aufgerufen wird `argv[1]` , das erste Befehlszeilenargument usw., bis `argv[argc]`, das immer NULL ist. Informationen zum Unterdrücken der Befehlszeilen Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) .

Das erste Befehlszeilenargument ist immer `argv[1]`, und das letzte ist `argv[argc - 1]`.

> [!NOTE]
> Gemäß der Konvention `argv[0]` ist der Befehl, mit dem das Programm aufgerufen wird.  Es ist jedoch möglich, einen [Prozess mithilfe von](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) "" zu erzeugen, und wenn Sie sowohl das erste als auch das zweite Argument (*lpApplicationName* und *lpCommandLine*) verwenden, `argv[0]` ist möglicherweise nicht der Name der ausführbaren Datei. verwenden Sie " [GetModuleFileName". ](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew), um den Namen der ausführbaren Datei und den voll qualifizierten Pfad abzurufen.

## <a name="microsoft-specific"></a>Microsoft-spezifisch

*envp*<br/>
Das *envp* -Array, bei dem es sich um eine gemeinsame Erweiterung in vielen UNIX- C++Systemen handelt, wird in Microsoft verwendet. Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Das Array wird mit einem NULL-Eintrag beendet. Sie kann als ein Array von Zeigern auf **char** `char *envp[]`() oder als Zeiger auf Zeiger auf **char** (`char **envp`) deklariert werden. Wenn das Programm anstelle `wmain` von `main`verwendet, verwenden Sie den **wchar_t** -Datentyp anstelle von **char**. Der an und `main` `wmain` über gegebene Umgebungsblock ist eine "fixierte" Kopie der aktuellen Umgebung. Wenn Sie anschließend die Umgebung mithilfe eines Aufrufes `putenv` von `_wputenv`oder ändern, ändert sich die aktuelle Umgebung `getenv` ( `_wgetenv` wie von `_environ` oder `_wenviron` und der-oder-Variable zurückgegeben), aber der Block, auf den von verwiesen wird. der Name der Anmeldung wird nicht geändert. Informationen zum Unterdrücken der Umgebungs Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) . Dieses Argument ist in C ANSI-kompatibel, aber nicht in C++.

**Ende Microsoft-spezifisch**

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird gezeigt, wie Sie die Argumente *argc*, *argv*und in `main`den folgenden *Themen* verwenden:

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