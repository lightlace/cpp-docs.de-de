---
title: _beginthread, _beginthreadex
ms.date: 02/27/2018
apiname:
- _beginthread
- _beginthreadex
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
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: d70d2fb0ecb647d4854a6277d6c69cd9886e072f
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2019
ms.locfileid: "54894210"
---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex

Erstellt einen Thread.

## <a name="syntax"></a>Syntax

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>Parameter

*start_address*<br/>
Startadresse einer Routine, die die Ausführung eines neuen Threads beginnt. Für **_beginthread**, ist die Aufrufkonvention [__cdecl](../../cpp/cdecl.md) (bei nativem Code) oder [__clrcall](../../cpp/clrcall.md) (bei verwaltetem Code); **_beginthreadex**, er ist entweder [__stdcall](../../cpp/stdcall.md) (bei nativem Code) oder [__clrcall](../../cpp/clrcall.md) (bei verwaltetem Code).

*stack_size*<br/>
Stapelgröße für einen neuen Thread oder 0.

*arglist*<br/>
Argumentliste, die an einem neuen Thread übergeben werden oder **NULL**.

*Sicherheit*<br/>
Zeiger auf eine [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) -Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn *Sicherheit* ist **NULL**, das Handle nicht geerbt werden. Muss **NULL** für Windows 95-Anwendungen.

*initflag*<br/>
Flags, die den anfänglichen Zustand eines neuen Threads steuern. Legen Sie *Initflag* um 0 sofort ausgeführt oder **CREATE_SUSPENDED** um den Thread in einem angehaltenen Zustand zu erstellen verwenden [ResumeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-resumethread) um den Thread auszuführen. Legen Sie *Initflag* zu **STACK_SIZE_PARAM_IS_A_RESERVATION** Flag mit *Stack_size* wie der ursprüngliche Größe des Stapels in Byte zu reservieren, ist dieses Flag nicht angegeben ist, *Stack_size* gibt an, die Commitgröße.

*thrdaddr*<br/>
Zeigt auf eine 32-Bit-Variable, die den Threadbezeichner empfängt. Ist dies **NULL**, er wird nicht verwendet.

## <a name="return-value"></a>Rückgabewert

Bei Erfolg gibt jede dieser Funktionen ein Handle für den neu erstellten Thread; jedoch, wenn der neu erstellte Thread zu schnell beendet **_beginthread** möglicherweise kein gültiges Handle zurück. (Weitere Informationen finden Sie bei der Diskussion im Abschnitt Hinweise.) Bei einem Fehler **_beginthread** gibt – 1 L zurück, und **Errno** nastaven NA hodnotu **EAGAIN** treten zu viele Threads zu **EINVAL** Wenn das Argument ist ungültig, oder die Größe des Stapels ist falsch, oder **EACCES** Wenn nicht genügend Ressourcen (z. B. Arbeitsspeicher) vorhanden sind. Bei einem Fehler **_beginthreadex** gibt 0 zurück, und **Errno** und **_doserrno** festgelegt sind.

