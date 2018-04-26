---
title: assert-Makro, _assert, _wassert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- assert
- _assert
- _wassert
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- assert
- _assert
- _wassert
- assert/_wassert
dev_langs:
- C++
helpviewer_keywords:
- aborting programs
- assert function
- assert macro
ms.assetid: a9ca031a-648b-47a6-bdf1-65fc7399dd40
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 573226f92b585b6bb158d0c8f9ba5c24af0f7bde
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2018
---
# <a name="assert-macro-assert-wassert"></a>assert-Makro, _assert, _wassert

Wertet einen Ausdruck und das Ergebnis ist **"false"**, gibt eine diagnosemeldung und bricht das Programm ab.

## <a name="syntax"></a>Syntax

```C
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

### <a name="parameters"></a>Parameter

*Ausdruck* ein skalarer Ausdruck (einschließlich zeigerausdrücken), der zu ungleich null ergibt (**"true"**) oder 0 (**"false"**).

*Nachricht* die anzuzeigende Meldung.

*FileName* der Assertionsfehler der Datei des Namens der Quelle.

*Zeile* die Zeilennummer in der Quelldatei mit dem Assertionsfehler.

## <a name="remarks"></a>Hinweise

Die **assert** -Makro wird normalerweise verwendet, um Logikfehler während der Programmentwicklung zu identifizieren. Verwenden, um die programmausführung zu beenden, wenn unerwartete Bedingungen, durch die Implementierung auftreten der *Ausdruck* Argument ausgewertet **"false"** nur wenn das Programm nicht ordnungsgemäß arbeitet. Assertionsprüfungen können deaktiviert werden zur Kompilierzeit durch Definition des Makros **NDEBUG**. Können Sie deaktivieren die **assert** Makro ohne Änderung der Quelldateien mit einer **/DNDEBUG** Befehlszeilenoption. Können Sie deaktivieren die **assert** -Makro im Quellcode mithilfe einer `#define NDEBUG` Richtlinie vor \<assert.h > enthalten ist.

Die **assert** -Makro gibt eine diagnosemeldung aus, wenn *Ausdruck* ergibt **"false"** (0) und ruft [abort](abort.md) Programm beenden die Ausführung. Es wird keine Aktion ausgeführt, wenn *Ausdruck* ist **"true"** (ungleich null). Die Diagnosemeldung enthält den Ausdruck, für den der Fehler aufgetreten ist, den Namen der Quelldatei und die Nummer der Zeile, in der der Assertionsfehler aufgetreten ist.

Die Diagnosemeldung wird in Breitzeichen ausgegeben. Daher funktioniert sie auch dann erwartungsgemäß, wenn sich Unicode-Zeichen im Ausdruck befinden.

Das Ziel der Diagnosemeldung hängt vom Typ der Anwendung ab, die die Routine aufgerufen hat. Konsolenanwendungen erhalten die Meldung immer über **"stderr"**. In einer Windows-basierten Anwendung **assert** ruft Windows [MessageBox](http://msdn.microsoft.com/library/windows/desktop/ms645505) Funktion so erstellen ein Meldungsfeld, um die Nachricht zusammen mit anzuzeigen ein **OK** Schaltfläche. Wenn der Benutzer auf **OK**klickt, wird das Programm sofort beendet.

Wenn die Anwendung mit einer Debugversion der Laufzeitbibliotheken verknüpft ist **assert** erstellt ein Meldungsfeld mit drei Schaltflächen: **Abort**, **wiederholen**, und **Ignorieren**. Wenn der Benutzer auf **Abbrechen**klickt, wird das Programm sofort beendet. Wenn der Benutzer auf **Wiederholen**klickt, wird der Debugger aufgerufen und der Benutzer kann das Programm debuggen, wenn Just-In-Time (JIT)-Debuggen aktiviert ist. Wenn der Benutzer klickt **ignorieren**, **assert** die normale Ausführung fort: erstellt das Meldungsfeld mit der **OK** Schaltfläche. Wenn ein Fehlerzustand vorliegt, kann das Klicken auf **Ignorieren** zu undefiniertem Verhalten führen.

Weitere Informationen zum CRT-Debugging (C Runtime Library) finden Sie unter [CRT-Debugverfahren](/visualstudio/debugger/crt-debugging-techniques).

Die **_assert** und **_wassert** Funktionen sind interne CRT-Funktionen. Sie helfen dabei, den für die Unterstützung von Assertion in Ihren Objektdateien erforderlichen Code zu minimieren. Wir empfehlen nicht, diese Funktionen direkt aufzurufen.

Die **assert** Makros in den Versionen Release- und Debugversionen der C-Laufzeitbibliotheken beim **NDEBUG** ist nicht definiert. Wenn **NDEBUG** wird definiert, das Makro ist verfügbar, aber wertet das Argument nicht angehalten und wirkt sich nicht. Wenn diese Option aktiviert ist, die **assert** Makro Aufrufe **_wassert** zu seiner Implementierung. Andere Assertionsmakros, [_ASSERT](assert-asserte-assert-expr-macros.md), [_ASSERTE](assert-asserte-assert-expr-macros.md) und [_ASSERT_EXPR](assert-asserte-assert-expr-macros.md), sind ebenfalls verfügbar, sie werten die ihnen übergebenen Ausdrücke jedoch nur aus, wenn das [_DEBUG](../../c-runtime-library/debug.md)-Makro definiert wurde und sie sich in Code befinden, der mit der Debugversion der C-Laufzeitbibliotheken gelinkt wurde.

## <a name="requirements"></a>Anforderungen

|Routine|Erforderlicher Header|
|-------------|---------------------|
|**Assert-**, **_wassert**|\<assert.h>|

Die Signatur der **_assert** Funktion ist nicht in einer Headerdatei verfügbar. Die Signatur der **_wassert** Funktion ist nur verfügbar, wenn die **NDEBUG** Makro ist nicht definiert.

## <a name="example"></a>Beispiel

In diesem Programm die **Analyze_string** Funktion verwendet die **assert** Makro so testen Sie verschiedene Bedingungen im Zusammenhang mit der Zeichenfolge und Länge. Wenn bei einer der Bedingungen ein Fehler auftritt, gibt das Programm eine Meldung aus, die auf die Ursache des Fehlers hinweist.

```C
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
Analyzing string 'abc'
Analyzing string '(null)'
Assertion failed: string != NULL, file crt_assert.c, line 25
```

Je nach Version von Betriebssystem und Laufzeitbibliothek, wird möglicherweise nach dem Assertionsfehler ein Meldungsfeld angezeigt, das etwas in dieser Art enthält:

```Output
A problem caused the program to stop working correctly. Windows will close the program and notify you if a solution is available.
```

Wenn ein Debugger installiert ist, wählen Sie die Schaltfläche **Debug** aus, um den Debugger zu starten, oder **Programm schließen** zum Beenden.

## <a name="see-also"></a>Siehe auch

[Fehlerbehandlung](../../c-runtime-library/error-handling-crt.md)<br/>
[Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_ASSERT, _ASSERTE, _ASSERT_EXPR Macros](assert-asserte-assert-expr-macros.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
