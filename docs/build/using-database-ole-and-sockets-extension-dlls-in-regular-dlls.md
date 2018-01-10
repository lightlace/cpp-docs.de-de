---
title: "Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], initializing
- DLLs [C++], extension
- DLLs [C++], regular
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0042dd5dc6049447868cf5ca5ea1112b3695f3a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="using-database-ole-and-sockets-mfc-extension-dlls-in-regular-mfc-dlls"></a>Verwenden von Datenbank-, OLE- und Sockets-MFC-Erweiterungs-DLLs in regulären MFC-DLLs
Bei eine MFC-Erweiterungs-DLL von einem regulären MFC-DLL zu verwenden, wenn die MFC-Erweiterungs-DLL nicht in einer drahtgebundenen der **CDynLinkLibrary** -Objekt Kette der regulären MFC-DLL, die Sie in mindestens einer Gruppe von verwandten Problemen ausführen können. Da die Debugversionen der MFC-Datenbank-, OLE- und Sockets unterstützt DLLs als MFC-Erweiterungs-DLLs implementiert sind, möglicherweise ähnliche Probleme bei der Verwendung dieser MFC-Funktionen, auch wenn Sie nicht explizit eine eigene MFC-Erweiterungs-DLLs verwenden. Einige Symptome sind:  
  
-   Wenn in der MFC-Erweiterungs-DLL, die Nachricht definiert versucht, ein Objekt eines Typs der Klasse zu deserialisieren "Warnung: CYourClass kann nicht geladen werden, aus dem Archiv. Klasse nicht definiert." wird ein Fehler auftritt, zu serialisieren, im Ablaufverfolgungsfenster Debug- und das Objekt angezeigt.  
  
-   Eine Ausnahme, die ungültige Klasse könnte ausgelöst werden.  
  
-   Ressourcen in MFC-Erweiterungs-DLL konnte nicht geladen werden, weil `AfxFindResourceHandle` gibt **NULL** oder eine falsche Ressourcenhandle.  
  
-   `DllGetClassObject`, `DllCanUnloadNow`, und die `UpdateRegistry`, `Revoke`, `RevokeAll`, und `RegisterAll` Memberfunktionen der `COleObjectFactory` , die eine Klassenfactory, die definiert, in der MFC-Erweiterungs-DLL zu finden.  
  
-   `AfxDoForAllClasses`funktioniert nicht für alle Klassen in MFC-Erweiterungs-DLL.  
  
-   MFC-Standarddatenbank, Sockets oder OLE-Ressourcen nicht geladen werden. Beispielsweise **AfxLoadString**(**AFX_IDP_SQL_CONNECT_FAIL**) gibt eine leere Zeichenfolge zurück, selbst wenn die regulären MFC-DLL die MFC-Datenbankklassen ordnungsgemäß verwendet wird.  
  
 Die Lösung für diese Probleme wird zum Erstellen und Exportieren eine Initialisierungsfunktion in der MFC-Erweiterungs-DLL, erstellt eine **CDynLinkLibrary** Objekt. Rufen Sie diese Initialisierungsfunktion genau einmal aus einzelnen regulären MFC-DLL, die MFC-Erweiterungs-DLL verwendet.  
  
## <a name="mfc-ole-mfc-database-or-dao-or-mfc-sockets-support"></a>MFC-OLE, MFC-Datenbank (oder DAO) oder MFC-Sockets unterstützen  
 Wenn Sie sind mit einem beliebigen MFC OLE, MFC-Datenbank (oder DAO) oder MFC-Sockets in der regulären MFC-DLL unterstützen, sind die MFC-Debugbuilds MFC-Erweiterungs-DLLs MFCOxxD.dll MFCDxxD.dll und MFCNxxD.dll (wobei Xx der Versionsnummer steht) automatisch verknüpft. Sie müssen eine vordefinierte Initialisierungsfunktion für jede dieser DLLs aufrufen, die Sie verwenden.  
  
 Fügen Sie einen Aufruf hinzu, für die datenbankunterstützung `AfxDbInitModule` zu Ihrem regulären MFC DLL `CWinApp::InitInstance` Funktion. Stellen Sie sicher, dass dieser Aufruf erfolgt vor irgendeinem Aufruf der Basisklasse oder alle hinzugefügten Code, der MFCDxxD.dll zugreift. Diese Funktion nimmt keine Parameter an und gibt "void" zurück.  
  
 Für OLE-Unterstützung, fügen Sie einen Aufruf von `AfxOleInitModule` zu Ihrem regulären MFC DLL `CWinApp::InitInstance`. Beachten Sie, dass die **COleControlModule InitInstance** Funktionsaufrufe `AfxOleInitModule` bereits, wenn Sie ein OLE-Steuerelements erstellen und verwenden `COleControlModule`, sollten Sie diesen Aufruf nicht hinzufügen `AfxOleInitModule`.  
  
 Fügen Sie einen Aufruf für Sockets-Unterstützung `AfxNetInitModule` zu Ihrem regulären MFC DLL `CWinApp::InitInstance`.  
  
 Beachten Sie, dass Releasebuilds von MFC-DLLs und Anwendungen nicht separaten DLLs für Sockets-Datenbank verwenden oder OLE unterstützen. Allerdings ist es sicher, diese Initialisierungsfunktionen im Releasemodus aufrufen.  
  
