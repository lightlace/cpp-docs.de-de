---
title: 'TN011: Verwenden von MFC als Teil einer DLL'
ms.date: 11/04/2016
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
ms.openlocfilehash: 753612fae101708dd4f8294db121980b62af30b3
ms.sourcegitcommit: 934cb53fa4cb59fea611bfeb9db110d8d6f7d165
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65610948"
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Verwenden von MFC als Teil einer DLL

Dieser Hinweis beschreibt reguläre MFC-DLLs, die Ihnen ermöglichen, die MFC-Bibliothek als Teil einer Windows-Dynamic Link Library (DLL) zu verwenden. Es wird davon ausgegangen, dass Sie mit Windows-DLLs und erstellen sie vertraut sind. Informationen zu MFC-Erweiterungs-DLLs, mit dem Sie erstellen können Erweiterungen für die MFC-Bibliothek finden Sie unter [DLL-Version von MFC](../mfc/tn033-dll-version-of-mfc.md).

## <a name="dll-interfaces"></a>DLL-Schnittstellen

reguläre MFC-DLLs wird davon ausgegangen, Schnittstellen zwischen der Anwendung und die DLL im C-ähnlichen Funktionen oder explizit exportierten Klassen angegeben sind. Schnittstellen von MFC-Klasse können nicht exportiert werden.

Wenn sowohl eine DLL-Datei und einer Anwendung MFC verwenden möchten, können beide entweder für die freigegebene Version von MFC-Bibliotheken verwenden oder auf eine Kopie der Bibliotheken statisch zu verknüpfen. Die Anwendung und die DLL kann sowohl eine der standard-Versionen der MFC-Bibliothek verwenden.

reguläre MFC-DLLs haben mehrere Vorteile:

- Die Anwendung, die die DLL verwendet, muss nicht MFC verwendet und muss keine werden von Visual C++-Anwendung.

- Mit regulären MFC-DLLs, die statisch mit MFC verknüpft sind, hängt von die Größe der DLL nur die MFC- und C-Laufzeitroutinen, die verwendet und verknüpft sind.

- In regulären MFC DLL-Dateien, die dynamisch mit MFC verknüpft, können die einsparungen im Arbeitsspeicher verwenden Sie die freigegebene Version von MFC erheblich sein. Allerdings müssen Sie verteilen, die gemeinsam genutzte DLLs, Mfc\<*Version*> .dll und Msvvcrt\<*Version*> .dll, zusammen mit der DLL.

- Der DLL-Entwurf ist unabhängig von der Implementierung von Klassen. Ihr Design DLL exportiert nur für die APIs werden sollen. Wenn die Implementierung geändert wird, sind reguläre MFC-DLLs daher weiterhin gültig.

- In regulären MFC DLL-Dateien, die statisch mit MFC verknüpft, wenn sowohl die DLL als auch die Anwendung MFC verwenden, stehen Ihnen keine Probleme mit der Anwendung, die eine andere Version von MFC als DLL oder umgekehrt werden sollen. Da die MFC-Bibliothek in jede DLL oder EXE-Datei statisch verknüpft ist, ist keine Frage, welche Version Sie haben.

## <a name="api-limitations"></a>API-Einschränkungen

MFC-Funktionen wird nicht für die DLL-Version, entweder aufgrund technischer Einschränkungen oder weil diese Dienste in der Regel von der Anwendung bereitgestellt werden. Die aktuelle Version von MFC ist die einzige Funktion, die nicht anwendbar ist `CWinApp::SetDialogBkColor`.

## <a name="building-your-dll"></a>Erstellen der DLL

Beim Kompilieren von regulären MFC-DLLs, die statisch mit MFC, die Symbole `_USRDLL` und `_WINDLL` muss definiert werden. Ihre DLL-Code muss auch mit den folgenden Compilerschaltern kompiliert werden:

- **/ D_WINDLL** gibt an, dass die Kompilierung für eine DLL

- **/ D_USRDLL** gibt an, Sie erstellen eine reguläre MFC-DLL

Sie müssen auch diese Symbole zu definieren und diese Compilerschalter beim Kompilieren von regulären MFC-DLLs, die dynamisch mit MFC verknüpft. Darüber hinaus das Symbol `_AFXDLL` muss definiert werden und Ihren DLL-Code muss mit kompiliert werden:

- **/ D_AFXDLL** gibt an, dass Sie eine reguläre MFC-DLL erstellen, die dynamisch mit MFC verknüpft

