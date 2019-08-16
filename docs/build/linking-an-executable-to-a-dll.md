---
title: Eine ausführbare Datei mit einer DLL verknüpfen
ms.date: 11/04/2016
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
ms.openlocfilehash: c4f9ea7a3606612189e85401b75a0577896fd90e
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69493222"
---
# <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Eine ausführbare Datei kann mit einer DLL durch eine der folgenden Methoden verknüpft werden (bzw. diese laden):

- *Implizites verknüpfen*, wobei das Betriebssystem die dll lädt, wenn die ausführbare Datei, die Sie verwendet, geladen wird Die ausführbare Client Datei ruft die exportierten Funktionen der dll auf, so als ob die Funktionen statisch verknüpft sind und in der ausführbaren Datei enthalten sind. Implizites verknüpfen wird manchmal als *statisches Laden* oder *dynamisches Verknüpfen der Ladezeit*bezeichnet.

- *Explizites verknüpfen*, bei dem das Betriebssystem die dll bei Bedarf zur Laufzeit lädt. Eine ausführbare Datei, die eine DLL durch explizites verknüpfen verwendet, muss Funktionsaufrufe ausführen, um die dll explizit zu laden und zu entladen und auf die von der DLL exportierten Funktionen zuzugreifen. Anders als Aufrufe von Funktionen in einer statisch verknüpften Bibliothek muss die ausführbare Client Datei die exportierten Funktionen in einer DLL über einen Funktionszeiger aufrufen. Explizites verknüpfen wird manchmal als *dynamische Auslastung* oder *Lauf Zeit dynamische Verknüpfung*bezeichnet.

Eine ausführbare Datei kann eine der beiden Verknüpfungs Methoden verwenden, um eine Verknüpfung mit der gleichen dll Außerdem schließen sich diese Methoden nicht gegenseitig aus. eine ausführbare Datei kann implizit mit einer DLL verknüpft werden, und ein anderer kann Sie explizit anfügen.

<a name="determining-which-linking-method-to-use"></a>

## <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Ob implizites verknüpfen oder explizite Verknüpfungen verwendet werden müssen, ist eine architektonische Entscheidung, die Sie für Ihre Anwendung treffen müssen. Jede Methode hat vor-und Nachteile.

### <a name="implicit-linking"></a>Implizite Verknüpfung

Implizites verknüpfen tritt auf, wenn der Code einer Anwendung eine exportierte DLL-Funktion aufruft. Beim Kompilieren oder Assemblieren des Quellcodes für die aufrufende ausführbare Datei wird durch den DLL-Funktionsaufruf ein Verweis auf eine externe Funktion im Objektcode generiert. Um diesen externen Verweis aufzulösen, muss die Anwendung mit der Importbibliothek (LIB-Datei) verknüpft werden, die vom Ersteller der DLL bereitgestellt wird.

Die Importbibliothek enthält nur Code zum Laden der DLL sowie zum Implementieren von Funktionsaufrufen in der DLL. Wenn in einer Importbibliothek eine externe Funktion gefunden wird, wird der Linker informiert, dass der Code für diese Funktion in einer DLL enthalten ist. Um externe Verweise auf DLLs aufzulösen, fügt der Linker der ausführbaren Datei einfach Informationen hinzu. Dadurch wird dem System mitgeteilt, wo der DLL-Code zu finden ist, wenn der Prozess startet.

Wenn vom System ein Programm gestartet wird, das dynamisch verknüpfte Verweise enthält, verwendet es die Informationen in der ausführbaren Programmdatei, um die benötigten DLLs zu finden. Wird die DLL nicht gefunden, beendet das System den Prozess und zeigt ein Dialogfeld mit einer entsprechenden Fehlermeldung an. Andernfalls ordnet das System die DLL-Module im Adressbereich des Prozesses zu.

Wenn eine der DLLs über eine Einstiegspunkt Funktion für Initialisierungs-und Beendigungs Code verfügt `DllMain`, z. b., ruft das Betriebssystem die Funktion auf. Über einen der Parameter, die an die Einstiegspunktfunktion übergeben werden, wird Code definiert, der angibt, dass die DLL an den Prozess angefügt wird. Wenn die Einstiegspunktfunktion nicht den Wert TRUE zurückgibt, beendet das System den Prozess mit einer entsprechenden Fehlermeldung.

Schließlich ändert das System den ausführbaren Code des Prozesses, um Startadressen für die DLL-Funktionen bereitzustellen.

