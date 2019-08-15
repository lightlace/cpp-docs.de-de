---
title: 'Multithreading: Erstellen von Arbeitsthreads in MFC'
ms.date: 11/04/2016
helpviewer_keywords:
- multithreading [C++], worker threads
- background tasks [C++]
- threading [C++], worker threads
- worker threads [C++]
- threading [C++], creating threads
- threading [MFC], worker threads
- threading [C++], user input not required
ms.assetid: 670adbfe-041c-4450-a3ed-be14aab15234
ms.openlocfilehash: c8df3dd9d17819b23362a3b31d8e198883aa9143
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512051"
---
# <a name="multithreading-creating-worker-threads-in-mfc"></a>Multithreading: Erstellen von Arbeitsthreads in MFC

Ein Arbeitsthread wird normalerweise zur Behandlung von Hintergrundaufgaben verwendet. Auf diese Weise muss der Benutzer nicht auf deren Beendung warten, um mit der Anwendung weiterarbeiten zu können. Aufgaben wie Neuberechnung und Hintergrunddruck sind gute Beispiele für Arbeitsthreads. In diesem Thema werden die notwendigen Schritte zur Erstellung eines Arbeitsthreads ausführlich erläutert. Folgende Themen werden behandelt:

- [Starten des Threads](#_core_starting_the_thread)

- [Implementieren der Steuerungsfunktion](#_core_implementing_the_controlling_function)

- [Beispiel](#_core_controlling_function_example)

Die Erstellung eines Arbeitsthreads ist eine verhältnismäßig einfache Aufgabe. Zur Aktivierung des Threads sind lediglich zwei Schritte erforderlich: das Implementieren einer Steuerungsfunktion und das Starten des Threads. Das Ableiten einer Klasse von [CWinThread](../mfc/reference/cwinthread-class.md)ist nicht erforderlich. Sie können eine Klasse ableiten, wenn Sie eine spezielle Version von `CWinThread` benötigen, dies ist jedoch für die meisten einfachen Arbeitsthreads nicht erforderlich. `CWinThread` kann unverändert verwendet werden.

##  <a name="_core_starting_the_thread"></a>Starten des Threads

Es gibt zwei überladene Versionen von `AfxBeginThread`: eine, mit der nur Arbeitsthreads erstellt werden können, und eine, mit der Benutzeroberflächenthreads und Arbeitsthreads erstellt werden können. Um die Ausführung des Arbeitsthreads mithilfe der ersten Überladung zu starten, geben Sie [AfxBeginThread](../mfc/reference/application-information-and-management.md#afxbeginthread)an, und geben Sie dabei die folgenden Informationen an:

- Die Adresse der Steuerungsfunktion

- Den an die Steuerungsfunktion zu übergebenden Parameter

- (Optional) Die gewünschte Priorität des Threads Standardmäßig ist normale Priorität eingestellt. Weitere Informationen zu den verfügbaren Prioritätsstufen finden Sie unter [SetThreadPriority](/windows/win32/api/processthreadsapi/nf-processthreadsapi-setthreadpriority) in der Windows SDK.

- (Optional) Die gewünschte Stapelgröße für den Thread. Standardmäßig wird die Größe des Erstellungsthreads verwendet.

- Optionale CREATE_SUSPENDED, wenn der Thread im angehaltenen Zustand erstellt werden soll. Standardmäßig ist 0 eingestellt; Sie können den Thread auch normal starten.

- (Optional) Die gewünschten Sicherheitsattribute Standardmäßig werden dieselben Zugriffsrechte wie für den übergeordneten Thread verwendet. Weitere Informationen zum Format dieser Sicherheitsinformationen finden Sie unter [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) im Windows SDK.

`AfxBeginThread` generiert und initialisiert ein `CWinThread`-Objekt automatisch, startet es und gibt seine Adresse zurück, damit Sie zu einem späteren Zeitpunkt darauf Bezug nehmen können. Während der gesamten Prozedur wird überprüft, ob alle Objekte ordnungsgemäß freigegeben werden, falls ein Teil des Erstellungsprozesses fehlschlagen sollte.

##  <a name="_core_implementing_the_controlling_function"></a>Implementieren der Steuerungsfunktion

Der Thread wird durch die Steuerungsfunktion definiert. Der Thread beginnt am Anfang dieser Funktion und wird bei Erreichen des Endes dieser Funktion terminiert. Diese Funktion sollte folgenden Prototyp aufweisen:

```
UINT MyControllingFunction( LPVOID pParam );
```

Bei dem Parameter handelt es sich um einen einzelnen Wert. Der Wert, den die Funktion in diesem Parameter empfängt, ist der Wert, der bei der Erstellung des Threadobjekts an den Konstruktor übergeben wurde. Die Steuerungsfunktion kann diesen Wert auf beliebige Art und Weise interpretieren: Er kann als Skalarwert oder als Zeiger auf eine Struktur mit mehreren Parametern behandelt werden, oder er kann ignoriert werden. Falls sich der Parameter auf eine Struktur bezieht, kann diese nicht nur zur Übergabe von Daten vom Aufrufer an den Thread verwendet werden, sondern auch zur Rückgabe von Daten vom Thread an den Aufrufer. Wenn Sie eine Struktur dieser Art zur Rückgabe von Daten an den Aufrufer verwenden, muss der Aufrufer vom Thread benachrichtigt werden, sobald die Ergebnisse verfügbar sind. Informationen zur Kommunikation zwischen dem Arbeits Thread und dem Aufrufer finden [Sie unter Multithreading: Programmiertipps](multithreading-programming-tips.md).

Wenn die Funktion beendet wird, sollte Sie einen uint-Wert zurückgeben, der den Grund für die Beendigung angibt. Normalerweise lautet dieser Exitcode 0; dies steht für eine erfolgreiche Ausführung. Andere Werte stehen für unterschiedliche Fehlertypen. Dies hängt ausschließlich von der Implementierung ab. Einige Threads verwalten eventuell einen Verwendungszähler für Objekte und geben die aktuelle Anzahl der Verwendungen des jeweiligen Objekts zurück. Informationen dazu, wie Anwendungen diesen Wert abrufen können, [finden Sie unter Multithreading: Beenden von](multithreading-terminating-threads.md)Threads.

Multithreadprogramme, die mit der MFC-Bibliothek geschrieben wurden, haben einige Einschränkungen. Beschreibungen dieser Einschränkungen und andere Tipps zur Verwendung von Threads finden [Sie unter Multithreading: Programmiertipps](multithreading-programming-tips.md).

##  <a name="_core_controlling_function_example"></a>Beispiel für eine Steuerungsfunktion

Aus dem folgenden Beispiel geht hervor, wie Sie eine Steuerungsfunktion definieren und diese von einem anderen Teil des Programms aus verwenden.

```
UINT MyThreadProc( LPVOID pParam )
{
    CMyObject* pObject = (CMyObject*)pParam;

    if (pObject == NULL ||
        !pObject->IsKindOf(RUNTIME_CLASS(CMyObject)))
    return 1;   // if pObject is not valid

    // do something with 'pObject'

    return 0;   // thread completed successfully
}

// inside a different function in the program
.
.
.
pNewObject = new CMyObject;
AfxBeginThread(MyThreadProc, pNewObject);
.
.
.
```

## <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [Multithreading: Erstellen von Benutzeroberflächenthreads](multithreading-creating-user-interface-threads.md)

## <a name="see-also"></a>Siehe auch

[Multithreading mit C++ und MFC](multithreading-with-cpp-and-mfc.md)
