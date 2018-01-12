---
title: "Verknüpfen eine ausführbaren Datei mit einer DLL | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6bdc8d4b372a589beb51d2f8a9bc05b1aa241c48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="link-an-executable-to-a-dll"></a>Eine ausführbare Datei mit einer DLL verknüpfen  
  
Eine ausführbare Datei kann mit einer DLL durch eine der folgenden Methoden verknüpft werden (bzw. diese laden):  
  
-   *Implizite Verknüpfung*, in denen das Betriebssystem die DLL lädt, wenn die ausführbare Datei mit der sie geladen wird. Der ausführbare Client Ruft die exportierten Funktionen der DLL, als ob die Funktionen wurden statisch verknüpft und in die ausführbare Datei enthalten sind. Implizite Verknüpfung wird gelegentlich als bezeichnet *statisches Laden* oder *dynamisches Verknüpfen zur Ladezeit*.  
  
-   *Explizite Verknüpfung*, wo das Betriebssystem die DLL zur Laufzeit bedarfsgesteuert lädt. Eine ausführbare Datei, die eine DLL durch die explizite Verknüpfung verwendet achten Funktionsaufrufe explizit zu laden und Entladen der DLL und auf die von der DLL exportierten Funktionen zugreifen. Im Gegensatz zu Aufrufen von Funktionen in einer statisch verknüpften Bibliothek muss die ausführbare Clientdatei exportierten Funktionen in einer DLL über einen Funktionszeiger aufrufen. Explizite Verknüpfung wird gelegentlich als bezeichnet *dynamisches Laden* oder *dynamisches Verknüpfen zur Laufzeit*.  
  
Beide Verknüpfungsmethoden können eine ausführbare Datei mit derselben DLL verknüpfen. Darüber hinaus sind diese Methoden nicht gegenseitig. eine ausführbare Datei implizit mit einer DLL verknüpfen kann, und eine andere angefügt werden kann explizit.  
  
<a name="determining-which-linking-method-to-use"></a>  
  
## <a name="determine-which-linking-method-to-use"></a>Ermitteln, welche Verknüpfungsmethode verwendet werden soll  
  
Soll eine implizite Verknüpfung oder explizite Verknüpfung verwenden, ist eine Entscheidung hinsichtlich der Architektur, die Sie für Ihre Anwendung vornehmen müssen. Es gibt vor- und Nachteile der einzelnen Methoden.  
  
### <a name="implicit-linking"></a>Implizite Verknüpfung  
  
Implizite Verknüpfung tritt auf, wenn der Code einer Anwendung eine exportierte DLL-Funktion aufruft. Beim Kompilieren oder Assemblieren des Quellcodes für die aufrufende ausführbare Datei wird durch den DLL-Funktionsaufruf ein Verweis auf eine externe Funktion im Objektcode generiert. Um diesen externen Verweis aufzulösen, muss die Anwendung mit der Importbibliothek (LIB-Datei) verknüpft werden, die vom Ersteller der DLL bereitgestellt wird.  
  
Die Importbibliothek enthält nur Code zum Laden der DLL sowie zum Implementieren von Funktionsaufrufen in der DLL. Wenn in einer Importbibliothek eine externe Funktion gefunden wird, wird der Linker informiert, dass der Code für diese Funktion in einer DLL enthalten ist. Um externe Verweise auf DLLs aufzulösen, fügt der Linker der ausführbaren Datei einfach Informationen hinzu. Dadurch wird dem System mitgeteilt, wo der DLL-Code zu finden ist, wenn der Prozess startet.  
  
Wenn vom System ein Programm gestartet wird, das dynamisch verknüpfte Verweise enthält, verwendet es die Informationen in der ausführbaren Programmdatei, um die benötigten DLLs zu finden. Wird die DLL nicht gefunden, beendet das System den Prozess und zeigt ein Dialogfeld mit einer entsprechenden Fehlermeldung an. Andernfalls ordnet das System die DLL-Module im Adressbereich des Prozesses zu.  
  
Wenn eine der DLLs verfügt über eine Einstiegspunktfunktion für Initialisierungs-und Terminierungscode wie `DllMain`, ruft das Betriebssystem die Funktion. Über einen der Parameter, die an die Einstiegspunktfunktion übergeben werden, wird Code definiert, der angibt, dass die DLL an den Prozess angefügt wird. Wenn die Einstiegspunktfunktion nicht den Wert TRUE zurückgibt, beendet das System den Prozess mit einer entsprechenden Fehlermeldung.  
  
Schließlich ändert das System den ausführbaren Code des Prozesses, um Startadressen für die DLL-Funktionen bereitzustellen.  
  
