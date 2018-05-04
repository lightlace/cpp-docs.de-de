---
title: Argumentdefinitionen | Microsoft Docs
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
ms.openlocfilehash: ca012d7b391e011d9658b0b74e0f4433d5dc9fd4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="argument-definitions"></a>Argumentdefinitionen
Argumente im Prototyp:  
  
```  
  
int main( int argc, char* argv[], char* envp[]);
int wmain( int argc, wchar_t* argv[], wchar_t* envp[]);  
```  
  
 Mit den genannten Argumenten können Sie einfache Befehlszeilenanalysen von Argumenten ausführen und optional auf Umgebungsvariablen zugreifen. Die Argumentdefinitionen sind wie folgt:  
  
 `argc`  
 Eine ganze Zahl, die die Anzahl von Argumenten enthält, die in `argv` folgen. Der `argc`-Parameter ist immer größer als oder gleich 1.  
  
 `argv`  
 Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen. Gemäß der Konvention `argv` **[0]** ist der Befehl, mit denen das Programm aufgerufen wird, `argv` **[1]** ist die erste Befehlszeilenargument usw., bis `argv`  **[**`argc`**]**, also immer **NULL**. Finden Sie unter [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md) Informationen zum Unterdrücken der befehlszeilenverarbeitung.  
  
 Das erste Befehlszeilenargument ist immer `argv` **[1]** und der letzte ist `argv` **[** `argc` - 1 **]**.  
  
> [!NOTE]
>  Gemäß der Konvention ist `argv`**[0]** der Befehl, mit dem das Programm aufgerufen wird.  Allerdings ist es möglich, einen Prozess mithilfe erzeugen [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) und bei Verwendung der ersten und zweiten Arguments (`lpApplicationName` und `lpCommandLine`), `argv` **[0]** möglicherweise nicht die Namen der ausführbaren Datei; Verwenden Sie [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197) Namen der ausführbaren Datei und den vollqualifizierten Pfad abrufen.  
  
## <a name="microsoft-specific"></a>Microsoft-spezifisch  
 `envp`  
 In Microsoft C++ wird das `envp`-Array verwendet, das eine verbreitete Erweiterung in vielen UNIX-Systemen ist. Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden. Dieses Array wird beendet, indem eine **NULL** Eintrag. Sie können deklariert werden, als ein Array von Zeigern auf **Char (Char** \*Envp []**)** oder als Zeiger auf Zeiger **Char (Char** \* \* Envp **)**. Wenn das Programm **"wmain"** anstelle von **main**, verwenden Sie die `wchar_t` -Datentyp anstelle von `char`. Der Umgebungsblock übergeben **main** und **"wmain"** ist eine "fixierte" Kopie der aktuellen Umgebung. Wenn Sie anschließend die Umgebung durch einen Aufruf von ändern **Putenv** oder `_wputenv`, der aktuellen Umgebung (wie vom `getenv` / `_wgetenv` und die `_environ` /  `_wenviron` Variable) ändern, aber der verweist Envp Block wird nicht ändert. Finden Sie unter [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md) Informationen zum Unterdrücken der umgebungsverarbeitung. Dieses Argument ist in C ANSI-kompatibel, aber nicht in C++.  
  
**Ende Microsoft-spezifisch**  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die `argc`, `argv`, und `envp` Argumente **main**:  
  
```  
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