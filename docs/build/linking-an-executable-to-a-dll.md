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
ms.openlocfilehash: b0a3a0acd9fe0270416745696079e382c35ec32d
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220654"
---
# <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Eine ausführbare Datei kann mit einer DLL durch eine der folgenden Methoden verknüpft werden (bzw. diese laden):

- *Implizite Verknüpfung*, in denen das Betriebssystem die DLL lädt, wenn die ausführbare Datei, die mit der sie geladen wird. Der ausführbare Client Ruft die exportierten Funktionen der DLL, als ob die Funktionen statisch verknüpft und innerhalb der ausführbaren Datei enthalten waren. Implizite Verknüpfung wird mitunter als *statisches Laden* oder *dynamisches Verknüpfen zur Ladezeit*.

- *Explizite Verknüpfung*, in denen das Betriebssystem die DLL auf Anforderung zur Laufzeit geladen. Eine ausführbare Datei, die eine DLL durch die explizite Verknüpfung verwendet muss Funktionsaufrufe explizit zu laden und Entladen der DLL und auf die von der DLL exportierten Funktionen zugreifen, werden. Im Gegensatz zum Aufrufen von Funktionen in einer statisch verknüpften Bibliothek muss die ausführbare Clientdatei die exportierten Funktionen in einer DLL über einen Funktionszeiger aufrufen. Explizite Verknüpfung wird mitunter als *dynamischer Auslastung* oder *dynamisches Verknüpfen zur Laufzeit*.

Eine ausführbare Datei kann beide Verknüpfungsmethoden verwenden, um mit derselben DLL verknüpfen. Darüber hinaus sind diese Methoden nicht gegenseitig. eine ausführbare Datei implizit mit einer DLL verknüpfen kann, und eine andere angefügt werden kann explizit.

<a name="determining-which-linking-method-to-use"></a>

## <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Angibt, ob implizite Verknüpfung oder explizite Verknüpfung verwenden, ist Bestandteil der architekturbezogenen Entscheidung, die Sie für Ihre Anwendung vornehmen müssen. Es gibt vor- und Nachteile jeder Methode.

### <a name="implicit-linking"></a>Implizite Verknüpfung

Implizite Verknüpfung tritt auf, wenn der Code einer Anwendung eine exportierte DLL-Funktion aufruft. Beim Kompilieren oder Assemblieren des Quellcodes für die aufrufende ausführbare Datei wird durch den DLL-Funktionsaufruf ein Verweis auf eine externe Funktion im Objektcode generiert. Um diesen externen Verweis aufzulösen, muss die Anwendung mit der Importbibliothek (LIB-Datei) verknüpft werden, die vom Ersteller der DLL bereitgestellt wird.

Die Importbibliothek enthält nur Code zum Laden der DLL sowie zum Implementieren von Funktionsaufrufen in der DLL. Wenn in einer Importbibliothek eine externe Funktion gefunden wird, wird der Linker informiert, dass der Code für diese Funktion in einer DLL enthalten ist. Um externe Verweise auf DLLs aufzulösen, fügt der Linker der ausführbaren Datei einfach Informationen hinzu. Dadurch wird dem System mitgeteilt, wo der DLL-Code zu finden ist, wenn der Prozess startet.

Wenn vom System ein Programm gestartet wird, das dynamisch verknüpfte Verweise enthält, verwendet es die Informationen in der ausführbaren Programmdatei, um die benötigten DLLs zu finden. Wird die DLL nicht gefunden, beendet das System den Prozess und zeigt ein Dialogfeld mit einer entsprechenden Fehlermeldung an. Andernfalls ordnet das System die DLL-Module im Adressbereich des Prozesses zu.

Wenn eine der DLLs verfügt über eine Einstiegspunktfunktion für Initialisierungs-und Terminierungscode wie `DllMain`, ruft das Betriebssystem die Funktion. Über einen der Parameter, die an die Einstiegspunktfunktion übergeben werden, wird Code definiert, der angibt, dass die DLL an den Prozess angefügt wird. Wenn die Einstiegspunktfunktion nicht den Wert TRUE zurückgibt, beendet das System den Prozess mit einer entsprechenden Fehlermeldung.

Schließlich ändert das System den ausführbaren Code des Prozesses, um Startadressen für die DLL-Funktionen bereitzustellen.

