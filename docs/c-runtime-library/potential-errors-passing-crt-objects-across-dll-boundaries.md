---
title: Potenzielle Fehler bei der Übergabe von CRT-Objekten über DLL-Grenzen
ms.date: 11/04/2016
helpviewer_keywords:
- DLL conflicts [C++]
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
ms.openlocfilehash: 31f9d9aceba167b516c9d37724e240f1bc4586e1
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749898"
---
# <a name="potential-errors-passing-crt-objects-across-dll-boundaries"></a>Potenzielle Fehler bei der Übergabe von CRT-Objekten über DLL-Grenzen

Beim Übergeben von CRT-Objekten (C Run Time, C-Laufzeit) wie z.B. Dateihandles, Gebietsschemas und Umgebungsvariablen in eine oder aus einer DLL (Funktionsaufrufe über die DLL-Grenze hinweg), kann ein unerwartetes Verhalten auftreten, wenn die DLL und die Dateien, die die DLL aufrufen, unterschiedliche Kopien der CRT-Bibliotheken verwenden.

Ein ähnliches Problem kann auftreten, wenn Sie Speicher belegen (entweder explizit mit `new` oder `malloc` oder implizit mit `strdup`, `strstreambuf::str` usw.) und dann einen Zeiger über eine DLL-Grenze hinweg übergeben, wo er freigegeben wird. Dies kann eine Speicherzugriffsverletzung oder Heapbeschädigung verursachen, wenn die DLL und ihre Benutzer unterschiedliche Kopien der CRT-Bibliotheken verwenden.

Ein anderes Symptom dieses Problems kann ein Fehler sein, der während des Debuggens im Ausgabefenster auftritt, wie z.B. der folgende:

HEAP[]: Invalid Address specified to RtlValidateHeap(#,#) (HEAP[]: Ungültige Adresse für RtlValidateHeap(#,#) angegeben)

## <a name="causes"></a>Ursachen

Jede Kopie der CRT-Bibliothek verfügt über einen eigenen Status, der von Ihrer App oder DLL im lokalen Threadspeicher gespeichert wird. Daher gelten CRT-Objekte wie Dateihandles, Umgebungsvariablen und Gebietsschemas nur für die Kopie der CRT in derjenigen App oder DLL, in der diese Objekte zugewiesen oder festgelegt sind. Wenn eine DLL und die zugehörigen App-Clients verschiedene Kopien der CRT-Bibliothek verwenden, können Sie diese CRT-Objekte nicht über die DLL-Grenze hinweg übergeben und damit rechnen, dass diese auf der anderen Seite ordnungsgemäß übernommen werden. Dies gilt insbesondere für CRT-Versionen vor der Universal CRT in Visual Studio 2015 und höher. Für jede mit Visual C++ 2013 oder früher erstellte Version von Visual Studio gab es eine versionsspezifische CRT-Bibliothek. Die internen Implementierungsdetails der CRT wie z.B. die Datenstrukturen und Benennungskonventionen unterschieden sich von Version zu Version. Die dynamische Verknüpfung von Code, der für eine Version der CRT kompiliert wurde, mit einer anderen Version der CRT-DLL wurde nie unterstützt. Die Verknüpfung funktionierte zwar zuweilen, das war aber eher Glück als Absicht.

Und da jede Kopie der CRT-Bibliothek einen eigenen Heap-Manager aufweist, ist das Belegen von Speicher in einer CRT-Bibliothek und das Übergeben des Zeigers über eine DLL-Grenze hinweg zur Freigabe durch eine andere Kopie der CRT-Bibliothek eine potenzielle Ursache für eine Beschädigung des Heaps. Wenn Sie Ihre DLL so konzipieren, dass sie CRT-Objekte über die Grenze hinweg übergibt oder Speicher belegt, der außerhalb der DLL freigegeben werden soll, müssen Sie die App-Clients der DLL so einrichten, dass sie dieselbe Kopie der CRT-Bibliothek verwenden wie die DLL. Die DLL und die DLL-Clients verwenden normalerweise nur dann die gleiche Kopie der CRT-Bibliothek, wenn beide zur Ladezeit mit der gleichen Version der CRT-DLL verknüpft sind. Da die von Visual Studio 2015 und später auch Windows 10 verwendete DLL-Version der Universal CRT-Bibliothek jetzt eine zentral bereitgestellte Windows-Komponente ist (ucrtbase.dll), kann sie für Apps verwendet werden, die mit Visual Studio 2015 und höher erstellt werden. Eine Einschränkung gilt aber auch hier: Auch wenn der CRT-Code identisch ist, können Sie Speicher, der in einem Heap belegt ist, nicht einer Komponente zuweisen, die einen anderen Heap verwendet.

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Dieses Beispiel übergibt ein Dateihandle über eine DLL-Grenze.

Die DLL und die EXE-Datei wurden mit /MD erstellt, sodass sie sich eine einzige Kopie der CRT teilen.

Wenn Sie die Dateien mit „/MT“ neu erstellen, sodass sie getrennte Kopien der CRT verwenden, zieht die Ausführung der resultierenden „test1Main.exe“ eine Zugriffsverletzung nach sich.

```cpp
// test1Dll.cpp
// compile with: cl /EHsc /W4 /MD /LD test1Dll.cpp
#include <stdio.h>
__declspec(dllexport) void writeFile(FILE *stream)
{
   char   s[] = "this is a string\n";
   fprintf( stream, "%s", s );
   fclose( stream );
}
```

```cpp
// test1Main.cpp
// compile with: cl /EHsc /W4 /MD test1Main.cpp test1Dll.lib
#include <stdio.h>
#include <process.h>
void writeFile(FILE *stream);

int main(void)
{
   FILE  * stream;
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );
   writeFile(stream);
   system( "type fprintf.out" );
}
```

```Output
this is a string
```

## <a name="example"></a>Beispiel

### <a name="description"></a>Beschreibung

Dieses Beispiel übergibt Umgebungsvariablen über eine DLL-Grenze hinweg.

```cpp
// test2Dll.cpp
// compile with: cl /EHsc /W4 /MT /LD test2Dll.cpp
#include <stdio.h>
#include <stdlib.h>

__declspec(dllexport) void readEnv()
{
   char *libvar;
   size_t libvarsize;

   /* Get the value of the MYLIB environment variable. */
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );

   if( libvar != NULL )
      printf( "New MYLIB variable is: %s\n", libvar);
   else
      printf( "MYLIB has not been set.\n");
   free( libvar );
}
```

```cpp
// test2Main.cpp
// compile with: cl /EHsc /W4 /MT test2Main.cpp test2dll.lib
#include <stdlib.h>
#include <stdio.h>

void readEnv();

int main( void )
{
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );
   readEnv();
}
```

```Output
MYLIB has not been set.
```

Wenn sowohl die DLL als auch die ausführbare Datei mit „/MD“ erstellt wurden, sodass nur eine einzige Kopie der CRT verwendet wird, wird das Programm erfolgreich ausgeführt und erzeugt folgende Ausgabe:

```
New MYLIB variable is: c:\mylib;c:\yourlib
```

## <a name="see-also"></a>Siehe auch

[CRT-Bibliotheksfunktionen](../c-runtime-library/crt-library-features.md)
