---
title: Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs
ms.date: 11/04/2016
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
ms.openlocfilehash: d08822a04abe5a01883ad8aa1bd6d94269e810cc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314688"
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs

Beim eine MFC-Erweiterungs-DLL aus einer regulären MFC-DLL zu verwenden, wenn die MFC-Erweiterungs-DLL nicht in einer drahtgebundenen der **CDynLinkLibrary** Kette Objekt von der regulären MFC DLL, die Sie in mindestens einer Gruppe von verwandten Problemen ausführen können. Da die Debugversionen der MFC-Datenbank-, OLE- und Sockets unterstützt DLLs werden als MFC-Erweiterungs-DLLs implementiert, werden möglicherweise angezeigt verfügt über ähnliche Probleme, wenn Sie diese MFC verwenden, auch wenn Sie nicht explizit eine eigene MFC-Erweiterungs-DLLs verwenden werden. Einige Symptome sind:

- Wenn in der MFC-Erweiterungs-DLL, die Nachricht definiert ein Objekt eines Typs der Klasse zu deserialisieren versucht, "Warnung: CYourClass kann nicht aus dem Archiv geladen werden. Klasse nicht definiert". wird im Debugfenster ABLAUFVERFOLGUNG und das Objekt kann nicht serialisiert.

- Eine Ausnahme, die ungültige Klasse kann ausgelöst werden.

- Ressourcen in die MFC-Erweiterungs-DLL nicht laden, da `AfxFindResourceHandle` gibt **NULL** oder eine falsche Ressource-Handle.

- `DllGetClassObject`, `DllCanUnloadNow`, und die `UpdateRegistry`, `Revoke`, `RevokeAll`, und `RegisterAll` Memberfunktionen der `COleObjectFactory` Fehler beim Suchen einer Klassenfactory, die in der MFC-Erweiterungs-DLL definiert.

- `AfxDoForAllClasses` funktioniert nicht für alle Klassen in der MFC-Erweiterungs-DLL.

- MFC-Standarddatenbank, Sockets oder OLE-Ressourcen, die das Laden fehl. Z. B. **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) eine leere Zeichenfolge zurückgegeben, wenn die regulären MFC-DLL ordnungsgemäß die MFC-Datenbankklassen verwendet werden.

Die Lösung dieser Probleme wird zum Erstellen und Exportieren eine Initialisierungsfunktion in der MFC-Erweiterungs-DLL, erstellt eine **CDynLinkLibrary** Objekt. Rufen Sie diese Initialisierungsfunktion, genau einmal aus jeder regulären MFC-DLL, die die MFC-Erweiterungs-DLL verwendet.

## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC OLE, MFC-Datenbank (oder DAO) oder Sockets MFC-Unterstützung

Wenn Sie alle MFC-OLE, MFC-Datenbank (oder DAO) verwenden oder MFC-Sockets in der regulären MFC-DLL unterstützen, sind die MFC-Debugbuilds MFC-Erweiterungs-DLLs MFCOxxD.dll MFCDxxD.dll und MFCNxxD.dll (wobei Xx die Versionsnummer ist) automatisch verknüpft. Sie müssen für jede dieser DLLs, die Sie verwenden, eine vordefinierte Initialisierungsfunktion aufrufen.

Fügen Sie für die datenbankunterstützung, die einen Aufruf von `AfxDbInitModule` zu Ihrem regulären MFC DLL des `CWinApp::InitInstance` Funktion. Stellen Sie sicher, dass dieser Aufruf erfolgt vor dem Aufruf Basisklasse oder einem der hinzugefügten Code, der die MFCDxxD.dll zugreift. Diese Funktion akzeptiert keine Parameter und gibt "void" zurück.

Fügen Sie einen Aufruf von für OLE-Unterstützung `AfxOleInitModule` zu Ihrem regulären MFC DLL des `CWinApp::InitInstance`. Beachten Sie, dass die **COleControlModule InitInstance** Funktionsaufrufe `AfxOleInitModule` bereits, wenn Sie ein OLE-Steuerelement erstellen und verwenden daher `COleControlModule`, sollten Sie diesen Aufruf nicht hinzufügen `AfxOleInitModule`.

Für die Unterstützung für Sockets, fügen Sie einen Aufruf von `AfxNetInitModule` zu Ihrem regulären MFC DLL des `CWinApp::InitInstance`.

Beachten Sie, dass von von MFC-DLLs Releasebuilds und Anwendungen Sie keine separate DLLs für die Datenbank, Sockets verwenden, oder OLE-Unterstützung. Allerdings ist es sicher ist, rufen diese Initialisierungsfunktionen im Releasemodus.

## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary-Objekten

Während jeder der Vorgänge am Anfang dieses Themas erwähnt muss MFC nach einem gewünschten Wert oder Objekt zu suchen. Beispielsweise muss während der Deserialisierung MFC alle derzeit verfügbaren Runtime-Klassen entsprechend der Objekte in das Archiv mit ihren entsprechenden Laufzeitklasse durchsuchen.

Im Rahmen diese Suchvorgänge, MFC durchsucht alle die MFC-Erweiterungs-DLLs verwendet Schritt für Schritt eine Kette von **CDynLinkLibrary** Objekte. **CDynLinkLibrary** Objekte automatisch zu einer Kette während deren Erstellung Anfügen und die Erstellung erfolgt jedes MFC-Erweiterungs-DLL im Gegenzug während der Initialisierung. Darüber hinaus weist jedem Modul (Anwendung oder regulären MFC-DLL) seine eigenen Kette von **CDynLinkLibrary** Objekte.

