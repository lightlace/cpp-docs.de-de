---
title: "_spawn- und _wspawn-Funktionen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr80.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcrt.dll"
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_spawn"
  - "_tspawnlp"
  - "_tspawnlpe"
  - "_tspawnve"
  - "_tspawnvp"
  - "_tspawnvpe"
  - "_tspawnl"
  - "spawn"
  - "_tspawnv"
  - "_tspawnle"
  - "wspawn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tspawnve-Funktion"
  - "_spawn-Funktionen"
  - "_tspawnlpe-Funktion"
  - "tspawnvpe-Funktion"
  - "Prozesse, Erstellen"
  - "tspawnve-Funktion"
  - "_tspawnvp-Funktion"
  - "spawn-Funktion"
  - "tspawnl-Funktion"
  - "tspawnlp-Funktion"
  - "_tspawnvpe-Funktion"
  - "_tspawnl-Funktion"
  - "tspawnvp-Funktion"
  - "tspawnv-Funktion"
  - "Prozesse, Ausführen neuer"
  - "_tspawnv-Funktion"
  - "tspawnle-Funktion"
  - "Prozesserstellung"
  - "_tspawnlp-Funktion"
  - "tspawnlpe-Funktion"
  - "_tspawnle-Funktion"
ms.assetid: bb47c703-5216-4e09-8023-8cf25bbf2cf9
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _spawn- und _wspawn-Funktionen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Jede der `_spawn`\-Funktionen erstellt und führt einen neuen Prozess aus:  
  
|||  
|-|-|  
|[\_spawnl, \_wspawnl](../c-runtime-library/reference/spawnl-wspawnl.md)|[\_spawnv, \_wspawnv](../c-runtime-library/reference/spawnv-wspawnv.md)|  
|[\_spawnle, \_wspawnle](../c-runtime-library/reference/spawnle-wspawnle.md)|[\_spawnve, \_wspawnve](../c-runtime-library/reference/spawnve-wspawnve.md)|  
|[\_spawnlp, \_wspawnlp](../c-runtime-library/reference/spawnlp-wspawnlp.md)|[\_spawnvp, \_wspawnvp](../c-runtime-library/reference/spawnvp-wspawnvp.md)|  
|[\_spawnlpe, \_wspawnlpe](../c-runtime-library/reference/spawnlpe-wspawnlpe.md)|[\_spawnvpe, \_wspawnvpe](../c-runtime-library/reference/spawnvpe-wspawnvpe.md)|  
  
 Die Buchstaben am Ende des Funktionsnamens bestimmen die Variante.  
  
 `e`  
 `envp`, Array von Zeigern auf den Umgebungseinstellungen, wird zum neuen Prozess übergeben.  
  
 `l`  
 Befehlszeilenargumente werden einzeln an die `_spawn`\-Funktion übergeben.  Dieses Suffix wird normalerweise verwendet, wenn mehrere Parameter einem neuen Prozess im Voraus bekannt ist.  
  
 `p`  
 Die `PATH`\-Umgebungsvariable wird verwendet, um die auszuführende Datei zu suchen.  
  
 `v`  
 `argv`, Array von Zeigern auf die Befehlszeilenargumente, wird zum `_spawn`\-Funktion übergeben.  Dieses Suffix wird normalerweise verwendet, wenn mehrere Parameter zu einer neuen Prozess\- variabel ist.  
  
## Hinweise  
 `_spawn` funktioniert jedes erstellen und führen einen neuen Prozess.  Sie behandeln Mehrbyte\-Zeichenfolgen\-Argumente automatisch entsprechend und derzeit erkennen Mehrbytezeichensequenzen entsprechend der Mehrbyte\-Codepage.  Die `_wspawn`\-Funktionen sind Breitzeichenversionen der Funktionen `_spawn` ; sie nicht behandelt Mehrbyte\-Zeichenfolgen.  Andernfalls verhalten sich die `_wspawn`\-Funktionen identisch zu ihren Entsprechungen `_spawn`.  
  
### Zuordnung generischer Textroutinen  
  
