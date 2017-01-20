---
title: "_beginthread, _beginthreadex"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
apiname: 
  - "_beginthread"
  - "_beginthreadex"
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
  - "beginthread"
  - "_beginthread"
  - "beginthreadex"
  - "_beginthreadex"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_beginthread-Funktion"
  - "Threading [C++], Erstellen von threads"
  - "beginthreadex-Funktion"
  - "_beginthreadex-Funktion"
  - "beginthread-Funktion"
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
caps.latest.revision: 36
caps.handback.revision: "36"
ms.author: "corob"
manager: "ghogen"
---
# _beginthread, _beginthreadex
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Erstellt einen Thread.  
  
## Syntax  
  
```  
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
  
#### Parameter  
 `start_address`  
 Startadresse einer Routine, die die Ausführung eines neuen Threads beginnt. Für `_beginthread` ist die Aufrufkonvention entweder [\_\_cdecl](../../cpp/cdecl.md) \(bei systemeigenem Code\) oder [\_\_clrcall](../../cpp/clrcall.md) \(bei verwaltetem Code\), für `_beginthreadex` ist es entweder [\_\_stdcall](../../cpp/stdcall.md) \(bei systemeigenem Code\) oder [\_\_clrcall](../../cpp/clrcall.md) \(bei verwaltetem Code\).  
  
 `stack_size`  
 Stapelgröße für einen neuen Thread oder 0.  
  
 `arglist`  
 Argumentliste, die an einen neuen Thread übergeben wird, oder NULL.  
  
 `Security`  
 Zeiger auf eine [SECURITY\_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560)\-Struktur, die bestimmt, ob das zurückgegebene Handle von untergeordneten Prozessen geerbt werden kann. Wenn `Security` NULL ist, kann das Handle nicht geerbt werden. Muss für Windows 95\-Anwendungen NULL sein.  
  
 `initflag`  
 Flags, die den anfänglichen Zustand eines neuen Threads steuern. Legen Sie `initflag` für eine sofortige Ausführung auf `0` fest oder auf `CREATE_SUSPENDED`, um den Thread in einem angehaltenen Zustand zu erstellen. Verwenden Sie [ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx), um den Thread auszuführen. Legen Sie `initflag` auf das `STACK_SIZE_PARAM_IS_A_RESERVATION`\-Flag fest, um `stack_size` als anfängliche Reservierungsgröße des Stapels in Byte zu verwenden. Wenn dieses Flag nicht angegeben wird, gibt `stack_size` die Commitgröße an.  
  
 `thrdaddr`  
 Zeigt auf eine 32\-Bit\-Variable, die den Threadbezeichner empfängt. Wenn sie NULL ist, wird sie nicht verwendet.  
  
## Rückgabewert  
 Bei Erfolg gibt jede dieser Funktionen ein Handle für den neu erstellten Thread zurück. Wenn der neu erstellte Thread allerdings zu schnell beendet wird, gibt `_beginthread` möglicherweise kein gültiges Handle zurück. \(Weitere Informationen finden Sie bei der Diskussion im Abschnitt Hinweise.\) Bei einem Fehler gibt `_beginthread` "\-1L" zurück, und `errno` wird auf `EAGAIN` festgelegt, wenn zu viele Threads vorhanden sind, auf `EINVAL`, wenn das Argument ungültig oder die Stapelgröße falsch ist, oder auf `EACCES`, wenn nicht genügend Ressourcen \(wie Arbeitsspeicher\) vorhanden sind. Bei einem Fehler gibt `_beginthreadex` 0 zurück, und `errno` sowie `_doserrno` werden festgelegt.  
  
 Wenn `startaddress` NULL ist, wird der ungültige Parameterhandler wie in [Parametervalidierung](../../c-runtime-library/parameter-validation.md) beschrieben aufgerufen. Wenn die weitere Ausführung zugelassen wird, stellen diese Funktionen `errno` auf `EINVAL` ein und geben \-1 zurück.  
  
 Weitere Informationen zu diesen und anderen Rückgabecodes finden Sie unter [errno, \_doserrno, \_sys\_errlist und \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Weitere Informationen zu `uintptr_t` finden Sie unter [Standardtypen](../../c-runtime-library/standard-types.md).  
  
## Hinweise  
 Mit der `_beginthread`\-Funktion wird ein Thread erstellt, der die Ausführung einer Routine bei `start_address` beginnt. Die Routine bei `start_address` muss die `__cdecl`\-Aufrufkonvention \(für systemeigenen Code\) oder die `__clrcall`\-Aufrufkonvention \(für verwalteten Code\) verwenden und sollte keinen Rückgabewert besitzen. Wenn der Thread aus dieser Routine zurückgegeben wird, wird er automatisch beendet. Weitere Informationen zu Threads finden Sie unter [Multithreadingunterstützung für älteren Code \(Visual C\+\+\)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 `_beginthreadex` ähnelt [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx)\-Win32\-API stärker als `_beginthread`.`_beginthreadex` unterscheidet sich von `_beginthread` wie folgt:  
  
-   `_beginthreadex` hat drei zusätzliche Parameter: `initflag`, `security` und `threadaddr`. Der neue Thread kann in einem unterbrochenen Zustand mit einer angegebenen Sicherheit erstellt werden, und es kann darauf mithilfe des `thrdaddr`\-Threadbezeichners zugegriffen werden.  
  
-   Die Routine bei `start_address`, die an `_beginthreadex` übergeben wird, muss `__stdcall` \(für systemeigenen Code\) oder `__clrcall` \(für verwalteten Code\) verwenden und einen Threadbeendigungscode zurückgeben.  
  
-   `_beginthreadex` gibt bei Fehler "0" anstatt "\-1L" zurück.  
  
-   Ein Thread, der mithilfe von `_beginthreadex` erstellt wird, wird durch den Aufruf von [\_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md) beendet.  
  
 Mit der `_beginthreadex`\-Funktion können Sie die Erstellung des Threads besser steuern, als es mit `_beginthread` möglich ist. Die `_endthreadex`\-Funktion ist auch flexibler. Sie können z. B. mit `_beginthreadex`, Sicherheitsinformationen verwenden, den Ausgangszustand des Threads festlegen \(ausgeführt oder angehalten\) und den Threadbezeichner des neu erstellten Threads abrufen. Sie können auch das Threadhandle verwenden, das von `_beginthreadex` mit den Synchronisierung\-APIs zurückgegeben wird. Das ist mit `_beginthread` nicht möglich.  
  
 Es ist sicherer, `_beginthreadex` zu verwenden und nicht `_beginthread`. Wenn der Thread, der von `_beginthread` generiert wird, schnell beendet, könnte das Handle, das dem Aufrufer von `_beginthread` zurückgegeben wird, ungültig sein oder auf einem anderen Thread zeigen. Allerdings muss das Handle, das von `_beginthreadex` zurückgegeben wird, vom Aufrufer von `_beginthreadex` geschlossen werden, sodass sichergestellt ist, dass es ein gültiges Handle ist, wenn `_beginthreadex` keinen Fehler zurückgegeben hat.  
  
 Sie können [\_endthread](../../c-runtime-library/reference/endthread-endthreadex.md) oder `_endthreadex` explizit aufrufen, um einen Thread zu beenden. Allerdings wird `_endthread` oder `_endthreadex` automatisch aufgerufen, wenn der Thread aus der als Parameter übergebenen Routine zurückgegeben wird. Das Beenden eines Threads durch Aufruf von `_endthread` oder `_endthreadex` stellt die korrekte Wiederherstellung der dem Thread zugeordneten Ressourcen sicher.  
  
 `_endthread` schließt das Threadhandle automatisch, `_endthreadex` hingegen nicht. Wenn Sie also `_beginthread` und `_endthread` verwenden, schließen Sie das Threadhandle nicht explizit mit dem Aufruf der [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx)\-Win32\-API. Dieses Verhalten unterscheidet sich von dem der [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx)\-Win32\-API.  
  
> [!NOTE]
>  Rufen Sie für eine mit "Libcmt.lib" verknüpfte ausführbare Datei die `ExitThread`\-Win32\-API nicht auf, damit Sie das Laufzeitsystem nicht an der Freigabe von zugeordneten Ressourcen hindern.`_endthread` und `_endthreadex` geben zugeordnete Threadressourcen frei und rufen dann `ExitThread` auf.  
  
 Die Speicherbelegung des Stapels wird vom Betriebssystem behandelt, wenn entweder `_beginthread` oder `_beginthreadex` aufgerufen wird. Sie müssen die Adresse des Threadstapels an keine dieser Funktionen übergeben. Außerdem kann das `stack_size`\-Argument "0" sein. In diesem Fall wird vom Betriebssystem der gleiche Wert wie vom Stapel verwendet, der für den Hauptthread angegeben wird.  
  
 `arglist` ist ein Parameter, der an den neu erstellten Thread übergeben werden soll. In der Regel ist das die Adresse eines Datenelements, z. B. einer Zeichenfolge.`arglist` kann NULL sein, wenn die Funktion nicht benötigt wird, aber `_beginthread` und `_beginthreadex` müssen einige Werte erhalten, die von Ihnen an den neuen Thread übergeben werden. Alle Threads werden beendet, sobald ein Thread `abort`, `exit`, `_exit` oder `ExitProcess` aufruft.  
  
 Das Gebietsschema des neuen Threads wird von seinem übergeordneten Thread geerbt. Wenn ein threadspezifisches Gebietsschema mit einem Aufruf von [\_configthreadlocale](../../c-runtime-library/reference/configthreadlocale.md) \(entweder global oder nur für neue Threads\) aktiviert wird, kann der Thread sein Gebietsschema unabhängig von seinem übergeordneten Element ändern, indem `setlocale` oder `_wsetlocale` aufgerufen wird. Weitere Informationen finden Sie unter [Locale](../../c-runtime-library/locale.md).  
  
 Für gemischten und reinen Code verfügen `_beginthread` und `_beginthreadex` jeweils über zwei Überladungen. Die Eine akzeptiert einen systemeigenen Funktionszeiger für die Aufrufkonvention, die Andere akzeptiert einen `__clrcall`\-Funktionszeiger. Die erste Überladung ist nicht anwendungsdomänensicher und wird es niemals sein. Wenn Sie gemischten oder reinen Code schreiben, müssen Sie sicherstellen, dass der neue Thread die richtige Anwendungsdomäne angibt, bevor er auf verwaltete Ressourcen zugreift. Hierzu können Sie z. B. [call\_in\_appdomain\-Funktion](../../dotnet/call-in-appdomain-function.md) verwenden. Die zweite Überladung ist anwendungsdomänensicher. Der neu erstellte Thread beendet immer in der Anwendungsdomäne des Aufrufers von `_beginthread` oder `_beginthreadex`.  
  
## Anforderungen  
  
|Routine|Erforderlicher Header|  
|-------------|---------------------------|  
|`_beginthread`|\<process.h\>|  
|`_beginthreadex`|\<process.h\>|  
  
 Weitere Informationen zur Kompatibilität finden Sie unter [Kompatibilität](../../c-runtime-library/compatibility.md).  
  
## Bibliotheken  
 Nur Multithread\-Versionen von [C\-Laufzeitbibliotheken](../../c-runtime-library/crt-library-features.md).  
  
 Zum Verwenden von `_beginthread` oder `_beginthreadex` muss die Anwendung mit einer Multithreadanwendung der C\-Laufzeitbibliotheken verknüpft werden.  
  
## Beispiel  
 Im folgenden Beispiel werden `_beginthread` und `_endthread`verwendet.  
  
```  
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
  