Für eine MFC-Erweiterungs-DLL in wired erhalten eine **CDynLinkLibrary** Kette, müssen sie erstellen eine **CDynLinkLibrary** Objekt im Kontext von jedem Modul, das die MFC-Erweiterungs-DLL verwendet. Aus diesem Grund, wenn eine MFC-Erweiterungs-DLL vor sich geht aus den regulären MFC-DLLs verwendet werden, er muss bereitstellen eine exportierten Initialisierungsfunktion, die erstellt eine **CDynLinkLibrary** Objekt. Alle regulären MFC-DLL mit der MFC-Erweiterung muss DLL exportierten Initialisierungsfunktion aufrufen.

Wenn eine MFC-Erweiterungs-DLL geht von einer MFC-Anwendung (.exe) und nie von einer regulären MFC DLL verwendet werden, genügt es, erstellen Sie die **CDynLinkLibrary** Objekt in der MFC-Erweiterungs-DLL des `DllMain`. Dies ist die Funktionsweise der MFC-DLL-Assistenten MFC-Erweiterungs-DLL-Code. Beim Laden einer MFC-Erweiterungs-DLL implizit `DllMain` lädt und ausführt, bevor die Anwendung jemals gestartet wird. Alle **CDynLinkLibrary** Erstellungen werden in eine verkabelte, die die MFC-DLL für eine MFC-Anwendung reserviert.

Beachten Sie, dass es keine gute Idee, mehrere **CDynLinkLibrary** Objekte aus einer MFC-Erweiterungs-DLL in einer eine Kette, insbesondere dann, wenn die MFC-Erweiterungs-DLL dynamisch aus dem Arbeitsspeicher entladen werden. Rufen Sie die Initialisierungsfunktion nicht mehr als einmal von jedem beliebigen Modul ein.

## <a name="sample-code"></a>Beispielcode

Dieser Beispielcode wird davon ausgegangen, dass die regulären MFC-DLL implizit mit der MFC-Erweiterungs-DLL verknüpft. Dies wird erreicht, indem Sie mit der Importbibliothek (.lib) von der MFC-Erweiterungs-DLL verknüpfen, beim Erstellen der regulären MFC-DLL.

Die folgenden Zeilen sollten in der Quelle der MFC-Erweiterungs-DLL sein:

```
// YourExtDLL.cpp:

// standard MFC extension DLL routines
#include "afxdllx.h"

static AFX_EXTENSION_MODULE NEAR extensionDLL = { NULL, NULL };

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)
{
    if (dwReason == DLL_PROCESS_ATTACH)
    {
        // MFC extension DLL one-time initialization
        if (!AfxInitExtensionModule(extensionDLL, hInstance))
           return 0;
    }
    return 1;   // ok
}

// Exported DLL initialization is run in context of
// application or regular MFC DLL
extern "C" void WINAPI InitYourExtDLL()
{
    // create a new CDynLinkLibrary for this app
    new CDynLinkLibrary(extensionDLL);

    // add other initialization here
}
```

Achten Sie darauf, dass Sie zum Exportieren der **InitYourExtDLL** Funktion. Dies kann mit **__declspec(dllexport)** oder in der DLLs DEF-Datei wie folgt:

```
// YourExtDLL.Def:
LIBRARY      YOUREXTDLL
CODE         PRELOAD MOVEABLE DISCARDABLE
DATA         PRELOAD SINGLE
EXPORTS
    InitYourExtDLL
```

Fügen Sie einen Aufruf an die `InitInstance` Mitglied der `CWinApp`-abgeleitete Objekt in jeder regulären MFC-DLL, die mit der MFC-Erweiterungs-DLL:

```
// YourRegularDLL.cpp:

class CYourRegularDLL : public CWinApp
{
public:
    virtual BOOL InitInstance(); // Initialization
    virtual int ExitInstance();  // Termination

    // nothing special for the constructor
    CYourRegularDLL(LPCTSTR pszAppName) : CWinApp(pszAppName) { }
};

BOOL CYourRegularDLL::InitInstance()
{
    // any DLL initialization goes here
    TRACE0("YOUR regular MFC DLL initializing\n");

    // wire any MFC extension DLLs into CDynLinkLibrary chain
    InitYourExtDLL();

    return TRUE;
}
```

### <a name="what-do-you-want-to-do"></a>Wie möchten Sie vorgehen?

- [MFC-Erweiterungs-DLLs initialisieren](run-time-library-behavior.md#initializing-extension-dlls)

- [Reguläre MFC-DLLs initialisieren](run-time-library-behavior.md#initializing-regular-dlls)

### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?

- [MFC extension DLLs (MFC-Erweiterungs-DLLs)](extension-dlls.md)

- [Regular MFC DLLs Statically Linked to MFC (Reguläre, statisch mit MFC verknüpfte MFC-DLLs)](regular-dlls-statically-linked-to-mfc.md)

- [Regular MFC DLLs Dynamically Linked to MFC (Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs)](regular-dlls-dynamically-linked-to-mfc.md)

- [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)

- [DLL-Version von MFC](../mfc/tn033-dll-version-of-mfc.md)

## <a name="see-also"></a>Siehe auch

[MFC extension DLLs (MFC-Erweiterungs-DLLs)](extension-dlls.md)
