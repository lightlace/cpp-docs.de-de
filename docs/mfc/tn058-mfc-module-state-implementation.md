---
title: 'TN058: MFC-Modulzustandsimplementierung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.mfc.implementation
dev_langs:
- C++
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90e407299f67922aa855a51b9983af074cdbd4fc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33385751"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058: MFC-Modulzustandsimplementierung
> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.  
  
 In diesem technischen Hinweis beschreibt die Implementierung von MFC-"Modulstatus" Konstrukte. Ein Überblick über die Status-modulimplementierung ist wichtig für gemeinsam DLLs aus einer DLL verwenden die MFC-Bibliothek genutzte (oder in-Process-OLE-Server).  
  
 Vor dem Lesen dieses Hinweis, finden Sie unter "Verwalten der Statusdaten von MFC-Modulen" im [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md). Dieser Artikel enthält wichtige Informationen und allgemeine Informationen zu diesem Thema.  
  
## <a name="overview"></a>Übersicht  
 Es gibt drei Arten von Statusinformationen MFC: Modulstatus Prozessstatus und Zustand des Threads. In einigen Fällen können dieser Zustand Typen kombiniert werden. Beispielsweise sind die MFC Handlezuordnungen lokalen Modul und Thread-lokalen. Dadurch werden zwei unterschiedliche Module unterschiedliche Karten in jedem ihrer Threads benötigt.  
  
 Prozessstatus und Threadzustand sind ähnlich. Diese Datenelemente Dinge, die seit jeher globale Variablen, jedoch spezifisch für einen bestimmten Prozess oder thread für ordnungsgemäße Win32s unterstützen oder für ordnungsgemäße Multithreadingunterstützung haben müssen. Welche Kategorie stimmt mit einem bestimmten Datenelement hängt davon ab, das Element und die gewünschte Semantik im Hinblick auf die Grenzen von Prozessen und Threads.  
  
 Modulstatus ist eindeutig, insofern, dass globale Zustand oder Status, der lokalen Prozess oder Thread-lokalen enthalten können. Darüber hinaus können sie schnell umgeschaltet werden.  
  
## <a name="module-state-switching"></a>Modulstatus wechseln  
 Jeder Thread enthält einen Zeiger auf den Zustand "Aktuell" oder "aktiv" (nicht überraschend für der Zeiger ist Teil der MFC Thread-lokalen Zustand). This-Zeiger wird geändert, wenn der Thread der Ausführung eine Modul-Grenze, z. B. eine Anwendung, die Aufrufe in ein OLE-Steuerelement oder DLL oder ein OLE-Steuerelements Rückrufe in eine Anwendung übergeben.  
  
 Der aktuelle Status des Moduls wird durch den Aufruf gewechselt **AfxSetModuleState**. Den meisten Fällen werden Sie nie direkt mit der API verarbeiten. MFC, in vielen Fällen genannt für Sie (am WinMain OLE-Einstiegspunkte, **fxWndProc**usw..). Dies erfolgt in eine beliebige Komponente, die Sie schreiben, indem Sie das statische verknüpfen in einer speziellen **WndProc**, und eine spezielle `WinMain` (oder `DllMain`), die weiß, welche Modulstatus aktuellen werden soll. Sie können diesen Code durch einen Blick auf DLLMODUL finden Sie unter. CPP oder APPMODUL. CPP im Verzeichnis MFC\SRC.  
  
 Es ist nur in seltenen Fällen die Modulstatus festgelegt und nicht erneut festgelegt werden sollen. In den meisten Fällen zu "Eigene Modul push" Status als aktueller Planer, und klicken Sie dann, wenn Sie fertig sind, "pop" des ursprünglichen Kontexts zurück. Dies erfolgt durch das Makro [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) und die Sonderklasse **AFX_MAINTAIN_STATE**.  
  
 `CCmdTarget` verfügt über spezielle Funktionen für die Unterstützung von Modul Status wechseln. Insbesondere eine `CCmdTarget` verwenden, wird die Stammklasse für OLE-Automatisierung und COM-OLE-Einstiegspunkte. Wie alle anderen Einstiegspunkt für das System verfügbar gemacht, müssen diese Einstiegspunkte die richtige Modulstatus festgelegt. Wie wird eine bestimmte `CCmdTarget` wissen, was der "richtige" Modulstatus sollte die Antwort ist, dass "gespeichert" Was "Aktuell"-Modulstatus ist, bei der es erstellt wurde, dass sie festlegen kann der aktuellen Modulstatus mit "gespeichert" Wert, wenn sie später bezeichnet. Daher das Modul hingewiesen, dass eine bestimmte `CCmdTarget` -Objekt zugeordnet ist mit ist der Modulzustand, der beim aktuell das Objekt erstellt wurde. Nehmen Sie ein einfaches Beispiel für ein PROZESSINTERNER Server laden, erstellen ein Objekt und seine Methoden aufrufen.  
  
