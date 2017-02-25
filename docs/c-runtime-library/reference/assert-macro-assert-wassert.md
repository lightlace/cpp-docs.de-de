---
title: "assert-Makro, _assert, _wassert | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "assert"
  - "_assert"
  - "_wassert"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "assert"
  - "_assert"
  - "_wassert"
  - "assert/_wassert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Abbrechen von Programmen"
  - "assert-Funktion"
  - "assert-Makro"
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# assert-Makro, _assert, _wassert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Wertet einen Ausdruck aus, gibt eine Diagnosemeldung aus und bricht das Programm ab, wenn das Ergebnis `false` ist.  
  
## Syntax  
  
```  
assert(   
   expression   
);  
void _assert(  
   char const* message,  
   char const* filename,  
   unsigned line  
);  
void _wassert(  
   wchar_t const* message,  
   wchar_t const* filename,  
   unsigned line  
);  
```  
  
#### Parameter  
 `expression`  
 Ein skalarer Ausdruck \(einschließlich Zeigerausdrücken\) der zu ungleich null \(`true`\) oder „0“ \(`false`\) ausgewertet wird.  
  
 `message`  
 Die anzuzeigende Meldung.  
  
 `filename`  
 Der Name der Quelldatei, in der der Assertionsfehler aufgetreten ist.  
  
 `line`  
 Die Zeilennummer in der Quelldatei mit dem Assertionsfehler.  
  
## Hinweise  
 Das `assert`\-Makro wird normalerweise verwendet, um Logikfehler während der Programmentwicklung zu erkennen. Verwenden Sie es, um die Programmausführung zu beenden, wenn unerwartete Bedingungen eintreten, indem Sie das `expression`\-Argument so implementieren, dass es nur dann als `false` ausgewertet wird, wenn das Programm nicht ordnungsgemäß arbeitet. Assertionsprüfungen können zur Kompilierzeit durch Definition des Makros `NDEBUG` deaktiviert werden. Deaktivieren der `assert` Makro ohne Ändern von Quelldateien mit einer **\/DNDEBUG** \-Befehlszeilenoption. Sie können das `assert`\-Makro im Quellcode durch eine `#define NDEBUG`\-Anweisung vor dem Einschließen von \<assert.h\> deaktivieren.  
  
 Das `assert`\-Makro gibt eine Diagnosemeldung aus, wenn `expression` zu `false` \(0\) ausgewertet wird, und ruft [abort](../../c-runtime-library/reference/abort.md) auf, um die Programmausführung zu beenden. Es wird keine Aktion ausgeführt, wenn `expression``true` \(ungleich null\) ist. Die Diagnosemeldung enthält den Ausdruck, für den der Fehler aufgetreten ist, den Namen der Quelldatei und die Nummer der Zeile, in der der Assertionsfehler aufgetreten ist.  
  
 Die Diagnosemeldung wird in Breitzeichen ausgegeben. Daher funktioniert sie auch dann erwartungsgemäß, wenn sich Unicode\-Zeichen im Ausdruck befinden.  
  
 Das Ziel der Diagnosemeldung hängt vom Typ der Anwendung ab, die die Routine aufgerufen hat. Konsolenanwendungen erhalten die Meldung immer über `stderr`. In einer Windows\-basierten Anwendung ruft `assert` die [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505)\-Funktion von Windows auf, um ein Meldungsfeld zu erstellen, in dem die Meldung zusammen mit einer **OK**\-Schaltfläche angezeigt wird. Wenn der Benutzer auf **OK** klickt, wird das Programm sofort beendet.  
  
 Wenn die Anwendung mit einer Debugversion der Laufzeitbibliotheken verknüpft ist, erstellt `assert` ein Meldungsfeld mit drei Schaltflächen: **Abbrechen**, **Wiederholen** und **Ignorieren**. Wenn der Benutzer auf **Abbrechen** klickt, wird das Programm sofort beendet. Wenn der Benutzer auf **Wiederholen** klickt, wird der Debugger aufgerufen und der Benutzer kann das Programm debuggen, wenn Just\-In\-Time \(JIT\)\-Debuggen aktiviert ist. Wenn der Benutzer auf **Ignorieren** klickt, setzt `assert` die normale Ausführung fort und erstellt das Meldungsfeld mit der Schaltfläche **OK**. Wenn ein Fehlerzustand vorliegt, kann das Klicken auf **Ignorieren** zu undefiniertem Verhalten führen.  
  
 Weitere Informationen zum CRT\-Debugging \(C Runtime Library\) finden Sie unter [CRT\-Debugverfahren](../Topic/CRT%20Debugging%20Techniques.md).  
  
 Die Funktionen `_assert` und `_wassert` sind interne CRT\-Funktionen. Sie helfen dabei, den für die Unterstützung von Assertion in Ihren Objektdateien erforderlichen Code zu minimieren. Wir empfehlen nicht, diese Funktionen direkt aufzurufen.  
  
 Das `assert`\-Makro ist sowohl in der endgültigen als auch in der Debugversion der C\-Laufzeitbibliotheken aktiviert, wenn `NDEBUG` nicht definiert ist. Wenn `NDEBUG` definiert ist, ist das Makro verfügbar, wertet aber seine Argumente nicht aus und bleibt ohne Wirkung. Wenn es aktiviert ist, ruft das `assert`\-Makro `_wassert` zu seiner Implementierung auf. Andere Assertionsmakros, [\_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), [\_ASSERTE](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) und [\_ASSERT\_EXPR](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md), sind ebenfalls verfügbar, sie werten die ihnen übergebenen Ausdrücke jedoch nur aus, wenn das [\_DEBUG](../../c-runtime-library/debug.md)\-Makro definiert wurde und sie sich in Code befinden, der mit der Debugversion der C\-Laufzeitbibliotheken gelinkt wurde.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`assert`, `_wassert`|\<assert.h\>|  
  
 Die Signatur der `_assert`\-Funktion ist nicht in einer Headerdatei verfügbar. Die Signatur der `_wassert`\-Funktion ist nur verfügbar, wenn das `NDEBUG`\-Makro nicht definiert ist.  
  
