---
title: Main-Funktion und Befehlszeilenargumente (C++)
description: Die Main-Funktion ist der Einstiegspunkt für C++ ein Programm.
ms.date: 12/10/2019
ms.assetid: c6568ee6-40ab-4ae8-aa44-c99e232f64ac
ms.openlocfilehash: 95e774700c63dc815f6d814bfda84a38a38d4e6e
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302409"
---
# <a name="main-function-and-command-line-arguments"></a>Main-Funktion und Befehlszeilenargumente

Alle C++ Programme müssen über eine `main`-Funktion verfügen. Wenn Sie versuchen, ein C++ *exe* -Projekt ohne eine Main-Funktion zu kompilieren, gibt der Compiler einen Fehler aus. (Dynamic-Link-Bibliotheken und statische Bibliotheken haben keine `main`-Funktion.) Die `main`-Funktion ist der Ort, an dem der Quellcode mit der Ausführung beginnt, aber bevor ein Programm in die `main`-Funktion eintritt, werden alle statischen Klassenmember ohne explizite Initialisierer auf NULL festgelegt. In Microsoft C++werden globale statische Objekte auch vor dem Eintrag in `main`initialisiert. Einige Einschränkungen gelten für die `main` Funktion, die nicht für andere C++ Funktionen gelten. Die `main`-Funktion:

- Kann nicht überladen werden (siehe [Funktions Überladung](function-overloading.md)).
- Kann nicht als **Inline**deklariert werden.
- Kann nicht als **statisch**deklariert werden.
- Ihre Adresse kann nicht übernommen werden.
- Kann nicht aufgerufen werden.

Die Deklarationssyntax für `main` lautet wie folgt:

```cpp
int main();
int main(int argc, char *argv[], char *envp[]);
```

**Microsoft-spezifisch**

Wenn die Quelldateien Unicode-breit Zeichen verwenden, können Sie `wmain`verwenden, bei dem es sich um die breit Zeichen Version von `main`handelt. Die Deklarationssyntax für `wmain` lautet wie folgt:

```cpp
int wmain( );
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);
```

Sie können auch `_tmain`verwenden, das in Tchar. h definiert ist. `_tmain` wird in `main` aufgelöst, sofern nicht _UNICODE definiert ist. In diesem Fall wird `_tmain` in `wmain` aufgelöst.

Wenn kein Rückgabewert angegeben wird, gibt der Compiler einen Rückgabewert von 0 (null) an. Alternativ können die Funktionen `main` und `wmain` als Rückgabe von **void** (kein Rückgabewert) deklariert werden. Wenn Sie `main` oder `wmain` als Rückgabe von **void**deklarieren, können Sie keinen Exitcode an den übergeordneten Prozess oder das Betriebssystem zurückgeben, indem Sie eine [Return](../cpp/return-statement-in-program-termination-cpp.md) -Anweisung verwenden. Um einen Exitcode zurückzugeben, wenn `main` oder `wmain` als **void**deklariert ist, müssen Sie die [Exit](../cpp/exit-function.md) -Funktion verwenden.

**Ende Microsoft-spezifisch**

## <a name="command-line-arguments"></a>Befehlszeilenargumente

Die Argumente für `main` oder `wmain` ermöglichen eine bequeme Befehlszeilen-Analyse von Argumenten und optional Zugriff auf Umgebungsvariablen. Die Typen für `argc` und `argv` werden von der Programmiersprache definiert. Die Namen `argc`, `argv`und `envp` sind traditionell, Sie können Sie jedoch beliebig benennen.

```cpp
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);
```

Die Argumentdefinitionen sind wie folgt:

*argc*<br/>
Eine ganze Zahl, die die Anzahl von Argumenten enthält, die in *argv*befolgt werden. Der *argc* -Parameter ist immer größer als oder gleich 1.

*argv*<br/>
Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß der Konvention ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird, `argv[1]` ist das erste Befehlszeilenargument usw., bis `argv[argc]`, das immer NULL ist. Informationen zum Unterdrücken der Befehlszeilen Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) .

Das erste Befehlszeilenargument ist immer `argv[1]`, und das letzte ist `argv[argc - 1]`.