1.  Die DLL wird geladen, OLE mit **LoadLibrary**.  
  
2. **RawDllMain** zuerst aufgerufen. Die Modulstatus festgelegt für die DLL auf das bekannte statische Modulstatus. Aus diesem Grund **RawDllMain** statisch mit der DLL verknüpft ist.  
  
3.  Der Konstruktor für die Klassenfactory unsere Objekt zugeordnet wird aufgerufen. `COleObjectFactory` stammt aus `CCmdTarget` und daher gespeichert in welche Modulstatus es instanziiert wurde. Dies ist wichtig, wenn die Klassenfactory aufgefordert wird, um Objekte zu erstellen, weiß jetzt welche Modulstatus zum aktuellen werden soll.  
  
4. `DllGetClassObject` wird aufgerufen, um die Klassenfactory zu erhalten. MFC sucht die Factory-Klassenliste, die diesem Modul zugeordnet und gibt ihn zurück.  
  
5. **COleObjectFactory::XClassFactory2::CreateInstance** aufgerufen wird. Vor dem Erstellen des Objekts und das zurückgeben, setzt diese Funktion den Zustand auf den Zustand, der in Schritt 3 war (das Projekt, das aktuelle wurde die `COleObjectFactory` instanziiert wurde). Dies geschieht innerhalb des [METHOD_PROLOGUE](com-interface-entry-points.md).  
  
6.  Wenn das Objekt erstellt wird, wird er zu einem `CCmdTarget` Ableitung und auf die gleiche Weise `COleObjectFactory` gespeichert, welche Modulstatus aktiv ist, wurde Gleiches gilt für dieses neue Objekt. Nachdem das Objekt, welche Modulstatus weiß So wechseln Sie zu wird immer aufgerufen.  
  
7.  Der Client Ruft eine Funktion für die OLE-COM-Objekt, das vom erhalten ihre `CoCreateInstance` aufrufen. Wenn das Objekt aufgerufen wird, verwendet er `METHOD_PROLOGUE` ebenso wie die Modulstatus wechseln `COleObjectFactory` verfügt.  
  
 Wie Sie sehen können, ist die Modulstatus vom Objekt an Objekt weitergegeben, wenn sie erstellt werden. Es ist wichtig, den Modulstatus ordnungsgemäß festgelegt wurden. Falls nicht festgelegt ist, kann die DLL-Datei oder COM-Objekt schlecht mit eine MFC-Anwendung interagieren, die aufruft, möglicherweise in der Lage, ihre eigenen Ressourcen suchen oder auf andere Weise miserable fehlschlagen.  
  
 Beachten Sie, dass bestimmte Arten von DLLs, insbesondere "MFC Extension" DLLs nicht in den Zustand wechselt ihrer **RawDllMain** (tatsächlich, sie in der Regel müssen noch ein **RawDllMain**). Dies ist, da sie bestimmt sind, Verhalten "als wären" tatsächlich vorhanden ist, in der Anwendung, die sie verwendet. Sie sind sehr viel einen Teil der Anwendung, die ausgeführt wird, und es ist ihre Absicht globalen Status der Anwendung ändern.  
  
 OLE-Steuerelemente und anderen DLLs sind sehr unterschiedlich. Sie sollen nicht die aufrufende Anwendung Status zu ändern. die Anwendung, die sie aufrufen, wird möglicherweise nicht selbst eine MFC-Anwendung, und daher möglicherweise kein Zustand zu ändern. Dies ist der Grund für das Modul Status wechseln erfunden wurde.  
  
 Für exportierte Funktionen aus einer DLL, z. B. ein, die ein Dialogfeld, in der DLL gestartet wird, müssen Sie den folgenden Code am Anfang der Funktion hinzufügen:  
  