## <a name="cdynlinklibrary-objects"></a>CDynLinkLibrary-Objekte  
 Während jeder der Vorgänge, die am Anfang dieses Themas erwähnt muss MFC nach einem gewünschten Wert oder Objekt zu suchen. Während der Deserialisierung muss MFC durchsucht alle derzeit verfügbaren Laufzeit-Klassen Abgleich von Objekten im Archiv mit ihrer Laufzeit-Klasse.  
  
 Als Teil dieser sucht, MFC durchsucht alle der MFC-Erweiterungs-DLLs verwendet werden eine Kette von **CDynLinkLibrary** Objekte. **CDynLinkLibrary** Objekten automatisch bei ihrer Erstellung an eine Kette Anfügen und die Erstellung erfolgt jedes MFC-Erweiterungs-DLL wiederum während der Initialisierung. Darüber hinaus weist jedem Modul (Anwendung oder reguläre MFC-DLL) seine eigene Kette von **CDynLinkLibrary** Objekte.  
  
 Für eine MFC-Erweiterungs-DLL-Datei in wired Abrufen einer **CDynLinkLibrary** Kette, müssen sie erstellen eine **CDynLinkLibrary** Objekt im Kontext von jedem Modul, das die MFC-Erweiterungs-DLL verwendet. Deshalb Wenn soll eine MFC-Erweiterungs-DLL von regulären MFC-DLLs verwendet werden, es muss bereitstellen eine exportierten Initialisierungsfunktion, die erstellt eine **CDynLinkLibrary** Objekt. Alle regulären MFC-DLL mit der MFC-Erweiterung DLL muss die exportierten Initialisierungsfunktion aufrufen.  
  
 Wenn eine MFC-Erweiterungs-DLL geht nur aus einer MFC-Anwendung (.exe) und nie von einem regulären MFC-DLL verwendet werden, es ist ausreichend, erstellen Sie die **CDynLinkLibrary** Objekt in der MFC-Erweiterungs-DLL des `DllMain`. Dies ist die Funktionsweise der MFC-DLL-Assistenten MFC-Erweiterungs-DLL-Codes. Beim Laden einer MFC-Erweiterungs-DLL implizit `DllMain` geladen und ausgeführt wird, bevor Sie jemals Starten der Anwendung. Alle **CDynLinkLibrary** Erstellungen sind kabelgebundene in einer Standardkette, die MFC-DLL für eine MFC-Anwendung reserviert.  
  
 Beachten Sie, dass es eine gute Idee, mehrere **CDynLinkLibrary** Objekte aus einer MFC-Erweiterungs-DLL in jeder eine Kette, insbesondere dann, wenn die MFC-Erweiterungs-DLL dynamisch aus dem Arbeitsspeicher entladen werden. Die Initialisierungsfunktion aus jedem ein Modul nicht mehr als einmal aufgerufen.  
  
## <a name="sample-code"></a>Beispielcode  
 In diesem Beispielcode wird davon ausgegangen, dass die reguläre MFC-DLL implizit auf die MFC-Erweiterungs-DLL verknüpft ist. Dies wird erreicht, indem Sie eine Verknüpfung mit der Importbibliothek (.lib) von den MFC-Erweiterungs-DLL beim Erstellen der regulären MFC-DLL.  
  
 Die folgenden Zeilen muss in der Quelle der MFC-Erweiterungs-DLL:  
  
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
  
 Achten Sie darauf, dass Sie exportieren die **InitYourExtDLL** Funktion. Dies kann mit **__declspec(dllexport)** oder in der DEF Datei wie folgt:  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 Fügen Sie einen Aufruf an die `InitInstance` Mitglied der `CWinApp`-abgeleitetes Objekt in jeder reguläre MFC-DLL mit MFC-Erweiterungs-DLL:  
  
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
  
-   [MFC-Erweiterungs-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-extension-dlls)  
  
-   [Reguläre MFC-DLLs initialisieren](../build/run-time-library-behavior.md#initializing-regular-dlls)  
  
### <a name="what-do-you-want-to-know-more-about"></a>Worüber möchten Sie mehr erfahren?  
  
-   [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls.md)  
  
-   [Regular MFC DLLs Statically Linked to MFC (Reguläre, statisch mit MFC verknüpfte MFC-DLLs)](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Regular MFC DLLs Dynamically Linked to MFC (Reguläre, dynamisch mit MFC verknüpfte MFC-DLLs)](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [DLL Version of MFC](../mfc/tn033-dll-version-of-mfc.md)  
  
## <a name="see-also"></a>Siehe auch  
 [MFC extension DLLs (MFC-Erweiterungs-DLLs)](../build/extension-dlls.md)