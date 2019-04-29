---
title: 'TN058: MFC-Modulzustandsimplementierung'
ms.date: 06/28/2018
f1_keywords:
- vc.mfc.implementation
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: db34f528e70a7dcc437836684656b3ce8a4078fd
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62399595"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC-Modulzustandsimplementierung

> [!NOTE]
> Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Diese technische Hinweis beschreibt die Implementierung von MFC-"Modulstatus" erstellt. Ein Überblick über die Implementierung der Modul-Zustand ist wichtig, für die MFC DLLs aus einer DLL gemeinsam genutzte (oder in-Process-OLE-Server).

Vor dem Lesen diesen Hinweis, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" im [Erstellen neuer Dokumente, Windows und Ansichten](../mfc/creating-new-documents-windows-and-views.md). Dieser Artikel enthält wichtige Informationen und allgemeine Informationen zu diesem Thema.

## <a name="overview"></a>Übersicht

Es gibt drei Arten von MFC-Informationen ein: Modulstatus, Status und Zustand des Threads. In einigen Fällen können diese Zustandstypen kombiniert werden. MFC Handlezuordnungen sind beispielsweise sowohl lokale-Modul und Thread-lokalen. Dadurch können zwei verschiedene Module zu unterschiedliche Zuordnungen in jeder ihre Threads zu erhalten.

Prozessstatus und Zustand des Threads sind ähnlich. Diese Datenelemente Dinge, die seit jeher globale Variablen, jedoch werden für einen bestimmten Prozess oder thread für die ordnungsgemäße Win32s unterstützen oder für die ordnungsgemäße Multithreadingunterstützung befinden muss. Die Kategorie, die ein angegebenes Datenelement in passt hängt davon ab, das Element und die gewünschte Semantik in Bezug auf die Grenzen von Prozessen und Threads.

Modulstatus ist einzigartig, da es entweder globale Status oder Zustand lokalen Prozesses oder Threads, die lokalen enthalten kann. Darüber hinaus können sie schnell gewechselt werden.

## <a name="module-state-switching"></a>Modulstatus wechseln

Jeder Thread enthält einen Zeiger auf den Zustand "current" oder "aktiv" (überrascht nicht, dass der Zeiger ist Teil der MFC Thread-lokalen Zustand ist). This-Zeiger wird geändert, wenn der Thread der Ausführung eine Modul-Grenze, z. B. eine Anwendung in ein OLE-Steuerelement oder DLL oder ein OLE-Steuerelements Rückrufe in eine Anwendung aufrufen übergibt.

Der aktuellen Zustand wird durch Aufrufen von gewechselt `AfxSetModuleState`. Zum größten Teil, werden Sie niemals direkt mit der API arbeiten. MFC in vielen Fällen nenne Sie (unter WinMain, OLE-Einstiegspunkten `AfxWndProc`usw..). Dies erfolgt in eine Komponente, die Sie schreiben, indem Sie das statische verknüpfen in einem speziellen `WndProc`, und eine spezielle `WinMain` (oder `DllMain`), die weiß, welche Modulstatus aktuellen werden soll. Sie können diesen Code anzeigen, indem Sie DLLMODUL ansehen. CPP oder APPMODUL. CPP im Verzeichnis MFC\SRC.

Es ist selten, dass Sie verwenden möchten, legen Sie den Modulstatus und nicht erneut festgelegt. In den meisten Fällen zu "Ihr eigenes Modul push" wie der aktuelle Zustand, und klicken Sie dann, wenn Sie fertig sind, "pop" des ursprünglichen Kontexts zurück. Dies erfolgt durch das Makro [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) und die spezielle Klasse `AFX_MAINTAIN_STATE`.

`CCmdTarget` verfügt über spezielle Features zur Unterstützung von Modul Status wechseln. Insbesondere eine `CCmdTarget` verwenden, wird die Stammklasse für die OLE-Automatisierung und OLE-COM-Einstiegspunkte an. Wie jedem anderen Einstiegspunkt für das System verfügbar gemacht, müssen diese Einstiegspunkte den richtigen Zustand festgelegt. Wie wird eine bestimmte `CCmdTarget` wissen, was der Zustand "richtig" sollte die Antwort ist, dass es "speichert", was der Zustand "current" ist, wenn er erstellt wird, so, dass sie festlegen, kann der aktuellen Modulstatus, "gespeichert" wird aufgerufen, Wert, wenn sie weiter unten. Daher das Modul angeben, die einen bestimmten `CCmdTarget` -Objekt zugeordnet ist mit ist der Modulzustand, der aktuell war, als das Objekt erstellt wurde. Nehmen Sie ein einfaches Beispiel für einen in-Process-Server zu laden, erstellen ein Objekt und seine Methoden aufrufen.