```  
AFX_MANAGE_STATE(AfxGetStaticModuleState())  
```  
  
 Dies tauscht den aktuellen Modulstatus mit dem Status Merry [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) bis zum Ende des aktuellen Gültigkeitsbereichs.  
  
 Probleme mit den Ressourcen-DLLs erfolgt, wenn die `AFX_MODULE_STATE` Makro wird nicht verwendet. Standardmäßig verwendet MFC das Ressourcenhandle von der hauptanwendung, um die Ressourcenvorlage zu laden. Diese Vorlage wird tatsächlich in der DLL gespeichert. Die Ursache ist, dass MFC Modulzustandsinformationen nicht durch gewechselt wurde die `AFX_MODULE_STATE` Makro. Das Ressourcenhandle wird vom MFC Modulstatus wiederhergestellt. Nicht durch einen Wechsel der Modulstatus wird das falsche Ressourcenhandle verwendet werden.  
  
 `AFX_MODULE_STATE` muss nicht in jeder Funktion in der DLL zu versetzen. Beispielsweise `InitInstance` kann aufgerufen werden, durch den MFC-Code in der Anwendung ohne `AFX_MODULE_STATE` Da MFC automatisch den Zustand vor dem verlagert `InitInstance` und dann wieder nach Switches `InitInstance` zurückgibt. Dasselbe gilt für alle Meldungshandler zuordnen. Reguläre MFC-DLLs haben eine spezielle master Fensterprozedur, die den Zustand automatisch wechselt vor dem Weiterleiten einer Nachricht.  
  
## <a name="process-local-data"></a>Verarbeiten von lokalen Daten  
 Verarbeiten von lokale Daten wäre es nicht für die Schwierigkeit des Modells Win32s DLL wurde nicht von solchen großer Wichtigkeit. In Win32s freigeben alle DLLs ihre globale Daten an, selbst wenn von mehreren Anwendungen geladen. Dies unterscheidet sich aus dem "real" Win32-DLL-Datenmodell, wobei jede DLL-Datei eine separate Kopie der Datenbereich in den einzelnen Prozessen abruft, die an die DLL angefügt wird. Um die Komplexität hinzugefügt haben, handelt es sich Daten, die auf dem Heap in einer DLL Win32s zugewiesen bestimmten Prozess (mindestens so weit im Laufe der Besitz). Betrachten Sie die folgenden Daten und den folgenden Code:  
  
```  
static CString strGlobal; // at file scope  
 
__declspec(dllexport)   
void SetGlobalString(LPCTSTR lpsz)  
{  
    strGlobal = lpsz;  
}  
 
__declspec(dllexport)  
void GetGlobalString(LPCTSTR lpsz,
    size_t cb)  
{  
    StringCbCopy(lpsz,
    cb,
    strGlobal);

}  
```  
  
 Erwägen Sie, was geschieht, wenn der obige Code in eine DLL befindet und dass DLL, durch zwei Prozesse A und B geladen wird (es könnten Sie tatsächlich zwei Instanzen derselben Anwendung sein). Eine Aufrufe `SetGlobalString("Hello from A")`. Folglich belegt für die `CString` Daten im Kontext des Prozesses A. Bedenken Beachten Sie, dass die `CString` selbst ist global gültig und wird angezeigt, bis beide A und b. Jetzt B ruft `GetGlobalString(sz, sizeof(sz))`. B wird in der Lage, Daten zu sehen, die eine Reihe. Dies ist da Win32s keinen Schutz zwischen Prozessen bietet wie Win32 der Fall ist. Dies ist das erste Problem; in vielen Fällen ist es nicht wünschenswert, dass eine Anwendung, die globalen Daten beeinflussen, die berücksichtigt wird, um das im Besitz einer anderen Anwendung sein.  
  
 Es gibt auch zusätzliche Probleme verursachen. Nehmen wir an, dass nun beendet. Wenn ein beendet wird, der von der belegte der "`strGlobal`" Zeichenfolge wird für das System verfügbar gemacht – d. h. alle vom Prozess ein zugeordneten Speicher wird reserviert, automatisch vom Betriebssystem. Es ist nicht freigegeben, da die `CString` Destruktor aufgerufen wird; er wurde nicht aufgerufen wurde. Wird einfach freigegeben werden kann, da die Anwendung, die er über zugeordnete die Szene verlassen hat. Wenn B aufgerufen nun `GetGlobalString(sz, sizeof(sz))`, gültigen Daten können nicht abgerufen. Eine anderen Anwendung möglicherweise, dass der Arbeitsspeicher für andere Zwecke verwendet.  
  
 Deutlich besteht ein Problem. MFC 3.x verwendet ein Verfahren namens lokalen Threadspeicher (TLS). MFC 3.x würde einen TLS-Index, der unter Win32s wirklich als Index Prozess lokaler Threadspeicher fungiert reservieren, obwohl sie nicht, die aufgerufen wird, und dann auf alle Daten, die basierend auf diesen TLS-Index verweisen würden. Dies ist vergleichbar mit der TLS-Index, der verwendet wurde, um die Thread-lokalen Datenspeicher in Win32 (siehe unten für Weitere Informationen zu diesem Thema). Dies verursacht jedes MFC-DLL für die Nutzung von mindestens zwei TLS-Indizes pro Prozess. Wenn Sie zum Laden von vielen OLE-Steuerelement-DLLs (OCX) berücksichtigen, führen Sie schnell außerhalb des TLS-Indizes (Es stehen nur 64). MFC musste außerdem gehen alle diese Daten an einem Ort, in eine einzelne Struktur platzieren. Es war nicht sehr erweiterbar und wurde nicht im Hinblick auf die Verwendung von TLS Indizes ideal.  
  
 MFC 4.x löst dieses Problem mit einem Satz von Klassenvorlagen, Sie können "umschließen" die Daten, die lokalen Prozess werden soll. Das oben beschriebene Problem kann z. B. durch das Schreiben von behoben werden:  
  