Der DLL-Code wird, wie der übrige Programmcode, nach dem Prozessstart im Adressbereich des Prozesses zugeordnet. Er wird nur bei Bedarf in den Arbeitsspeicher geladen. Folglich haben die Code Attribute `PRELOAD` und `LOADONCALL` , die von DEF-Dateien zum Steuern des Ladens in früheren Windows-Versionen verwendet werden, keine Bedeutung mehr.

### <a name="explicit-linking"></a>Explizite Verknüpfung

Die meisten Anwendungen verwenden die implizite Verknüpfung, da diese Verknüpfungsmethode am einfachsten anzuwenden ist. Es gibt jedoch Zeiten, in denen eine explizite Verknüpfung notwendig ist. Die folgenden Gründe sprechen häufig für die explizite Verknüpfung:

- Die Anwendung kennt den Namen einer DLL, die Sie zum Zeitpunkt der Laufzeit lädt. Die Anwendung kann z. b. den Namen der dll und der exportierten Funktionen beim Start aus einer Konfigurationsdatei abrufen.

- Ein Prozess, der implizites verknüpfen verwendet, wird vom Betriebssystem beendet, wenn die dll beim Prozessstart nicht gefunden wurde. Ein Prozess, bei dem explizite Verknüpfungen verwendet werden, wird in dieser Situation nicht beendet, und es kann versucht werden, den Fehler zu beheben. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.

- Ein Prozess, der implizites verknüpfen verwendet, wird auch beendet, wenn eine der DLLs, mit `DllMain` denen er verknüpft ist, eine Funktion enthält, die fehlschlägt. Ein Prozess, bei dem explizite Verknüpfungen verwendet werden, wird in dieser Situation nicht beendet.

- Eine Anwendung, die implizit mit zahlreichen DLLs verknüpft ist, wird u. U. langsam gestartet, da von Windows neben der Anwendung auch alle DLLs geladen werden. Um die Startleistung zu verbessern, kann eine Anwendung implizit nur mit den DLLs verknüpft werden, die unmittelbar nach dem Laden erforderlich sind, und warten, bis andere DLLs explizit mit Ihnen verknüpft werden müssen.

- Bei der expliziten Verknüpfung entfällt die Notwendigkeit, die Anwendung mit einer Import Bibliothek zu verknüpfen. Wenn Änderungen in der dll bewirken, dass die Export Ordinalzahlen geändert werden, müssen Anwendungen, die explizite Verknüpfungen verwenden, nicht erneut `GetProcAddress` verknüpft werden, wenn Sie mithilfe des Namens einer Funktion und nicht eines Ordinalwerts aufgerufen werden, während Anwendungen, die implizites verknüpfen verwenden, eine erneute Verknüpfung mit dem Neue Import Bibliothek.

Beachten Sie die beiden folgenden Schwachstellen im Zusammenhang mit der expliziten Verknüpfung:

- Wenn die dll über eine `DllMain` Einstiegspunkt Funktion verfügt, ruft das Betriebssystem die Funktion im Kontext des Threads auf, der `LoadLibrary`aufgerufen hat. Die Einstiegspunkt Funktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess angefügt wurde `LoadLibrary` , weil ein vorheriger Aufruf von vorhanden ist, der über keinen entsprechenden Aufruf der `FreeLibrary` -Funktion verfügt. Explizites verknüpfen kann Probleme verursachen, wenn die `DllMain` dll eine Funktion verwendet, um die Initialisierung für jeden Thread eines Prozesses auszuführen, da `LoadLibrary` Threads, `AfxLoadLibrary`die bereits vorhanden sind, wenn (oder) aufgerufen wird, nicht initialisiert werden.

- Wenn eine DLL statische Blockdaten als `__declspec(thread)`deklariert, kann Sie einen Schutz Fehler verursachen, wenn Sie explizit verknüpft ist. Nachdem die dll durch einen Aufruf von geladen wurde `LoadLibrary`, verursacht Sie einen Schutz Fehler, wenn der Code auf diese Daten verweist. (Statische Daten umfassen sowohl globale als auch lokale statische Elemente.) Wenn Sie also eine DLL erstellen, sollten Sie entweder die Verwendung des lokalen Thread Speichers vermeiden oder dll-Benutzern über die möglichen Fehler beim dynamischen Laden der dll informieren. Weitere Informationen finden Sie unter [Verwenden von lokalem Thread Speicher in einer Dynamic Link Library (Windows SDK)](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library).

<a name="linking-implicitly"></a>