1. Die DLL wird geladen von OLE mit `LoadLibrary`.

2. `RawDllMain` wird zuerst aufgerufen. Der Status des Moduls festgelegt für die DLL auf den bekannten statischen Zustand. Aus diesem Grund `RawDllMain` statisch mit der DLL verknüpft ist.

1. Der Konstruktor für die Klassenfactory, die das Objekt zugeordnet wird aufgerufen. `COleObjectFactory` stammt aus `CCmdTarget` und daher speichert es in welchem Modulzustand es instanziiert wurde. Dies ist wichtig, wenn die Klassenfactory aufgefordert wird, um Objekte zu erstellen, er weiß jetzt, welche Modulstatus zum aktuellen werden soll.

4. `DllGetClassObject` wird aufgerufen, um die Klassenfactory zu erhalten. MFC sucht die Liste der Factory diesem Modul zugeordnet, und gibt ihn zurück.

5. `COleObjectFactory::XClassFactory2::CreateInstance` wird aufgerufen. Vor dem Erstellen des Objekts, und dieser zurückgegeben wird, setzt diese Funktion den Zustand, den Zustand, der in Schritt 3 war (diejenige, die aktuellen wurde die `COleObjectFactory` instanziiert wurde). Dies geschieht innerhalb des [METHOD_PROLOGUE](com-interface-entry-points.md).

1. Wenn das Objekt erstellt wird, ist eine `CCmdTarget` Ableitung und auf die gleiche Weise `COleObjectFactory` gespeichert, welche Modulstatus aktiv ist, wurde Gleiches gilt für dieses neue Objekt. Nachdem das Objekt, welche Modulstatus weiß, wechseln Sie zu jedes Mal, wenn sie aufgerufen wird.

1. Der Client Ruft eine Funktion für das OLE-COM-Objekt, das sie über empfangen dessen `CoCreateInstance` aufrufen. Wenn das Objekt aufgerufen wird, die sie verwendet `METHOD_PROLOGUE` So wechseln Sie den Zustand wie `COleObjectFactory` ist.

Wie Sie sehen können, wird der Status des Moduls aus Objekt Objekt weitergegeben während der Erstellung. Es ist wichtig, den Zustand wie gewünscht festgelegt haben. Wenn sie nicht festgelegt ist, kann Ihr DLL- oder COM-Objekt schlecht mit einer MFC-Anwendung interagieren, die aufruft, möglicherweise nicht um einen eigenen Ressourcen zu suchen oder auf andere Weise ärgerliche möglicherweise hat.

Beachten Sie, dass bestimmte Arten von DLLs, insbesondere "MFC Extension" DLLs nicht in den Zustand wechselt ihrer `RawDllMain` (tatsächlich in der Regel nicht selbst haben ein `RawDllMain`). Dies ist, da sie verhalten sich "als wären" tatsächlich vorhanden ist, in der Anwendung, die sie verwendet werden sollen. Sie sind sehr viel einen Teil der Anwendung, die ausgeführt wird, und es ist ihre Wahl zum Ändern des globalen Status der Anwendung.

OLE-Steuerelemente und anderen DLLs sind sehr unterschiedlich. Sie sollen nicht die aufrufende Anwendung Status zu ändern. die Anwendung, die sie aufrufen, wird möglicherweise auch keiner MFC-Anwendung, und daher möglicherweise keinen Zustand ändern. Dies ist der Grund für das Modul Zustand wechseln erfunden wurde.

Für exportierte Funktionen aus einer DLL, z. B. ein, die ein Dialogfeld, in der DLL, gestartet wird, müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