Der DLL-Code wird, wie der übrige Programmcode, nach dem Prozessstart im Adressbereich des Prozesses zugeordnet. Er wird nur bei Bedarf in den Arbeitsspeicher geladen. Daher die `PRELOAD` und `LOADONCALL` von DEF-Dateien, um zu steuern, die beim Laden in früheren Versionen von Windows nicht mehr verwendeten Codeattribute Bedeutung haben.  
  
### <a name="explicit-linking"></a>Explizite Verknüpfung  
  
Die meisten Anwendungen verwenden die implizite Verknüpfung, da diese Verknüpfungsmethode am einfachsten anzuwenden ist. Es gibt jedoch noch Mal, wenn die explizite Verknüpfung erforderlich ist. Die folgenden Gründe sprechen häufig für die explizite Verknüpfung:  
  
-   Die Anwendung kennt nicht den Namen einer DLL, die erst zur Laufzeit geladen. Die Anwendung kann z. B. den Namen der DLL und der exportierten Funktionen aus einer Konfigurationsdatei beim Start abrufen.  
  
-   Ein Prozess, der implizite Verknüpfung verwendet wird vom Betriebssystem beendet, wenn die DLL beim Starten des Prozesses nicht gefunden wird. Ein Prozess, der explizite Verknüpfung verwendet wird in dieser Situation nicht beendet und kann versuchen, die Verarbeitung fortzusetzen. So könnte der Prozess z. B. dem Benutzer den Fehler melden und ihn veranlassen, einen anderen Pfad für die DLL anzugeben.  
  
-   Ein Prozess, die implizite Verknüpfung verwendet wird auch beendet, wenn eine der DLLs, die es verknüpft ist eine `DllMain` -Funktion, die ein Fehler auftritt. Ein Prozess, der explizite Verknüpfung verwendet wird in dieser Situation nicht beendet.  
  
-   Eine Anwendung, die implizit mit zahlreichen DLLs verknüpft ist, wird u. U. langsam gestartet, da von Windows neben der Anwendung auch alle DLLs geladen werden. Um den Start zu beschleunigen, kann eine Anwendung implizit nur mit verknüpft denjenigen DLLs erforderlich direkt nach dem Laden, warten Sie bis die anderen DLLs erst erforderlich sind, damit die explizite Verknüpfung.  
  
-   Explizite Verknüpfung entfällt die Notwendigkeit, die Anwendung mit einer Importbibliothek zu verknüpfen. Wenn Änderungen in der DLL dazu führen, die Exportordinalzahlen dass ändern, Anwendungen, die explizite Verknüpfung verwenden müssen nicht erneut binden, wenn sie aufrufen `GetProcAddress` unter Verwendung des Namens einer Funktion und nicht durch einen Ordinalwert, während die Anwendungen, die implizite Verknüpfung verwenden, erneut binden, müssen die neuen Importbibliothek.  
  
Beachten Sie die beiden folgenden Schwachstellen im Zusammenhang mit der expliziten Verknüpfung:  
  
-   Wenn die DLL hat eine `DllMain` Einstiegspunktfunktion, ruft das Betriebssystem die Funktion im Kontext des Threads, die aufgerufen `LoadLibrary`. Die Einstiegspunktfunktion wird nicht aufgerufen, wenn die DLL bereits an den Prozess, aufgrund eines vorherigen Aufrufs von angefügt ist `LoadLibrary` hatte, die ohne entsprechenden Aufruf der `FreeLibrary` Funktion. Explizite Verknüpfung kann Probleme verursachen, wenn die DLL verwendet eine `DllMain` Funktion, um die Initialisierung für jeden Thread eines Prozesses ausgeführt werden, weil Threads, die bereits vorhanden sind beim `LoadLibrary` (oder `AfxLoadLibrary`) aufgerufen wird nicht initialisiert werden.  
  