// Bounce - Thread to create and and control a colored letter that moves  
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
  
## Beispiel  
 Im folgenden Beispielcode wird die Verwendung des Threadhandles, das von `_beginthreadex` mit der Synchronisierungs\-API [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) zurückgegeben wird, dargestellt. Der Hauptthread wartet auf das Beenden des zweiten Threads, bevor er fortsetzt. Wenn vom zweiten Thread `_endthreadex` aufgerufen wird, wird das Threadobjekt in den signalisierten Zustand versetzt. Damit kann der primäre Thread fortgesetzt werden. Das ist mit `_beginthread` und `_endthread` möglich, da `_endthread` von `CloseHandle` aufgerufen wird. Dadurch wird das Threadobjekt zerstört, bevor es auf den signalisierten Zustand festgelegt werden kann.  
  
```  
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
Erstellen des zweiten Threads... Im zweiten Thread... Indikator sollte 1000000 sein; er ist-> 1000000  
```  
  
## .NET Framework-Entsprechung  
 [System::Threading::Thread::Start](https://msdn.microsoft.com/en-us/library/system.threading.thread.start.aspx)  
  
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../../c-runtime-library/process-and-environment-control.md)   
 [\_endthread, \_endthreadex](../../c-runtime-library/reference/endthread-endthreadex.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)