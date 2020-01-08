---
title: C++Programm Beendigung
ms.date: 12/10/2019
helpviewer_keywords:
- terminating execution
- quitting applications
- exiting applications
- programs [C++], terminating
ms.assetid: fa0ba9de-b5f1-4e7b-aa65-e7932068b48c
ms.openlocfilehash: a0e86cacd951327d39296a183be5ee4fbc36fd15
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301339"
---
# <a name="c-program-termination"></a>C++Programm Beendigung

In C++können Sie ein Programm auf folgende Weise beenden:

- Ruft die [Exit](exit-function.md) -Funktion auf.
- Ruft die [Abbruch](abort-function.md) -Funktion auf.
- Führen Sie eine [Return](return-statement-cpp.md) -Anweisung aus `main`aus.

## <a name="exit-function"></a>exit-Funktion

Die [Exit](../c-runtime-library/reference/exit-exit-exit.md) -Funktion, die in \<STDLIB. h-> deklariert C++ wird, beendet ein Programm. Der Wert, der als Argument für `exit` bereitgestellt wird, wird als Rückgabecode oder Exitcode des Programms an das Betriebssystem zurückgegeben. Gemäß der Konvention bedeutet ein Rückgabecode von Null, dass das Programm erfolgreich abgeschlossen wurde. Sie können die Konstanten EXIT_FAILURE und EXIT_SUCCESS verwenden, die auch in \<STDLIB. h-> definiert sind, um den Erfolg oder Misserfolg des Programms anzugeben.

Das Ausgeben einer **Return** -Anweisung aus der `main`-Funktion entspricht dem Aufrufen der `exit`-Funktion mit dem Rückgabewert als Argument.

## <a name="abort-function"></a>abort-Funktion

Die [Abbruch](../c-runtime-library/reference/abort.md) -Funktion, die auch in der standardmäßigen Includedatei \<STDLIB. h > C++ deklariert wird, beendet ein Programm. Der Unterschied zwischen `exit` und `abort` besteht darin, dass C++ `exit` die Lauf Zeit Beendigungs Verarbeitung durchführen kann (globale objektdeperktoren werden aufgerufen), während `abort` das Programm sofort beendet. Die `abort`-Funktion umgeht den normalen Zerstörungsprozess für initialisierte globale statische Objekte. Außerdem werden alle speziellen Verarbeitungsschritte umgangen, die mithilfe der [atexit](../c-runtime-library/reference/atexit.md) -Funktion angegeben wurden.

## <a name="atexit-function"></a>atexit-Funktion

Verwenden Sie die [atexit](../c-runtime-library/reference/atexit.md) -Funktion, um Aktionen anzugeben, die vor der Programm Beendigung ausgeführt werden. Vor der Ausführung der Funktion für die Beendigungs Verarbeitung werden keine globalen statischen Objekte, die vor dem **atexit** -aufrufungstyp initialisiert wurden, zerstört.

## <a name="return-statement-in-main"></a>Return-Anweisung in Main

Das Ausgeben einer [Return](return-statement-cpp.md) -Anweisung von `main` ist funktional äquivalent zum Aufrufen der `exit`-Funktion. Betrachten Sie das folgende Beispiel:

```cpp
// return_statement.cpp
#include <stdlib.h>
int main()
{
    exit( 3 );
    return 3;
}
```

Die `exit`-und **Return** -Anweisungen im vorherigen Beispiel sind funktionell identisch. C++ Erfordert jedoch, dass Funktionen, die andere Rückgabe Typen als **void** aufweisen, einen Wert zurückgeben. Mit der **Return** -Anweisung können Sie einen Wert aus `main`zurückgeben.

## <a name="destruction-of-static-objects"></a>Zerstörung statischer Objekte

Wenn Sie `exit` aufgerufen oder eine **Return** -Anweisung von `main`ausführen, werden statische Objekte in umgekehrter Reihenfolge ihrer Initialisierung zerstört (nach dem-`atexit`, sofern vorhanden). Das folgende Beispiel zeigt, wie so eine Initialisierung und Bereinigung funktionieren.

### <a name="example"></a>Beispiel

Im folgenden Beispiel werden die statischen Objekte `sd1` und `sd2` vor dem Eintrag zum `main`erstellt und initialisiert. Nachdem das Programm mithilfe der **Return** -Anweisung beendet wurde, wird zuerst `sd2` zerstört und dann `sd1`. Der Destruktor für die Klasse `ShowData` schließt die Dateien, die diesen statischen Objekten zugeordnet sind.

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

[main: Programmstart](main-program-startup.md)