## Beispiel  
 In diesem Programm verwendet die `analyze_string`\-Funktion das `assert`\-Makro, um verschiedene Bedingungen im Zusammenhang mit der Zeichenfolge und ihrer Länge zu prüfen. Wenn bei einer der Bedingungen ein Fehler auftritt, gibt das Programm eine Meldung aus, die auf die Ursache des Fehlers hinweist.  
  
```  
// crt_assert.c  
// compile by using: cl /W4 crt_assert.c  
#include <stdio.h>  
#include <assert.h>  
#include <string.h>  
  
void analyze_string( char *string );   // Prototype  
  
int main( void )  
{  
   char  test1[] = "abc", *test2 = NULL, test3[] = "";  
  
   printf ( "Analyzing string '%s'\n", test1 ); fflush( stdout );  
   analyze_string( test1 );  
   printf ( "Analyzing string '%s'\n", test2 ); fflush( stdout );  
   analyze_string( test2 );  
   printf ( "Analyzing string '%s'\n", test3 ); fflush( stdout );  
   analyze_string( test3 );  
}  
  
// Tests a string to see if it is NULL,   
// empty, or longer than 0 characters.  
void analyze_string( char * string )  
{  
   assert( string != NULL );        // Cannot be NULL  
   assert( *string != '\0' );       // Cannot be empty  
   assert( strlen( string ) > 2 );  // Length must exceed 2  
}  
```  
  
 Das Programm erzeugt diese Ausgabe:  
  
```Output  
Analyse von Zeichenfolge 'abc' Analyse von Zeichenfolge '(null)' Assertionsfehler: Zeichenfolge != NULL, Datei „crt_assert.c“, Zeile 25  
```  
  
 Je nach Version von Betriebssystem und Laufzeitbibliothek, wird möglicherweise nach dem Assertionsfehler ein Meldungsfeld angezeigt, das etwas in dieser Art enthält:  
  
```Output  
Aufgrund eines Problems funktioniert das Programm nicht mehr ordnungsgemäß. Windows schließt das Programm und benachrichtigt Sie, sobald eine Lösung verfügbar ist.  
```  
  
 Wenn ein Debugger installiert ist, wählen Sie die Schaltfläche **Debug** aus, um den Debugger zu starten, oder **Programm schließen** zum Beenden.  
  
## .NET Framework-Entsprechung  
 [System::Diagnostics::Debug::Assert](https://msdn.microsoft.com/en-us/library/system.diagnostics.debug.assert.aspx)  
  
## Siehe auch  
 [Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)   
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [raise](../../c-runtime-library/reference/raise.md)   
 [signal](../../c-runtime-library/reference/signal.md)   
 [\_ASSERT\-, \_ASSERTE\-, \_ASSERT\_EXPR\-Makros](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [\_DEBUG](../../c-runtime-library/debug.md)