> [!NOTE]
> Gemäß der Konvention ist `argv[0]` der Befehl, mit dem das Programm aufgerufen wird. Es ist jedoch möglich, einen Prozess mithilfe von " [deateprocess](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) " zu erzeugen, und wenn Sie sowohl das erste als auch das zweite Argument (*lpApplicationName* und *lpCommandLine*) verwenden, ist `argv[0]` möglicherweise nicht der Name der ausführbaren Datei. Verwenden Sie [GetModuleFileName](/windows/win32/api/libloaderapi/nf-libloaderapi-getmodulefilenamew) , um den Namen der ausführbaren Datei und den voll qualifizierten Pfad abzurufen.

**Microsoft-spezifisch**

*envp*<br/>
Das *envp* -Array, bei dem es sich um eine gemeinsame Erweiterung in vielen UNIX- C++Systemen handelt, wird in Microsoft verwendet. Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Das Array wird mit einem NULL-Eintrag beendet. Sie kann als ein Array von Zeigern auf **char** (`char *envp[]`) oder als Zeiger auf Zeiger auf **char** (`char **envp`) deklariert werden. Wenn das Programm anstelle von `main``wmain` verwendet, verwenden Sie den **wchar_t** -Datentyp anstelle von **char**. Der Umgebungsblock, der an `main` und `wmain` übermittelt wird, ist eine "fixierte" Kopie der aktuellen Umgebung. Wenn Sie anschließend die Umgebung mithilfe eines Aufrufes `putenv` oder `_wputenv`ändern, ändert sich die aktuelle Umgebung (wie von `getenv` oder `_wgetenv` und der `_environ`-oder `_wenviron` Variablen zurückgegeben), aber der Block, auf den von ' SVP ' verwiesen wird, ändert sich nicht. Informationen zum Unterdrücken der Umgebungs Verarbeitung finden Sie unter [Anpassen der Befehlszeilen Verarbeitung](../cpp/customizing-cpp-command-line-processing.md) . Dieses Argument ist in C ANSI-kompatibel, aber nicht in C++.

**Ende Microsoft-spezifisch**

### <a name="example"></a>Beispiel

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

## <a name="parsing-c-command-line-arguments"></a>Parsing C++ -Befehlszeilenargumente

**Microsoft-spezifisch**

Beim Interpretieren von Argumenten, die in der Befehlszeile des Betriebssystems angegeben werden, verwendet der Microsoft C/C++-Startcode die folgenden Regeln:

- Argumente werden durch einen Leerraum (Leerzeichen oder Tabstopp) abgegrenzt.

- Die Einfügemarke (^) wird nicht als Escape- oder Trennzeichen erkannt. Das Zeichen wird vom Befehlszeilenparser im Betriebssystem vollständig verarbeitet, bevor es an das `argv`-Array im Programm übergeben wird.

- Eine Zeichenfolge, die in doppelten Anführungszeichen ("*String*") eingeschlossen ist, wird als einzelnes Argument interpretiert, unabhängig von Leerraum, der in enthalten ist. Eine Zeichenfolge in Anführungszeichen kann in ein Argument eingebettet sein.

- Wenn dem Anführungszeichen ein umgekehrter Schrägstrich (\\") vorangestellt wird, wird diese Zeichenfolge als literales Anführungszeichen (") interpretiert.

- Ein umgekehrter Schrägstrich wird als solcher interpretiert, sofern er nicht unmittelbar vor einem Anführungszeichen steht.

- Wenn ein doppeltes Anführungszeichen auf eine gerade Anzahl umgekehrter Schrägstriche folgt, wird für jedes Paar umgekehrter Schrägstriche ein umgekehrter Schrägstrich im `argv`-Array platziert. Das doppelte Anführungszeichen wird als Zeichenfolgentrennzeichen interpretiert.