-   Wenn eine DLL statische Daten als deklariert `__declspec(thread)`, sie können eine allgemeine schutzverletzung auftreten, wenn explizit verknüpft. Nach dem Laden der DLL durch einen Aufruf von `LoadLibrary`, eine allgemeine schutzverletzung, sobald der Code auf diese Daten verwiesen wird. (Statische Daten umfassen sowohl globale als auch lokale statische Elemente.) Aus diesem Grund Wenn Sie eine DLL erstellen, sollten Sie vermeiden Sie die Verwendung von lokalem Threadspeicher oder DLL-Benutzer über die potenzielle Fehlerquellen dynamisches Laden der DLL informieren. Weitere Informationen finden Sie unter [threadlokalen Speicher in einer Dynamic Link Library (Windows SDK) mit](http://msdn.microsoft.com/library/windows/desktop/ms686997).  
  
<a name="linking-implicitly"></a>  
  
## <a name="how-to-link-implicitly-to-a-dll"></a>Gewusst wie: implizit mit einer DLL verknüpfen  
  
Um eine DLL-Datei durch die implizite Verknüpfung zu verwenden, benötigen ausführbaren Clientdateien diese Dateien vom Anbieter der DLL:  
  
-   Eine oder mehrere Headerdateien (.h-Dateien), die die Deklarationen der exportierten Daten, die Funktionen und/oder C++-Klassen in der DLL enthalten. Die Klassen, Funktionen und Daten, die von der DLL exportierten müssen alle markiert werden `__declspec(dllimport)` in der Headerdatei. Weitere Informationen finden Sie unter [Dllexport, Dllimport](../cpp/dllexport-dllimport.md).  
  
-   Eine Importbibliothek, in der ausführbaren Datei zu verknüpfen. Der Linker erstellt der Importbibliothek her, wenn die DLL erstellt wird. Weitere Informationen finden Sie unter [. LIB-Dateien](../build/reference/dot-lib-files-as-linker-input.md).  
  
-   Die tatsächliche DLL-Datei.  
  
Um eine DLL-Datei durch die implizite Verknüpfung zu verwenden, muss eine ausführbare Datei die Headerdateien enthalten, die die Daten, Funktionen oder C++-Klassen, die von der DLL in jeder Quelldatei, die Aufrufe der exportierten Daten, Funktionen und Klassen enthält exportierten deklarieren. Hinsichtlich der Codierung unterscheiden sind Aufrufe der exportierten Funktionen wie jeden anderen Funktionsaufruf.  
  
Um die aufrufende ausführbare Datei zu erstellen, stellen Sie eine Verknüpfung mit der Importbibliothek her. Wenn Sie ein externes Makefile verwenden oder Buildsystem, geben Sie den Dateinamen der Importbibliothek her, in dem Sie andere Objektdateien (.obj) auflisten, oder Bibliotheken, die Sie verknüpfen.  
  
Das Betriebssystem muss in der Lage sein, die DLL-Datei beim Laden der aufrufenden ausführbaren Datei zu lokalisieren. Dies bedeutet, dass Ihre Anwendung muss bereitstellen oder Überprüfen Sie das Vorhandensein der DLL, wenn die Anwendung installiert ist.   
  
<a name="linking-explicitly"></a>  
  
## <a name="how-to-link-explicitly-to-a-dll"></a>Gewusst wie: die explizite Verknüpfung mit einer DLL  
  
Um eine DLL-Datei durch die explizite Verknüpfung verwenden zu können, müssen Anwendungen einen Funktionsaufruf explizit laden die DLL zur Laufzeit vornehmen. Für die explizite Verknüpfung mit einer DLL muss eine Anwendung folgende Schritte ausführen:  
  
-   Rufen Sie [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, oder eine ähnliche Funktion zum Laden der DLL und ein Modulhandle zu erhalten.  
  
-   Rufen Sie [GetProcAddress](getprocaddress.md) abzurufenden einen Funktionszeiger auf jede exportierte Funktion, die die Anwendung aufruft. Da Anwendungen die DLL-Funktionen über einen Zeiger aufrufen, löst der Compiler keine externen Verweise, daher keine Notwendigkeit besteht, mit einer Importbibliothek zu verknüpfen. Allerdings benötigen Sie ein `typedef` oder `using` -Anweisung, die Aufrufsignatur der exportierten Funktionen definiert, die aufgerufen werden.   
  
-   Rufen Sie [FreeLibrary](freelibrary-and-afxfreelibrary.md) Wenn die DLL nicht mehr benötigen.  
  
Dieses Beispiel z. B.-Funktionsaufrufe `LoadLibrary` zum Laden einer DLL, die mit dem Namen "Eigene", ruft `GetProcAddress` um einen Zeiger auf eine Funktion mit dem Namen "DLLFunc1", ruft die Funktion speichert das Ergebnis und ruft dann `FreeLibrary` zum Entladen der DLL. 
  
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
  
Anders als in diesem Beispiel wird in den meisten Fällen Sie sollten Aufrufen `LoadLibrary` und `FreeLibrary` nur einmal in der Anwendung für eine bestimmte DLL, insbesondere dann, wenn Sie beabsichtigen, mehrere Funktionen in der DLL aufrufen oder DLL-Funktionen wiederholt.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [Arbeiten mit Importbibliotheken und Exportdateien](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [Der Suchpfad zum Auffinden einer DLL von Windows verwendeter](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## <a name="see-also"></a>Siehe auch  
 [DLLs in Visual C++](../build/dlls-in-visual-cpp.md)