Die Schnittstellen (APIs) zwischen der Anwendung und die DLL müssen explizit exportiert werden. Es wird empfohlen, dass Sie Ihre Schnittstellen mit geringer Bandbreite werden definieren, und nur C-Schnittstellen verwenden, sofern möglich. Direkte C-Schnittstellen sind einfacher zu verwalten als eine komplexere C++-Klassen.

Platzieren Sie Ihre APIs in einem separaten-Header, der von C- und C++-Dateien enthalten sein kann. Finden Sie unter den Header ScreenCap.h im MFC Advanced Concepts-Beispiel [DLLScreenCap](../overview/visual-cpp-samples.md) verdeutlicht. Um Ihre Funktionen zu exportieren, geben Sie in der `EXPORTS` Teil Ihrer Moduldefinitionsdatei (. DEF) oder `__declspec(dllexport)` auf Ihre Funktionsdefinitionen. Verwendung `__declspec(dllimport)` um diese Funktionen in die ausführbare Clientdatei zu importieren.

Sie müssen am Anfang die exportierten Funktionen in regulären MFC-DLLs, die dynamisch mit MFC verknüpft, das AFX_MANAGE_STATE-Makro hinzufügen. Dieses Makro legt den aktuellen Modulstatus, die für die DLL an. Um dieses Makro zu verwenden, fügen Sie die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen aus:

`AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`

## <a name="winmain---dllmain"></a>WinMain-DllMain >.

Die MFC-Bibliothek definiert die standard-Win32 `DllMain` Einstiegspunkt, der initialisiert Ihre [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitetes Objekt wie eine typische MFC-Anwendung. Platzieren Sie alle DLL-spezifische-Initialisierung in der [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) Methode, wie eine typische MFC-Anwendung.

Beachten Sie, dass die [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run) Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn die DLL nicht modale Dialogfelder angezeigt oder ein Hauptrahmenfenster eigene, Haupt-Meldungsverteilschleife Ihrer Anwendung muss eine DLL exportierte Routine aufrufen, die Aufrufe [PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage).

Siehe Beispiel DLLScreenCap für die Verwendung dieser Funktion.

Die `DllMain` -Funktion, die MFC enthält, ruft der [CWinApp:: ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) Methode der Klasse, die von abgeleitet ist `CWinApp` , bevor die DLL entladen wird.

## <a name="linking-your-dll"></a>Verknüpfen einer DLL

Mit regulären MFC-DLLs, die statisch mit MFC verknüpfen, müssen Sie die DLL mit Nafxcwd.lib oder Nafxcw.lib und mit der Version der C-Laufzeiten, die mit dem Namen "LIBCMT.lib" verknüpfen. Diese Bibliotheken sind vorkonfigurierte und können installiert werden, indem Sie sie beim Ausführen des Visual C++-Setups angeben.

## <a name="sample-code"></a>Beispielcode

Finden Sie im MFC Advanced Concepts-Beispiel, das Programm DLLScreenCap ein vollständiges Beispiel aus. Beachten Sie in diesem Beispiel werden mehrere interessante Dinge lauten wie folgt aus:

- Die Compilerflags, der die DLL und die von der Anwendung sind unterschiedlich.

- Die Zeilen der Verknüpfung und. DEF-Dateien für die DLL und die für die Anwendung sind unterschiedlich.

- Die Anwendung, die die DLL verwendet, muss nicht in C++ werden.

- Die Schnittstelle zwischen der Anwendung und die DLL ist eine API, die von C oder C++ verwendet werden kann und exportiert wird, wird mit DLLScreenCap.def.

Das folgende Beispiel veranschaulicht eine API, die in einem regulären MFC-DLL definiert, die statisch mit MFC verknüpft wird. In diesem Beispiel steht in die Deklaration einer `extern "C" { }` Block für C++-Benutzer. Dies hat mehrere Vorteile. Zunächst können sie Ihre DLL-APIs verwendet werden von nicht-c++-Client-Anwendungen. Zweitens wird verringert, DLL-Mehraufwand, da C++ die namenszerlegung nicht in den exportierten Namen angewendet wird. Schließlich vereinfacht explizit hinzugefügt ein. DEF-Datei (für das Exportieren nach Ordnungszahl) ohne die namenszerlegung kümmern.

```
#ifdef __cplusplus
extern "C" {
#endif  /* __cplusplus */

struct TracerData
{
    BOOL bEnabled;
    UINT flags;
};

BOOL PromptTraceFlags(TracerData FAR* lpData);

#ifdef __cplusplus
}
#endif
```

Die von der API verwendeten Strukturen nicht von MFC-Klassen abgeleitet werden und in der API-Header definiert sind. Dies reduziert die Komplexität der Schnittstelle zwischen der DLL und der Anwendung und die DLL von C-Programmen verwendet werden kann.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)
