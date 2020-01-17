---
title: C++Programm Beendigung
description: Beschreibt die Möglichkeiten, ein C++Sprachprogramm exit.
ms.date: 01/15/2020
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
no-loc:
- exit
- abort
- return
- main
- atexit
- void
ms.openlocfilehash: f83c9d5da5b0a1127603a97fd7946e9cca43a7a5
ms.sourcegitcommit: e93f3e6a110fe38bc642055bdf4785e620d4220f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2020
ms.locfileid: "76123954"
---
# <a name="c-program-termination"></a>C++Programm Beendigung

In C++können Sie ein Programm auf folgende Weise exit:

- Ruft die [exit](exit-function.md) -Funktion auf.
- Ruft die [abort](abort-function.md) -Funktion auf.
- Führen Sie eine [return](return-statement-cpp.md) Anweisung aus `main`aus.

## <a name="opno-locexit-function"></a>exit-Funktion

Die [exit](../c-runtime-library/reference/exit-exit-exit.md) Funktion, die in \<STDLIB. h-> deklariert ist C++ , beendet ein Programm. Der Wert, der als Argument für `exit` bereitgestellt wird, wird als return Code oder exit Code des Programms an das Betriebssystem zurückgegeben. Gemäß der Konvention bedeutet ein return Code 0, dass das Programm erfolgreich abgeschlossen wurde. Sie können die Konstanten EXIT_FAILURE und EXIT_SUCCESS verwenden, die auch in \<STDLIB. h-> definiert sind, um den Erfolg oder Misserfolg des Programms anzugeben.

Das Ausgeben einer **return** -Anweisung aus der `main`-Funktion entspricht dem Aufrufen der `exit`-Funktion mit dem return Wert als Argument.

## <a name="opno-locabort-function"></a>abort-Funktion

Die [abort](../c-runtime-library/reference/abort.md) Funktion, die auch in der standardmäßigen Includedatei \<STDLIB. h > deklariert C++ wird, beendet ein Programm. Der Unterschied zwischen `exit` und `abort` besteht darin, dass C++ `exit` die Lauf Zeit Beendigungs Verarbeitung durchführen kann (globale objektdeperktoren werden aufgerufen), während `abort` das Programm sofort beendet. Die `abort`-Funktion umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte. Außerdem werden alle speziellen Verarbeitungsschritte umgangen, die mithilfe der [atexit](../c-runtime-library/reference/atexit.md) -Funktion angegeben wurden.

## <a name="opno-locatexit-function"></a>atexit-Funktion

Verwenden Sie die [atexit](../c-runtime-library/reference/atexit.md) -Funktion, um Aktionen anzugeben, die vor der Programm Beendigung ausgeführt werden. Vor der Ausführung der exitVerarbeitungs Funktion werden keine globalen statischen Objekte initialisiert, die vor dem- **atexit** initialisiert wurden.

## <a name="opno-locreturn-statement-in-opno-locmain"></a>return-Anweisung in main

Das Ausgeben einer [return](return-statement-cpp.md) -Anweisung von `main` ist funktional äquivalent zum Aufrufen der `exit`-Funktion. Betrachten Sie das folgende Beispiel:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Die Anweisungen `exit` und **return** im vorherigen Beispiel sind funktionell identisch. C++ Erfordert jedoch, dass Funktionen, die andere return Typen als **void** haben, einen Wert return. Mit der **return** -Anweisung können Sie einen Wert aus `main`return.

## <a name="destruction-of-static-objects"></a>Zerstörung statischer Objekte

Wenn Sie `exit` aufgerufen oder eine **return** Anweisung aus `main`ausführen, werden statische Objekte in umgekehrter Reihenfolge ihrer Initialisierung zerstört (nachdem der-`atexit`, sofern vorhanden). Das folgende Beispiel zeigt, wie so eine Initialisierung und Bereinigung funktionieren.

### <a name="example"></a>Beispiel

Im folgenden Beispiel werden die statischen Objekte `sd1` und `sd2` vor dem Eintrag zum `main`erstellt und initialisiert. Nachdem das Programm mit der **return** -Anweisung beendet wurde, wird zuerst `sd2` zerstört und dann `sd1`. Der Destruktor für die Klasse `ShowData` schließt die Dateien, die diesen statischen Objekten zugeordnet sind.

```cpp
// using_exit_or_return1.cpp
#include <stdio.h>
class ShowData {
public:
   // Constructor opens a file.
   ShowData( const char *szDev ) {
   errno_t err;
      err = fopen_s(&OutputDev, szDev, "w" );
   }

   // Destructor closes the file.
   ~ShowData() { fclose( OutputDev ); }

   // Disp function shows a string on the output device.
   void Disp( char *szData ) {
      fputs( szData, OutputDev );
   }
private:
   FILE *OutputDev;
};

//  Define a static object of type ShowData. The output device
//   selected is "CON" -- the standard output device.
ShowData sd1 = "CON";

//  Define another static object of type ShowData. The output
//   is directed to a file called "HELLO.DAT"
ShowData sd2 = "hello.dat";

int main() {
   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

Eine andere Möglichkeit zum Schreiben des Codes besteht darin, die `ShowData`-Objekte mit dem Blockbereich zu deklarieren, sodass sie zerstört werden, wenn sie den Gültigkeitsbereich verlassen:

```cpp
int main() {
   ShowData sd1, sd2( "hello.dat" );

   sd1.Disp( "hello to default device\n" );
   sd2.Disp( "hello to file hello.dat\n" );
}
```

## <a name="see-also"></a>Siehe auch

[main Funktion und Befehlszeilenargumente](main-function-command-line-args.md)