Wenn *Start_address* ist **NULL**, Handler für ungültige Parameter aufgerufen, siehe [Parametervalidierung](../../c-runtime-library/parameter-validation.md). Wenn die weitere Ausführung zugelassen wird, um den Vorgang fortzusetzen, legen diese Funktionen **Errno** zu **EINVAL** und geben-1 zurück.

Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, _doserrno, _sys_errlist und _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Weitere Informationen zu **Uintptr_t**, finden Sie unter [Standardtypen](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Hinweise

Die **_beginthread** Funktion erstellt einen Thread, der Beginn der Ausführung einer Routine bei *Start_address*. Die Routine bei *Start_address* verwenden, muss die **__cdecl** (bei nativem Code) oder **__clrcall** (bei verwaltetem Code) Aufrufkonvention und sollte keinen Wert zurückgibt. Wenn der Thread aus dieser Routine zurückgegeben wird, wird er automatisch beendet. Weitere Informationen zu Threads finden Sie unter [Multithreadingunterstützung für älteren Code (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** ähnelt der Win32 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) Weitere API stärker als **_beginthread** ist. **_beginthreadex** unterscheidet sich von **_beginthread** auf folgende Weise:

- **_beginthreadex** hat drei zusätzliche Parameter: *Initflag*, *Sicherheit*, und **Threadaddr**. Der neue Thread kann in einem unterbrochenen Zustand mit einer angegebenen Sicherheit erstellt werden und kann zugegriffen werden, indem *Thrdaddr*, d.h. den Threadbezeichner.

- Die Routine bei *Start_address* übergebene **_beginthreadex** verwenden, muss die **__stdcall** (bei nativem Code) oder **__clrcall** (für verwalteter Code) Aufrufkonvention, und einen threadbeendigungscode zurückgeben müssen.

- **_beginthreadex** gibt 0 für Fehler, und nicht als-1 L zurück.

- Ein Thread, der erstellt wird **_beginthreadex** wird durch einen Aufruf beendet [_endthreadex](endthread-endthreadex.md).

Die **_beginthreadex** Funktion können Sie besser steuern zu können, wie der Thread, als erstellt wird **_beginthread** ist. Die **_endthreadex** Funktion ist außerdem flexibler. Z. B. mit **_beginthreadex**, können Sie Sicherheitsinformationen verwenden, legen Sie den Ausgangszustand des Threads (ausgeführt oder angehalten) und den Threadbezeichner des neu erstellten Threads abrufen. Sie können auch das Threadhandle, die von zurückgegeben wird **_beginthreadex** mit der Synchronisierungs-APIs, die mit nicht möglich **_beginthread**.

Es ist sicherer, verwenden Sie **_beginthreadex** als **_beginthread**. Wenn der Thread, die vom generierten **_beginthread** schnell beendet, das Handle, das an den Aufrufer zurückgegeben wird **_beginthread** möglicherweise ungültig, oder zeigen Sie auf einem anderen Thread. Allerdings das Handle, das von zurückgegebene **_beginthreadex** muss geschlossen werden, durch den Aufrufer der **_beginthreadex**, sodass sie ein gültiges Handle ist unbedingt, wenn **_beginthreadex** hat keine Fehler zurückgegeben.

Rufen Sie [_endthread](endthread-endthreadex.md) oder **_endthreadex** explizit auf einen Thread zu beenden. allerdings **_endthread** oder **_endthreadex** aufgerufen wird automatisch bei der Thread von der Routine zurück, der als Parameter übergeben wird. Beenden eines Threads durch einen Aufruf von **_endthread** oder **_endthreadex** sichergestellt korrekte Wiederherstellung der Ressourcen, die für den Thread zugewiesen werden.

**_endthread** schließt das Threadhandle automatisch, während **_endthreadex** nicht. Aus diesem Grund bei Verwendung von **_beginthread** und **_endthread**, explizit schließen Sie nicht das Threadhandle durch Aufrufen der Win32- ["CloseHandle"](/windows/desktop/api/handleapi/nf-handleapi-closehandle) API. Dieses Verhalten unterscheidet sich von dem der [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) -Win32-API.

> [!NOTE]
> Für eine mit "LIBCMT.lib" verknüpfte ausführbare Datei, rufen Sie nicht die Win32 **ExitThread** API, damit Sie das Laufzeitsystem Freigabe zu verhindern, dass keine zugeordneten Ressourcen. **_endthread** und **_endthreadex** zugeordnete Threadressourcen, und rufen dann **ExitThread**.

Vom Betriebssystem behandelt die speicherbelegung des Stapels bei beiden **_beginthread** oder **_beginthreadex** aufgerufen wird; Sie müssen die Adresse des Threadstapels an jede dieser Funktionen zu übergeben. Darüber hinaus die *Stack_size* Argument kann 0 (null) und in dem verwendet Fall das Betriebssystem den gleichen Wert wie vom Stapel, der angegeben wird, für den Hauptthread sein.

*Arglist* ist ein Parameter, um den neu erstellten Thread übergeben werden. In der Regel ist das die Adresse eines Datenelements, z. B. einer Zeichenfolge. *Arglist* kann **NULL** , wenn es nicht erforderlich ist, aber **_beginthread** und **_beginthreadex** müssen einige Werte erhalten werden, an den neuen Thread übergeben. Alle Threads werden beendet, wenn alle Aufrufe thread [Abbrechen](abort.md), **beenden**, **_exit**, oder **ExitProcess**.

Das Gebietsschema des neuen Threads wird mit die gebietsschemaangabe aktuellen globalen pro Prozess initialisiert. Wenn das threadspezifische Gebietsschema aktiviert ist, durch einen Aufruf von [_configthreadlocale](configthreadlocale.md) (entweder global oder für neue Threads nur), kann der Thread ändern sein Gebietsschema unabhängig von anderen Threads durch Aufrufen von **Setlocale** oder **_wsetlocale**. Threads, die die threadspezifische Gebietsschema Kennzeichen festgelegt haben, können die Gebietsschemainformationen in alle anderen Threads, die auch die threadspezifische Gebietsschema Kennzeichen festgelegt haben, sowie alle neu erstellten Threads auswirken. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).

Für **"/ CLR"** Code **_beginthread** und **_beginthreadex** haben jeweils zwei Überladungen. Eine akzeptiert einen systemeigenen Funktionszeiger für die Aufrufkonvention, und der andere eine **__clrcall** Funktionszeiger. Die erste Überladung ist nicht anwendungsdomänensicher und wird es niemals sein. Wenn Sie schreiben **"/ CLR"** Code Sie sicherstellen müssen, dass der neue Thread die richtige Anwendungsdomäne angibt, bevor sie greift auf verwaltete Ressourcen. Hierzu können Sie beispielsweise die [call_in_domain-Funktion](../../dotnet/call-in-appdomain-function.md) verwenden. Die zweite Überladung ist anwendungsdomänensicher; der neu erstellte Thread wird beendet immer in der Anwendungsdomäne des Aufrufers des **_beginthread** oder **_beginthreadex**.

## <a name="requirements"></a>Anforderungen

|-Routine zurückgegebener Wert|Erforderlicher Header|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Bibliotheken

Nur Multithread-Versionen von [C-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md) .

Verwendung von **_beginthread** oder **_beginthreadex**, muss die Anwendung mit einem der Multithread C-Laufzeitbibliotheken gelinkt.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird **_beginthread** und **_endthread**.

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

Drücken Sie zum Beenden der Beispielanwendung eine beliebige Taste.

## <a name="example"></a>Beispiel

Im folgenden Beispielcode wird veranschaulicht, wie Sie das Threadhandle verwenden können, die von zurückgegeben wird **_beginthreadex** mit der Synchronisierungs-API [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject). Der Hauptthread wartet auf das Beenden des zweiten Threads, bevor er fortsetzt. Wenn der zweite Thread aufruft **_endthreadex**, wird das Threadobjekt in den signalisierten Zustand versetzt. Damit kann der primäre Thread fortgesetzt werden. Dies kann nicht mit **_beginthread** und **_endthread**, da **_endthread** Aufrufe **"CloseHandle"**, die den Thread zerstört -Objekt, bevor sie auf den signalisierten Zustand festgelegt werden kann.

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>Siehe auch

- [Prozess- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [abort](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
