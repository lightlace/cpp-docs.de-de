---
title: "Argumentdefinitionen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argc-Argument"
  - "Argumente [C++], Für main-Funktion"
  - "argv-Argument"
  - "envp-Argument"
  - "main-Funktion, Argumente"
ms.assetid: 6148cbf3-ebe8-44f2-b277-de4b723991c7
caps.latest.revision: 13
caps.handback.revision: "13"
ms.author: "mblome"
manager: "ghogen"
---
# Argumentdefinitionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Argumente im Prototyp:  
  
```  
  
int main( int argc[ , char *argv[ ] [, char *envp[ ] ] ] ); int wmain( int argc[ , wchar_t *argv[ ] [, wchar_t *envp[ ] ] ] );  
```  
  
 Mit den genannten Argumenten können Sie einfache Befehlszeilenanalysen von Argumenten ausführen und optional auf Umgebungsvariablen zugreifen.  Die Argumentdefinitionen sind wie folgt:  
  
 `argc`  
 Eine ganze Zahl, die die Anzahl von Argumenten enthält, die in `argv` folgen.  Der `argc`\-Parameter ist immer größer als oder gleich 1.  
  
 `argv`  
 Ein Array von Zeigern auf Zeichenfolgen, die auf NULL enden und von den Benutzern des Programms eingegebene Befehlszeilenargumente darstellen.  Gemäß der Konvention ist `argv`**\[0\]** der Befehl, mit dem das Programm aufgerufen wird, `argv`**\[1\]** ist das erste Befehlszeilenargument, und so geht es weiter bis zu `argv`**\[**`argc`**\]**, das immer **NULL** ist.  Informationen zum Unterdrücken der Befehlszeilenverarbeitung finden Sie in der Erläuterung zum [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md).  
  
 Das erste Befehlszeilenargument ist immer `argv`**\[1\]**, und das letzte ist `argv`**\[**`argc` – 1**\]**.  
  
> [!NOTE]
>  Gemäß der Konvention ist `argv`**\[0\]** der Befehl, mit dem das Programm aufgerufen wird.  Allerdings es ist möglich, einen Prozess mit [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms683197) zu erstellen, und wenn Sie sowohl das erste als auch das zweite Argument \(`lpApplicationName` und `lpCommandLine`\) verwenden, ist `argv`**\[0\]** möglicherweise nicht der ausführbare Name. Verwenden Sie [GetModuleFileName](http://msdn.microsoft.com/library/windows/desktop/ms683197), um den ausführbaren Namen und dessen vollqualifizierten Pfad abzurufen.  
  
## Microsoft\-spezifisch  
 `envp`  
 In Microsoft C\+\+ wird das `envp`\-Array verwendet, das eine verbreitete Erweiterung in vielen UNIX\-Systemen ist.  Es ist ein Zeichenfolgenarray, das die Variablen darstellt, die in der Benutzerumgebung festgelegt werden.  Das Array wird mit einem **NULL**\-Eintrag beendet.  Es kann als Array von Zeigern auf **char \(char** \*envp\[ \]**\)** oder als ein Zeiger auf die Zeiger auf **char \(char** \*\*envp**\)** deklariert sein.  Wenn das Programm **wmain** anstelle von **main** verwendet, verwenden Sie den `wchar_t`\-Datentyp anstelle von `char`.  Beachten Sie, dass der Umgebungsblock, der an **main** und **wmain** übergeben wird, eine "fixierte" Kopie der aktuellen Umgebung ist.  Wenn Sie danach die Umgebung durch einen Aufruf von **putenv** oder `_wputenv` ändern, wird die aktuelle Umgebung geändert \(wie durch `getenv`\/`_wgetenv` und die `_environ`\/ `_wenviron`\-Variablen zurückgegeben\), aber der von "envp" referenzierte Block ändert sich nicht.  Informationen zum Unterdrücken der Umgebungsverarbeitung finden Sie in der Erläuterung zum [Anpassen der Befehlszeilenverarbeitung](../cpp/customizing-cpp-command-line-processing.md).  Dieses Argument ist in C ANSI\-kompatibel, aber nicht in C\+\+.  
  
## END Microsoft\-spezifisch  
  
## Beispiel  
 Im folgenden Beispiel wird die Verwendung der Argumente `argc`, `argv` und `envp` für **main** gezeigt:  
  
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
  
## Siehe auch  
 [main: Programmstart](../cpp/main-program-startup.md)