Dies tauscht den aktuellen Modulstatus mit dem Status von zurückgegebenen [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.

Probleme mit Ressourcen in DLLs treten auf, wenn das AFX_MODULE_STATE-Makro nicht verwendet wird. Standardmäßig verwendet MFC Ressourcenhandle von der hauptanwendung beim Laden der Ressourcenvorlage an. Mit dieser Vorlage wird in der DLL tatsächlich gespeichert. Die Ursache ist, dass MFC modulstatusinformationen nicht durch das Makro AFX_MODULE_STATE gewechselt wurde. Das Ressourcenhandle wird von MFCs-Modulstatus wiederhergestellt. Wechseln nicht den Zustand bewirkt, dass das Handle falsche Ressource verwendet werden.

AFX_MODULE_STATE muss nicht in jeder Funktion in der DLL eingefügt werden. Z. B. `InitInstance` kann von den MFC-Code in der Anwendung ohne AFX_MODULE_STATE aufgerufen werden, da MFC automatisch den Zustand vor dem verschiebt `InitInstance` und klicken Sie dann die Switches, die sie wieder nach `InitInstance` zurückgibt. Dasselbe gilt für alle Map-Meldungshandler. Reguläre MFC-DLLs haben eine besondere master Fensterprozedur, die den Zustand automatisch wechselt vor dem Weiterleiten einer Nachricht.

## <a name="process-local-data"></a>Verarbeiten von lokalen Daten

Verarbeiten von lokale Daten wäre es nicht die schwierigkeiten bei der Win32s DLL-Modell wurde nicht von solchen großer Wichtigkeit. In Win32s alle DLLs, die ihre globale Daten freigeben, selbst wenn von mehreren Anwendungen geladen. Dies unterscheidet sich von "echten" Win32-DLL Datenmodell, in dem jede DLL-Datei für eine separate Kopie des Datenspeicherplatzes in den einzelnen Prozessen abruft, die an die DLL angefügt wird. Um die Komplexität hinzuzufügen, ist Daten, die auf dem Heap in einer DLL Win32s tatsächlich bestimmten Prozess (zumindest im Laufe der Besitz). Beachten Sie folgende Daten und Code aus:

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

Bedenken Sie, was geschieht, und wenn der obige Code in einer DLL in gespeichert ist, dass die DLL geladen wird, durch zwei Verfahren A und B (sie könnten tatsächlich zwei Instanzen derselben Anwendung sein). Eine Aufrufe `SetGlobalString("Hello from A")`. Daher ist zugewiesene Speicher die `CString` Daten im Kontext des Prozesses A. Bedenken Beachten Sie, dass die `CString` selbst ist global und für beide ein sichtbar ist und b Jetzt B ruft `GetGlobalString(sz, sizeof(sz))`. B werden können, um die Daten anzuzeigen, die eine Gruppe. Dies ist da Win32s keinen Schutz zwischen Prozessen bietet wie Win32. Das ist das erste Problem. in vielen Fällen ist es nicht wünschenswert, dass sich eine Anwendung, die globale Daten beeinflussen, die zu einer anderen Anwendung gehört angesehen werden.

Es gibt auch zusätzliche Probleme verursachen. Nehmen wir an, dass nun beendet wurde. Wenn ein beendet wird, den Speicher ein, die die "`strGlobal`' Zeichenfolge für das System zur Verfügung gestellt wird –, also alle vom Prozess A reservierte Speicher automatisch durch das Betriebssystem freigegeben ist. Es ist nicht freigegeben, da die `CString` Destruktor aufgerufen wird; es wurde nicht aufgerufen wurde. Es wird einfach freigegeben, da die Anwendung, die ihr zugeordnete die Szene verlassen hat. Nun, wenn B aufgerufen `GetGlobalString(sz, sizeof(sz))`, gültige Daten können nicht abgerufen. Eine anderen Anwendung möglicherweise, dass der Arbeitsspeicher für andere Zwecke verwendet.

Natürlich gibt es ein Problem. MFC 3.x verwendet eine Technik namens lokalen Threadspeicher (TLS). MFC 3.x würde einen TLS-Index, der unter Win32s als Prozess lokaler Threadspeicher Index dient, zuordnen, obwohl sie nicht, die aufgerufen wird, und dann auf alle Daten, die basierend auf diesen TLS-Index verweisen würden. Dies ist vergleichbar mit der TLS-Index, der zum Speichern von threadlokalen Daten auf Win32 verwendet wurde (siehe unten für Weitere Informationen zu diesem Thema). Dies verursacht jedes MFC-DLL in mindestens zwei TLS-Indizes pro Prozess zu verwenden. Wenn Sie zum Laden von vielen OLE-Steuerelement-DLLs (OCX) zu berücksichtigen, führen Sie schnell aus TLS-Indizes (Es stehen nur für 64). Darüber hinaus musste MFC alle diese Daten an einem Ort, in eine einzelne Struktur platzieren. Es war nicht allzu erweiterbar und war nicht ideal in Bezug auf die Verwendung von TLS-Indizes.

MFC 4.x dieses Problem löst, mit einem Satz von Klassenvorlagen, können Sie "umschließen" rund um die Daten, die lokalen Prozess werden soll. Das oben beschriebene Problem könnte z. B. durch das Schreiben von behoben werden:

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC implementiert dies in zwei Schritten. Eine Möglichkeit ist eine Schicht über die Win32 __Tls\*__  APIs (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**usw.) dem Verwenden Sie nur zwei TLS-Indizes pro Prozess, unabhängig davon, wie viele DLLs haben. Zweitens wird die `CProcessLocal` Vorlage wird bereitgestellt, um diese Daten zugreifen. Es überschreibt die Operator -> Dies ist die intuitivste Syntax ermöglicht oben angezeigt. Alle Objekte, die von umschlossen werden `CProcessLocal` abgeleitet werden, von `CNoTrackObject`. `CNoTrackObject` Stellt eine Low-Level-Zuweisung (**LocalAlloc**/**LocalFree**) und einen virtuellen Destruktor, MFC, wenn der Prozess beendet wird automatisch in die lokale Prozessobjekte beschädigt werden kann. Solche Objekte haben einen benutzerdefinierten Destruktor auf, wenn zusätzliche Bereinigung erforderlich ist. Im Beispiel oben, erfordern nicht, da es sich bei generiert der Compiler eine Standarddestruktor, um das eingebettete zerstören `CString` Objekt.

Es gibt andere interessante Vorteile dieses Ansatzes. Sie sind nicht nur alle `CProcessLocal` Objekte automatisch zerstört, sie nicht erstellt werden, bis sie benötigt werden. `CProcessLocal::operator->` das zugeordnete Objekt der ersten, die sie aufgerufen wird und keine früher instanziiert. Im obigen Beispiel, das bedeutet, dass die "`strGlobal`' Zeichenfolge wird nicht erstellt werden, bis zum ersten Mal `SetGlobalString` oder `GetGlobalString` aufgerufen wird. In einigen Fällen können diese DLL-Startzeit zu verringern.

## <a name="thread-local-data"></a>Thread-lokalen Daten

Ähnlich wie bei lokale Daten zu verarbeiten, threadlokale Daten dient, wenn die Daten lokal in einem bestimmten Thread werden müssen. Das heißt, benötigen Sie eine separate Instanz der Daten für jeden Thread, der die Daten zugreift. Dies kann oft durch umfangreiche Synchronisierungsmechanismen verwendet werden. Wenn die Daten nicht von mehreren Threads gemeinsam verwendet werden müssen, können dieser Mechanismen teuer und nicht erforderlich sein. Angenommen, wir hatten eine `CString` Objekt (ähnlich wie im obigen Beispiel). Wir können erleichtern thread-lokalen durch Umschließen mit einem `CThreadLocal` Vorlage:

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

Wenn `MakeRandomString` aufgerufen wurde von zwei verschiedenen Threads, jede würde "shuffle" die Zeichenfolge auf unterschiedliche Weise ohne Konflikte mit anderen. Dies ist, da man `strThread` Instanz pro Thread und nicht nur eine globale Instanz.

Beachten Sie, wie ein Verweis verwendet wird, zum Erfassen der `CString` Adresse einmal statt einmal pro Schleifeniteration. Der Code der Schleife ließe mit `threadData->strThread` überall "`str`" verwendet wird, aber der Code wäre sehr viel langsamer ausgeführt. Es wird empfohlen, einen Verweis auf die Daten zwischenzuspeichern, wenn solche Verweise in Schleifen auftreten.

Die `CThreadLocal` -Klassenvorlage verwendet die gleichen Mechanismen, die `CProcessLocal` verfügt und die gleichen implementierungstechniken.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