## <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Um eine DLL durch implizites verknüpfen verwenden zu können, müssen ausführbare Client Dateien diese Dateien vom Anbieter der dll abrufen:

- Eine oder mehrere Header Dateien (. h-Dateien), die die Deklarationen der exportierten Daten, Funktionen und C++ /oder Klassen in der dll enthalten. Die von der DLL exportierten Klassen, Funktionen und Daten müssen in der Header `__declspec(dllimport)` Datei markiert werden. Weitere Informationen finden Sie unter [dllexport, dllimport](../cpp/dllexport-dllimport.md).

- Eine Import Bibliothek, die mit Ihrer ausführbaren Datei verknüpft werden soll. Der Linker erstellt die Import Bibliothek, wenn die dll erstellt wird. Weitere Informationen finden Sie unter [. LIB-Dateien](reference/dot-lib-files-as-linker-input.md).

- Die tatsächliche dll-Datei.

Um eine DLL durch implizites verknüpfen zu verwenden, muss eine ausführbare Datei die Header Dateien enthalten, die C++ die Daten, Funktionen oder Klassen deklarieren, die von der dll in jeder Quelldatei exportiert werden, die Aufrufe der exportierten Daten, Funktionen und Klassen enthält. Aus Codierungs Sicht entsprechen Aufrufe der exportierten Funktionen wie jeder andere Funktionsaufruf.

Um die aufrufende ausführbare Datei zu erstellen, stellen Sie eine Verknüpfung mit der Importbibliothek her. Wenn Sie ein externes Makefile-oder Buildsystem verwenden, geben Sie den Dateinamen der Import Bibliothek an, in der Sie andere Objektdateien (OBJ-Dateien) oder Bibliotheken auflisten, die Sie verknüpfen.

Das Betriebssystem muss in der Lage sein, die DLL-Datei beim Laden der aufrufenden ausführbaren Datei zu lokalisieren. Dies bedeutet, dass Ihre Anwendung das vorhanden sein der DLL bereitstellen oder überprüfen muss, wenn die Anwendung installiert ist.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>Explizites verknüpfen mit einer dll

Um eine DLL durch explizites verknüpfen verwenden zu können, müssen Anwendungen einen Funktionsaufruf durchführen, um die dll zur Laufzeit explizit zu laden. Für die explizite Verknüpfung mit einer DLL muss eine Anwendung folgende Schritte ausführen:

- Rufen Sie [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`oder eine ähnliche Funktion zum Laden der dll und zum Abrufen eines Modul Handles auf.

- Rufen Sie [GetProcAddress](getprocaddress.md) auf, um einen Funktionszeiger auf jede exportierte Funktion zu erhalten, die die Anwendung aufruft. Da Anwendungen die DLL-Funktionen mithilfe eines Zeigers aufzurufen, generiert der Compiler keine externen Verweise, daher besteht keine Notwendigkeit, eine Verknüpfung mit einer Import Bibliothek zu erstellen. Sie müssen jedoch über eine `typedef` -oder `using` -Anweisung verfügen, die die Rückruf Signatur der von Ihnen aufzurufenden exportierten Funktionen definiert.

- Rufen Sie [FreeLibrary](freelibrary-and-afxfreelibrary.md) auf, wenn Sie mit der dll abgeschlossen sind.

Beispielsweise ruft `LoadLibrary` diese Beispiel Funktion auf, um eine DLL mit dem Namen "myDll" `GetProcAddress` zu laden, ruft auf, um einen Zeiger auf eine Funktion mit dem Namen "DLLFunc1" zu erhalten, ruft die `FreeLibrary` Funktion auf und speichert das Ergebnis und ruft dann auf, um die dll zu entladen.

```C
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)
{
    HINSTANCE hDLL;               // Handle to DLL
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer
    HRESULT hrReturnVal;

    hDLL = LoadLibrary("MyDLL");
    if (NULL != hDLL)
    {
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");
        if (NULL != lpfnDllFunc1)
        {
            // call the function
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);
        }
        else
        {
            // report the error
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }
    return hrReturnVal;
}
```

Anders als in diesem Beispiel sollten Sie in den meisten Fällen `LoadLibrary` und `FreeLibrary` nur einmal in der Anwendung für eine bestimmte DLL aufrufen, insbesondere wenn Sie mehrere Funktionen in der DLL aufrufen oder DLL-Funktionen wiederholt aufrufen.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Arbeiten mit Importbibliotheken und Exportdateien](reference/working-with-import-libraries-and-export-files.md)

- [Such Reihenfolge der Dynamic Link Library](/windows/win32/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