```  
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
  
 MFC implementiert diese in zwei Schritten. Zunächst wird eine Schicht über Win32 **Tls\***  APIs (**TlsAlloc**, **TlsSetValue**, **TlsGetValue**usw.) die Verwenden Sie nur zwei TLS-Indizes pro Prozess, unabhängig davon, wie viele DLLs, die Sie verfügen. Zweitens stellt die `CProcessLocal` Vorlage wird bereitgestellt, um diese Daten zugreifen. Es überschreibt die Operator -> Dies ist die intuitive Syntax ermöglicht Sie finden Sie weiter oben. Alle Objekte, die von umschlossen werden `CProcessLocal` abgeleitet werden müssen `CNoTrackObject`. `CNoTrackObject` Stellt eine Zuweisung auf niedrigerer Ebene (**LocalAlloc**/**LocalAlloc**) und einen virtuellen Destruktor, dass MFC automatisch lokalen Prozessobjekte zerstören kann, wenn der Prozess beendet wird. Solche Objekte haben einen benutzerdefinierten Destruktor, wenn zusätzliche Bereinigung erforderlich ist. Im obigen Beispiel nicht erforderlich sind, da der Compiler eine Standarddestruktor generiert, um den eingebetteten zerstören `CString` Objekt.  
  
 Es gibt andere interessante Vorteile dieses Ansatzes. Sind Sie nicht nur alle `CProcessLocal` Objekte automatisch zerstört, sie werden nicht erstellt, bis sie benötigt werden. `CProcessLocal::operator->` das zugeordnete Objekt beim ersten Aufruf und keine früher instanziiert. Im obigen Beispiel Dies bedeutet, dass der "`strGlobal`' Zeichenfolge wird nicht erstellt werden, bis zum ersten Mal **SetGlobalString** oder **GetGlobalString** aufgerufen wird. In einigen Fällen können dadurch verringern Sie die Startzeit für die DLL.  
  
## <a name="thread-local-data"></a>Lokalen Threaddaten  
 Ähnlich wie bei lokale Daten zu verarbeiten, lokalen Threaddaten dient, wenn die Daten für einen bestimmten Thread lokal sein müssen. D. h., benötigen Sie eine separate Instanz der Daten für jeden Thread, der die Daten zugreift. Dies kann mehrere Male anstelle von umfangreichen Synchronisierungsmechanismen verwendet werden. Wenn die Daten nicht von mehreren Threads gemeinsam genutzt werden müssen, können solche Mechanismen teuer und unnötige sein. Angenommen, wir haben eine `CString` Objekt (ähnlich wie im obigen Beispiel). Machen sie die thread-lokalen durch Umschließen mit einem `CThreadLocal` Vorlage:  
  
```  
struct CMyThreadData : public CNoTrackObject  
{  
    CString strThread;  
};  
CThreadLocal<CMyThreadData> threadData;  
 
void MakeRandomString()  
{ *// a kind of card shuffle (not a great one)  
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
  
 Wenn `MakeRandomString` hieß aus zwei verschiedenen Threads, jede würde "mischen" die Zeichenfolge auf unterschiedliche Weise ohne Konflikte mit anderen. Dies ist, da es ist eigentlich eine `strThread` Instanz pro Thread und nicht nur eine globale Instanz.  
  
 Beachten Sie, wie ein Verweis zur Erfassung der `CString` Adresse einmal statt einmal pro Schleifeniteration. Der Code der Schleife ließe mit `threadData->strThread` everywhere "`str`" verwendet wird, aber der Code wäre sehr viel langsamer ausgeführt. Es wird empfohlen, einen Verweis auf die Daten zwischengespeichert, wenn es sich bei Auftreten solche Verweise in Schleifen.  
  
 Die `CThreadLocal` Klassenvorlage verwendet die gleichen Mechanismen, die `CProcessLocal` verfügt und die gleichen Techniken für die Implementierung.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