Der DLL-Code wird, wie der übrige Programmcode, nach dem Prozessstart im Adressbereich des Prozesses zugeordnet. Er wird nur bei Bedarf in den Arbeitsspeicher geladen. Daher die `PRELOAD` und `LOADONCALL` von DEF-Dateien, um zu steuern, die beim Laden in früheren Versionen von Windows nicht mehr verwendeten Codeattribute Bedeutung haben.

### <a name="explicit-linking"></a>Explizite Verknüpfung

Die meisten Anwendungen verwenden die implizite Verknüpfung, da diese Verknüpfungsmethode am einfachsten anzuwenden ist. Es gibt jedoch noch Mal, wenn die explizite Verknüpfung erforderlich ist. Die folgenden Gründe sprechen häufig für die explizite Verknüpfung:

- Die Anwendung kennt nicht den Namen einer DLL, die bis zur Laufzeit geladen. Beispielsweise kann die Anwendung den Namen der DLL und die exportierten Funktionen aus einer Konfigurationsdatei beim Start erhalten.

- Ein Prozess, der implizite Verknüpfung verwendet wird vom Betriebssystem beendet, wenn die DLL beim Start des Prozesses nicht gefunden wird. Ein Prozess, der explizite Verknüpfung verwendet wird in dieser Situation nicht beendet, und kann versuchen, die Verarbeitung fortzusetzen. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.

- Ein Prozess, die implizite Verknüpfung verwendet wird auch beendet, wenn eine der DLLs, die es verknüpft ist eine `DllMain` -Funktion, die ein Fehler auftritt. Ein Prozess, der die explizite Verknüpfung verwendet, ist in dieser Situation nicht beendet.

- Eine Anwendung, die implizit mit zahlreichen DLLs verknüpft ist, wird u. U. langsam gestartet, da von Windows neben der Anwendung auch alle DLLs geladen werden. Um die startleistung zu verbessern, kann eine Anwendung implizit nur mit verknüpft denjenigen DLLs sofort nach dem Laden, und warten Sie erforderlich sind, bis die anderen DLL-Dateien erforderlich sind, explizit auf diese zu verknüpfen.

- Explizite Verknüpfung entfällt die Notwendigkeit, die Anwendung mit einer Importbibliothek zu verknüpfen. Wenn Änderungen in der DLL dazu führen, die Exportordinalzahlen dass ändern, Anwendungen, die explizite Verknüpfung müssen nicht erneut binden, wenn sie rufen `GetProcAddress` verwenden den Namen einer Funktion und keinen Ordinalwert, während Anwendungen, die implizite Verknüpfung verwenden, neu verknüpfen, müssen der neuen Importbibliothek.

Beachten Sie die beiden folgenden Schwachstellen im Zusammenhang mit der expliziten Verknüpfung:

- Wenn die DLL hat eine `DllMain` Einstiegspunktfunktion, ruft das Betriebssystem die Funktion im Kontext des Threads, der Namen `LoadLibrary`. Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess, aufgrund eines vorherigen Aufrufs von angefügt ist `LoadLibrary` hatte, die ohne entsprechenden Aufruf der `FreeLibrary` Funktion. Explizite Verknüpfung kann Probleme verursachen, wenn die DLL verwendet eine `DllMain` Funktion, um die Initialisierung für jeden Thread eines Prozesses ausgeführt werden, da Threads, die bereits vorhanden sein. bei `LoadLibrary` (oder `AfxLoadLibrary`) wird aufgerufen, nicht initialisiert werden.

- Wenn eine DLL statische Daten deklariert `__declspec(thread)`, es kann dazu führen, dass eine schutzverletzung, wenn explizit verknüpft. Nach dem Laden der DLL durch einen Aufruf von `LoadLibrary`, eine schutzverletzung, sobald der Code auf diese Daten verwiesen wird. (Statische Daten umfassen sowohl globale als auch lokale statische Elemente.) Aus diesem Grund bei der Erstellung einer DLL Sie vermeiden Sie die Verwendung von threadlokalen Speicher oder DLL-Benutzer über die potenziellen Fallstricke bei, das dynamische Laden der DLL informieren. Weitere Informationen finden Sie unter [mithilfe von threadlokalen Speicher in einer Dynamic Link Library (Windows SDK)](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library).

<a name="linking-implicitly"></a>

## <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen

Um eine DLL-Datei werden durch die implizite Verknüpfung verwenden, müssen die ausführbaren Clientdateien diese Dateien vom Anbieter der DLL abrufen:

- Eine oder mehrere Headerdateien (.h-Dateien), die die Deklarationen der exportierten Daten, die Funktionen und/oder C++-Klassen in der DLL enthalten. Die Klassen, Funktionen und Daten, die von der DLL exportierten müssen alle gekennzeichnet werden `__declspec(dllimport)` in der Headerdatei. Weitere Informationen finden Sie unter [Dllexport, Dllimport](../cpp/dllexport-dllimport.md).

- Eine Importbibliothek in der ausführbaren Datei zu verknüpfen. Der Linker erstellt die Importbibliothek, wenn die DLL erstellt wird. Weitere Informationen finden Sie unter [. LIB-Dateien](reference/dot-lib-files-as-linker-input.md).

- Die tatsächliche DLL-Datei.

Um eine DLL-Datei werden durch die implizite Verknüpfung verwenden, muss eine ausführbare Datei die Header-Dateien enthalten, die die Daten, Funktionen oder C++-Klassen, die von der DLL in jeder Quelldatei, die Aufrufe an den exportierten Daten, Funktionen und Klassen enthält exportierten deklarieren. Sind hinsichtlich der Codierung Aufrufe an die exportierten Funktionen, wie ein anderer Funktionsaufruf.

Um die aufrufende ausführbare Datei zu erstellen, stellen Sie eine Verknüpfung mit der Importbibliothek her. Wenn Sie ein externes Makefile verwenden oder System zu erstellen, geben Sie den Dateinamen der Importbibliothek her, in dem Sie andere Objektdateien (obj) auflisten, oder Bibliotheken, die Sie verknüpfen.

Das Betriebssystem muss in der Lage sein, die DLL-Datei beim Laden der aufrufenden ausführbaren Datei zu lokalisieren. Dies bedeutet, dass Ihre Anwendung bereitstellen muss, oder Überprüfen Sie, ob der DLL an, wenn die Anwendung installiert ist.

<a name="linking-explicitly"></a>

## <a name="how-to-link-explicitly-to-a-dll"></a>Wie Sie die explizite Verknüpfung mit einer DLL

Um eine DLL-Datei durch die explizite Verknüpfung verwenden, müssen Anwendungen einen Funktionsaufruf explizit laden die DLL zur Laufzeit vornehmen. Für die explizite Verknüpfung mit einer DLL muss eine Anwendung folgende Schritte ausführen:

- Rufen Sie [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, oder eine ähnliche Funktion die DLL zu laden und ein Modulhandle zu erhalten.

- Rufen Sie [GetProcAddress](getprocaddress.md) exportiert einen Funktionszeiger auf die einzelnen erhalten-Funktion, die die Anwendung aufruft. Da Anwendungen die DLL-Funktionen über einen Zeiger aufrufen, ist der Compiler keine externen Verweise generieren. daher keine Notwendigkeit besteht, mit einer Importbibliothek zu verknüpfen. Allerdings benötigen Sie eine `typedef` oder `using` -Anweisung, die der Aufrufsignatur aus der exportierten Funktionen definiert, die Sie aufrufen.

- Rufen Sie [FreeLibrary](freelibrary-and-afxfreelibrary.md) Wenn die DLL nicht mehr benötigen.

Diese Beispielfunktion ruft z. B. `LoadLibrary` zum Laden einer DLL, die mit dem Namen "Eigene", ruft `GetProcAddress` zum Abrufen von eines Zeigers auf eine Funktion, die mit dem Namen "DLLFunc1", ruft die Funktion speichert das Ergebnis und ruft dann `FreeLibrary` Endladen die DLL.

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

Im Gegensatz zu in diesem Beispiel in den meisten Fällen Sie sollten Aufrufen `LoadLibrary` und `FreeLibrary` wiederholt nur einmal in Ihrer Anwendung für eine bestimmte DLL, insbesondere dann, wenn Sie beabsichtigen, mehrere Funktionen in der DLL aufrufen oder DLL-Funktionen.

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Arbeiten mit Importbibliotheken und Exportdateien](reference/working-with-import-libraries-and-export-files.md)

- [Dynamic Link Library Search Order](/windows/desktop/Dlls/dynamic-link-library-search-order)

## <a name="see-also"></a>Siehe auch

[Erstellen von C/C++-DLLs in Visual Studio](dlls-in-visual-cpp.md)