- Wenn auf eine ungerade Anzahl umgekehrter Schrägstriche ein doppeltes Anführungszeichen folgt, wird für jedes Paar von umgekehrten Schrägstrichen ein umgekehrter Schrägstrich in das `argv`-Array eingefügt, und das doppelte Anführungszeichen wird vom verbleibenden umgekehrten Schrägstrich mit einem Escapezeichen versehen, sodass ein echtes doppeltes Anführungszeichen (") in `argv` eingefügt wird.

### <a name="example"></a>Beispiel

Das folgende Programm zeigt, wie Befehlszeilenargumente übergeben werden:

```cpp
// command_line_arguments.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;
int main( int argc,      // Number of strings in array argv
          char *argv[],   // Array of command-line argument strings
          char *envp[] )  // Array of environment variable strings
{
    int count;

    // Display each command-line argument.
    cout << "\nCommand-line arguments:\n";
    for( count = 0; count < argc; count++ )
         cout << "  argv[" << count << "]   "
                << argv[count] << "\n";
}
```

Die folgende Tabelle zeigt beispielhafte Eingaben und zu erwartende Ausgaben, wobei die Regeln in der vorangehenden Liste aufgezeigt werden.

### <a name="results-of-parsing-command-lines"></a>Ergebnisse der Befehlszeilen Verarbeitung

|Befehlszeileneingabe|argv[1]|argv[2]|argv[3]|
|-------------------------|---------------|---------------|---------------|
|`"abc" d e`|`abc`|`d`|`e`|
|`a\\b d"e f"g h`|`a\\b`|`de fg`|`h`|
|`a\\\"b c d`|`a\"b`|`c`|`d`|
|`a\\\\"b c" d e`|`a\\b c`|`d`|`e`|

**Ende Microsoft-spezifisch**

## <a name="wildcard-expansion"></a>Platzhaltererweiterung

**Microsoft-spezifisch**

Sie können Platzhalter – das Fragezeichen (?) und das Sternchen (*) – verwenden, um Dateinamen- und Pfadargumente in der Befehlszeile anzugeben.

Befehlszeilenargumente werden von einer Routine mit dem Namen `_setargv` behandelt (oder in der breit Zeichen Umgebung `_wsetargv`), die standardmäßig keine Platzhalter in separate Zeichen folgen im `argv` Zeichen folgen Array erweitert. Weitere Informationen zum Aktivieren der Platzhalter Erweiterung finden Sie unter Erweitern von Platzhalter [Argumenten](../c-language/expanding-wildcard-arguments.md).

**Ende Microsoft-spezifisch**

## <a name="customizing-c-command-line-processing"></a>Anpassen der C++-Befehlszeilenverarbeitung

**Microsoft-spezifisch**

Wenn das Programm keine Befehlszeilenargumente akzeptiert, können Sie ein wenig Platz sparen, indem Sie die Verwendung der Bibliotheksroutine unterdrücken, die die Befehlszeilenverarbeitung ausführt. Diese Routine wird `_setargv` aufgerufen und unter Platzhalter [Erweiterung](../cpp/wildcard-expansion.md)beschrieben. Um die Verwendung zu unterdrücken, definieren Sie eine Routine, die in der Datei mit der `main`-Funktion keine Aktion ausführt, und benennen Sie Sie `_setargv`. Der `_setargv`-wird dann durch die Definition von `_setargv`erfüllt, und die Bibliotheksversion wird nicht geladen.

Wenn Sie auf die Umgebungs Tabelle nicht über das `envp`-Argument zugreifen, können Sie auch eine eigene leere Routine bereitstellen, die anstelle von `_setenvp`, der Umgebungs Verarbeitungsroutine, verwendet werden soll. Genau wie bei der `_setargv`-Funktion müssen `_setenvp` als **extern "C"** deklariert werden.

Das Programm kann in der C-Lauf Zeit Bibliothek Aufrufe an die `spawn` oder `exec` Familie von Routinen tätigen. Wenn dies der Fall ist, sollten Sie die umgebungsverarbeitende Routine nicht unterdrücken, da diese Routine verwendet wird, um eine Umgebung aus dem übergeordneten Prozess an den untergeordneten Prozess zu übergeben.

**Ende Microsoft-spezifisch**

## <a name="see-also"></a>Siehe auch

[Grundlegende Konzepte](../cpp/basic-concepts-cpp.md)