|Tchar.h\-Routine|\_UNICODE und \_MBCS nicht definiert|\_MBCS definiert|\_UNICODE definiert|  
|----------------------|------------------------------------------|----------------------|-------------------------|  
|`_tspawnl`|`_spawnl`|`_spawnl`|`_wspawnl`|  
|`_tspawnle`|`_spawnle`|`_spawnle`|`_wspawnle`|  
|`_tspawnlp`|`_spawnlp`|`_spawnlp`|`_wspawnlp`|  
|`_tspawnlpe`|`_spawnlpe`|`_spawnlpe`|`_wspawnlpe`|  
|`_tspawnv`|`_spawnv`|`_spawnv`|`_wspawnv`|  
|`_tspawnve`|`_spawnve`|`_spawnve`|`_wspawnve`|  
|`_tspawnvp`|`_spawnvp`|`_spawnvp`|`_wspawnvp`|  
|`_tspawnvpe`|`_spawnvpe`|`_spawnvpe`|`_wspawnvpe`|  
  
 muss genügend Arbeitsspeicher zum Laden und Ausführen des Prozesses neuen verfügbar sein.  Das Argument `mode` bestimmt die Aktionen, die von der aufrufende Prozess vor und während `_spawn` ausgeführt werden.  Die folgenden Werte für `mode` werden in Process.h definiert:  
  
 `_P_OVERLAY`  
 Überlagert einen aufrufenden Prozesses mit einem neuen Prozess und zerstört der aufrufende Prozess \(denselben Effekt der `_exec` aufgerufen\).  
  
 `_P_WAIT`  
 Hält einen aufrufenden Thread, bis die Ausführung des neuen Vorgangs abgeschlossen wurde \(synchrones `_spawn`\).  
  
 `_P_NOWAIT` oder `_P_NOWAITO`  
 Fährt fort, um einen aufrufende Prozess gleichzeitig mit den neuen Prozess \(Asynchronous `_spawn`\) auszuführen.  
  
 `_P_DETACH`  
 Fährt fort, und der aufrufende Prozess auszuführen; der neue Prozess wird im Hintergrund ohne Zugriff auf die Konsole oder die Tastatur ausgeführt.  Aufrufe von `_cwait` für den neuen Prozess schlagen fehl \(Asynchronous `_spawn`\).  
  
 Das Argument `cmdname` gibt der Datei an, die während der neue Prozess ausgeführt und einem vollständigen Pfad \(ausgehend\), einem partiellen Pfad \(im aktuellen Arbeitsverzeichnis\) oder nur einem Dateinamen angeben kann.  Wenn `cmdname` keine Dateinamenerweiterung hat nicht mit einem Punkt \(.\) beendet, versucht die `_spawn`\-Funktion zuerst die Dateinamenerweiterung .com\- und dann die .exe\-Dateinamenerweiterung, die .bat\-Dateinamenerweiterung und schließlich die .cmd\-Dateinamenerweiterung.  
  
 Wenn `cmdname` eine Dateinamenerweiterung verfügt, nur diese Erweiterung verwendet wird.  Wenn `cmdname` mit einem Punkt beendet, sucht die `_spawn` für `cmdname` ohne Dateinamenerweiterung.  `_spawnlp`, `_spawnlpe`, `_spawnvp` und  `_spawnvpe`\-Funktionssuche für `cmdname` \(mithilfe der Schritte\) in Verzeichnissen durch die Umgebungsvariable `PATH`.  
  
 Wenn `cmdname` verwendet einen oder einen Schrägstrich enthält, \(das heißt, wenn ein relativer Pfad ist\), durchsucht der `_spawn` Aufruf nur für die angegebene Datei; kein Pfadsuchen ist ausgeführt.  
  
 In der Vergangenheit haben einige dieser Funktionen `errno` auf Null bei Erfolg; das aktuelle Verhalten ist, `errno` unverändert bei Erfolg wird, wie vom C\-Standard angegeben.  Wenn Sie das alte Verhalten emulieren müssen, erstellen Sie `errno` auf Null unmittelbar vor dem Aufrufen dieser Funktionen.  
  
> [!NOTE]
>  Damit eine korrekte Overlayinitialisierung und Threadende zu gewährleisten, verwenden Sie nicht die `setjmp` oder Funktion um `longjmp` einzugeben oder zu übergehen Routine zu überlagern.  
  
## Argumente für den generierten Prozess  
 Um Argumente den neuen Prozess zu übergeben, geben Sie eine oder mehrere Zeiger auf Zeichenfolgen wie Argumente `_spawn` im Aufruf.  Diese Zeichenfolgen besteht die Argumentliste für den generierten Prozess.  Die kombinierte Länge der Zeichenfolgen, die die Argumentliste für den neuen Prozess besteht, darf 1024 Bytes nicht überschreiten.  Das NULL\-Zeichen \("\\ 0 "\) für jede Zeichenfolge wird nicht in Anzahl enthalten, die Leerzeichen \(automatisch eingefügt, um Argumente zu trennen\) werden aufgenommen.  
  
> [!NOTE]
>  Die in den Zeichenfolgen eingebetteten Leerzeichen können zu einem unerwarteten Verhalten führen. Zum Beispiel führt die Zeichenfolge `"hi there"` durch die Übergabe von `_spawn` dazu, dass der neue Prozess zwei Argumente erhält: `"hi"` und `"there"`.  Wenn der neue Prozess die benannte Datei "hi there" öffnen sollte, schlägt der Prozess fehl.  Sie können dies verhindern, indem Sie die Zeichenfolge in Anführungszeichen setzen: `"\"hi there\""`.  
  
> [!IMPORTANT]
>  Übergeben Sie Benutzereingaben nicht an `_spawn`, ohne den Inhalt explizit zu überprüfen.  `_spawn` führt zu einem Aufruf von [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425). Beachten Sie daher, dass nicht qualifizierte Pfadnamen zu potenziellen Sicherheitslücken führen können.  
  
 Sie können Argumentzeiger als separate Argumente übergeben \(in `_spawnl`, `_spawnle`, `_spawnlp` und `_spawnlpe`\) oder als Array Zeiger \(in `_spawnv`, `_spawnve`, `_spawnvp` und `_spawnvpe`\).  Sie müssen ein Argument, `arg0` oder `argv`\[0\], z erstelltem Prozess mindestens übergeben.  Üblicherweise ist dieses Argument der Name des Programms, wie Sie es in der Befehlszeile eingeben.  Ein weiterer Wert erzeugt keinen Fehler.  
  
 `_spawnl`, `_spawnle`, `_spawnlp` und `_spawnlpe` aufgerufen werden normalerweise verwendet, wenn die Anzahl von Argumenten im Voraus bekannt ist.  Das `arg0`\-Argument ist normalerweise ein Zeiger auf `cmdname`.  Die Argumente `arg1` bis `argn` sind Zeiger auf Zeichenfolgen, die die Argumentliste neu bilden.  Nach `argn` muss ein `NULL`\-Zeiger stehen, mit dem das Ende der Argumentliste markiert wird.  
  
 `_spawnv`, `_spawnve`, `_spawnvp` und `_spawnvpe` aufgerufen sind nützlich, wenn eine variable Anzahl von Argumenten zum neuen Prozess gibt.  Zeiger für Argumente werden als Array, `argv` übergeben *.* Das `argv`\[0\]\-Argument ist gewöhnlich ein Zeiger auf einen Pfad im Echtzeitmodus oder auf den Programmnamen im geschützten Modus und `argv`\[1\] bis `argv`\[`n`\] sind Zeiger auf die Zeichenfolgen, die die neue Argumentliste bilden.  Das Argument `argv`\[`n` \+1\] muss ein `NULL`\-Zeiger sein, um das Ende der Argumentliste zu markieren.  
  
## Umgebung generierten des Prozesses  
 Dateien, die geöffnet werden, wenn ein `_spawn` Aufruf ausgeführt wird, verbleiben im neuen Prozess geöffnet.  In `_spawnl`, `_spawnlp`, `_spawnv` und `_spawnvp` Aufrufen erbt der neue Prozess die Umgebung des aufrufenden Prozesses.  Sie können `_spawnle`, `_spawnlpe`, `_spawnve` und `_spawnvpe` aufgerufen verwenden, um die Umgebung für den neuen Prozess zu ändern, indem Sie eine Liste der Umgebungseinstellungen vom Argument `envp` übergeben.  Das Argument `envp` ist ein Array Zeichenzeiger, jedes Element \(außer das letzte Element\) aus dem auf eine auf NULL endende Zeichenfolge verweist, die eine Umgebungsvariable definiert.  Solch eine Zeichenfolge hat normalerweise die Form `NAME`\=`value`, wobei `NAME` der Name einer Umgebungsvariable und `value` der Zeichenfolgenwert ist, für den diese Variable festgelegt wird. \(Beachten Sie, dass `value` nicht in doppelte Anführungszeichen gesetzt wird.\) Das letzte Element des `envp`\-Arrays sollte `NULL` sein.  Wenn `envp` selbst `NULL` befindet, erbt der generierte Prozess die Umgebungseinstellungen des übergeordneten Prozesses.  
  
 Die Funktionen `_spawn` können alle Informationen zu geöffnete Dateien, einschließlich den Übersetzungsmodus, um neuen Prozess übergeben.  Diese Informationen werden in Realmodus durch den `C_FILE_INFO` \- Eintrag in der Umgebung an.  Der Startcode verarbeitet normalerweise diesen Eintrag und löscht ihn von der Umgebung.  Wenn eine Funktion einen `_spawn` nicht\-\-C Prozess erzeugt, bleibt dieser Eintrag in der Umgebung.  Die Umgebung installiertes, zeigt Schriftzeichen in der Definitionszeichenfolge für diesen Eintrag gezeigt, da die Umgebungsinformationen in binäre Form im Realmodus übergeben wird.  Sie sollte keine anderen Auswirkungen auf Standardvorgänge haben.  im geschützten Modus wird die Umgebungsinformationen in Textform übergeben und somit keine Schriftzeichen enthält.  
  
 Sie müssen jeden Stream leeren explizit \(mit `fflush` oder `_flushall`\) oder schließen, bevor Sie eine `_spawn`\-Funktion aufrufen.  
  
 Die neuen Prozesse, die durch Aufrufe `_spawn` Routinen erstellt werden, behalten keine Signaleinstellungen bei.  Stattdessen die generierten Prozessrücksetzungssignaleinstellungen zum Standard.  
  
## Umleiten ausgegeben  
 Wenn Sie `_spawn` in einer DLL oder einer GUI\-Anwendung aufrufen und die Ausgabe an eine Pipe umleiten möchten, haben Sie zwei Möglichkeiten:  
  
-   Verwenden Sie die Win32\-API, um eine Pipe, dann legen Aufruf [AllocConsole](http://msdn.microsoft.com/library/windows/desktop/ms681944), die Handlewerte in der Startstruktur und im Aufruf [CreateProcess](http://msdn.microsoft.com/library/windows/desktop/ms682425) fest.  
  
-   Rufen Sie [\_popen, \_wpopen](../c-runtime-library/reference/popen-wpopen.md), die eine Pipe auf und rufen Sie die App mit **cmd.exe \/c** \(oder **command.exe \/c**\).  
  
## Beispiel  
  
```  
// crt_spawn.c  
// This program accepts a number in the range  
// 1-8 from the command line. Based on the number it receives,  
// it executes one of the eight different procedures that  
// spawn the process named child. For some of these procedures,  
// the CHILD.EXE file must be in the same directory; for  
// others, it only has to be in the same path.  
//  
  
#include <stdio.h>  
#include <process.h>  
  
char *my_env[] =  
{  
   "THIS=environment will be",  
   "PASSED=to child.exe by the",  
   "_SPAWNLE=and",  
   "_SPAWNLPE=and",  
   "_SPAWNVE=and",  
   "_SPAWNVPE=functions",  
   NULL  
};  
  
int main( int argc, char *argv[] )  
{  
   char *args[4];  
  
   // Set up parameters to be sent:   
   args[0] = "child";  
   args[1] = "spawn??";  
   args[2] = "two";  
   args[3] = NULL;  
  
   if (argc <= 2)  
   {  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
  
   switch (argv[1][0])   // Based on first letter of argument   
   {  
   case '1':  
      _spawnl( _P_WAIT, argv[2], argv[2], "_spawnl", "two", NULL );  
      break;  
   case '2':  
      _spawnle( _P_WAIT, argv[2], argv[2], "_spawnle", "two",   
               NULL, my_env );  
      break;  
   case '3':  
      _spawnlp( _P_WAIT, argv[2], argv[2], "_spawnlp", "two", NULL );  
      break;  
   case '4':  
      _spawnlpe( _P_WAIT, argv[2], argv[2], "_spawnlpe", "two",   
                NULL, my_env );  
      break;  
   case '5':  
      _spawnv( _P_OVERLAY, argv[2], args );  
      break;  
   case '6':  
      _spawnve( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   case '7':  
      _spawnvp( _P_OVERLAY, argv[2], args );  
      break;  
   case '8':  
      _spawnvpe( _P_OVERLAY, argv[2], args, my_env );  
      break;  
   default:  
      printf( "SYNTAX: SPAWN <1-8> <childprogram>\n" );  
      exit( 1 );  
   }  
   printf( "from SPAWN!\n" );  
}  
```  
  
  **Ausgabe des untergeordneten Prozesses**  
**von den FISCHEIERN\!**   
## Siehe auch  
 [Prozess\- und Umgebungssteuerung](../c-runtime-library/process-and-environment-control.md)   
 [abort](../c-runtime-library/reference/abort.md)   
 [atexit](../c-runtime-library/reference/atexit.md)   
 [\_exec\- und \_wexec\-Funktionen](../c-runtime-library/exec-wexec-functions.md)   
 [exit, \_Exit, \_exit](../c-runtime-library/reference/exit-exit-exit.md)   
 [\_flushall](../c-runtime-library/reference/flushall.md)   
 [\_getmbcp](../c-runtime-library/reference/getmbcp.md)   
 [\_onexit, \_onexit\_m](../c-runtime-library/reference/onexit-onexit-m.md)   
 [\_setmbcp](../c-runtime-library/reference/setmbcp.md)   
 [system, \_wsystem](../c-runtime-library/reference/system-wsystem.md)