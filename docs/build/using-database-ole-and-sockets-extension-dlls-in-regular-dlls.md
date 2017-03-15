---
title: "Verwenden von Datenbank-, OLE- und Sockets-Erweiterungs-DLLs in regul&#228;ren DLLs | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DLLs [C++], Erweiterung"
  - "DLLs [C++], Initialisieren"
  - "DLLs [C++], Reguläre"
ms.assetid: 9f1d14a7-9e2a-4760-b3b6-db014fcdb7ff
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden von Datenbank-, OLE- und Sockets-Erweiterungs-DLLs in regul&#228;ren DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Bei Verwendung einer Erweiterungs\-DLL aus einer regulären DLL können u. U. mehrere zusammenhängende Probleme auftreten, falls die Erweiterungs\-DLL nicht in die **CDynLinkLibrary**\-Objektkette der regulären DLL eingegliedert ist.  Da das Debugbuild der unterstützenden MFC\-Datenbank\-, OLE\- und Sockets\-DLLs als Erweiterungs\-DLLs implementiert sind, können Ihnen ähnliche Probleme begegnen, wenn Sie diese MFC\-Features verwenden. Dies gilt selbst dann, wenn Sie keine eigenen Erweiterungs\-DLLs explizit verwenden.  Einige Symptome sind:  
  
-   Beim Versuch, ein Objekt vom Typ einer in der Erweiterungs\-DLL definierten Klasse zu deserialisieren, wird im TRACE\-Debugfenster eine Warnung angezeigt, dass die Klasse nicht aus dem Archiv geladen werden kann,  da sie Klasse nicht definiert ist. Die Objektserialisierung schlägt daraufhin fehl.  
  
-   Es kann eine Ausnahme mit dem Hinweis auf eine fehlerhafte Klasse ausgelöst werden.  
  
-   Die in der Erweiterungs\-DLL gespeicherten Ressourcen können nicht geladen werden, da `AfxFindResourceHandle` den Wert **NULL** oder ein falsches Ressourcenhandle zurückgibt.  
  
-   `DllGetClassObject`, `DllCanUnloadNow` und die Memberfunktionen `UpdateRegistry`, `Revoke`, `RevokeAll` und `RegisterAll` von `COleObjectFactory` sind nicht in der Lage, eine in der Erweiterungs\-DLL definierte Class Factory zu lokalisieren.  
  
-   `AfxDoForAllClasses` kann für keine der Klassen in der Erweiterungs\-DLL ausgeführt werden.  
  
-   Die MFC\-Standardressourcen für Datenbanken, Sockets oder OLE können nicht geladen werden.  Der Aufruf **AfxLoadString**\(**AFX\_IDP\_SQL\_CONNECT\_FAIL**\) gibt z. B. selbst dann eine leere Zeichenfolge zurück, wenn die MFC\-Datenbankklassen korrekt von der regulären DLL verwendet werden.  
  
 Um diese Probleme zu beheben, erstellen und exportieren Sie eine Initialisierungsfunktion in der Erweiterungs\-DLL, wodurch ein **CDynLinkLibrary**\-Objekt erstellt wird.  Rufen Sie diese Initialisierungsfunktion genau einmal aus jeder regulären DLL auf, die die Erweiterungs\-DLL verwendet.  
  
## MFC\-Unterstützung für OLE, Datenbanken \(oder DAO\) und Sockets  
 Wenn Sie die MFC\-Unterstützung für OLE, Datenbanken \(bzw. DAO\) oder Sockets in der regulären DLL verwenden, werden die MFC\-Debugbuilds der Erweiterungs\-DLLs MFCOxxD.dll, MFCDxxD.dll und MFCNxxD.dll automatisch verknüpft \(xx entspricht der Versionsnummer\).  Für jede dieser verwendeten DLLs müssen Sie eine vordefinierte Initialisierungsfunktion aufrufen.  
  
 Für die Datenbankunterstützung fügen Sie der `CWinApp::InitInstance`\-Funktion der regulären DLL einen `AfxDbInitModule`\-Aufruf hinzu.  Achten Sie darauf, dass dieser Aufruf vor eventuellen Basisklassenaufrufen bzw. vor der Ausführung von zusätzlichem Code stattfindet, der auf MFCDxxD.dll zugreift.  Diese Funktion hat keine Parameter und eine leere Rückgabe.  
  
 Für die OLE\-Unterstützung fügen Sie der `CWinApp::InitInstance`\-Funktion der regulären DLL einen `AfxOleInitModule`\-Aufruf hinzu.  Beachten Sie, dass die `COleControlModule`\-Funktion  `bereits AfxOleInitModule aufruft, sodass Sie beim Erstellen eines OLE-Steuerelements mit COleControlModule` den Aufruf von AfxOleInitModule nicht hinzufügen sollten.  
  
 Für die Sockets\-Unterstützung fügen Sie der `CWinApp::InitInstance`\-Funktion der regulären DLL einen `AfxNetInitModule`\-Aufruf hinzu.  
  
 Beachten Sie, dass Releasebuilds von MFC\-DLLs und \-Anwendungen keine separaten DLLs für die Datenbank\-, Sockets\- oder OLE\-Unterstützung verwenden.  Im Releasemodus können diese Initialisierungsfunktionen jedoch bedenkenlos aufgerufen werden.  
  
## CDynLinkLibrary\-Objekte  
 Während jeder der Operationen, die zu Beginn dieses Artikels erwähnt wurden, muss MFC nach einem gewünschten Wert oder Objekt suchen.  Während der Deserialisierung muss MFC z. B. alle zurzeit verfügbaren Laufzeitklassen durchsuchen, um für jedes Objekt im Archiv die entsprechende Laufzeitklasse zu finden.  
  
 Bei diesen Suchläufen durchsucht MFC auch alle verwendeten Erweiterungs\-DLLs, wobei eine Kette von **CDynLinkLibrary**\-Objekten durchlaufen wird.  **CDynLinkLibrary**\-Objekte werden während der Initialisierung von jeder einzelnen Erweiterungs\-DLL erstellt und bei der Erstellung automatisch an eine Kette angefügt.  Außerdem hat jedes Modul \(Anwendung oder reguläre DLL\) seine eigene Kette von **CDynLinkLibrary**\-Objekten.  
  
 Damit eine Erweiterungs\-DLL in eine **CDynLinkLibrary**\-Kette eingegliedert werden kann, muss diese ein **CDynLinkLibrary**\-Objekt im Kontext jedes Moduls erstellen, das die Erweiterungs\-DLL verwendet.  Wenn eine Erweiterungs\-DLL von regulären DLLs verwendet werden soll, muss sie daher eine exportierte Initialisierungsfunktion bereitstellen, durch die ein **CDynLinkLibrary**\-Objekt erstellt wird.  Jede reguläre DLL, die die Erweiterungs\-DLL verwendet, muss die exportierte Initialisierungsfunktion aufrufen.  
  
 Wenn eine Erweiterungs\-DLL ausschließlich von einer MFC\-Anwendung \(EXE\) und niemals von einer regulären DLL verwendet werden soll, reicht es aus, das **CDynLinkLibrary**\-Objekt in der `DllMain`\-Funktion der Erweiterungs\-DLL zu erstellen.  Genau dies ist die Aufgabe des vom MFC\-DLL\-Assistenten generierten Erweiterungs\-DLL\-Codes.  Wenn eine Erweiterungs\-DLL implizit geladen wird, wird vor dem eigentlichen Anwendungsstart die `DllMain`\-Funktion geladen und ausgeführt.  Alle **CDynLinkLibrary**\-Objekte werden in eine Standardkette eingegliedert, die von der MFC\-DLL für eine MFC\-Anwendung reserviert wird.  
  
 Es wird davon abgeraten, mehrere, zu einer Erweiterungs\-DLL gehörige **CDynLinkLibrary**\-Objekte in einer Kette anzulegen. Dies gilt insbesondere, wenn die Erweiterungs\-DLL dynamisch aus dem Speicher entladen wird.  Die Initialisierungsfunktion sollte von jedem Modul jeweils nur einmal aufgerufen werden.  
  
## Beispielcode  
 Bei diesem Beispielcode wird davon ausgegangen, dass die reguläre DLL implizit mit der Erweiterungs\-DLL verknüpft wird.  Dazu wird beim Erstellen der regulären DLL eine Verknüpfung mit der Importbibliothek \(.lib\) der Erweiterungs\-DLL erstellt.  
  
 Die folgenden Zeilen sollten im Quellcode der Erweiterungs\-DLL enthalten sein:  
  
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
        // extension DLL one-time initialization  
        if (!AfxInitExtensionModule(extensionDLL, hInstance))  
           return 0;  
    }  
    return 1;   // ok  
}  
  
// Exported DLL initialization is run in context of  
// application or regular DLL  
extern "C" void WINAPI InitYourExtDLL()  
{  
    // create a new CDynLinkLibrary for this app  
    new CDynLinkLibrary(extensionDLL);  
  
    // add other initialization here  
}  
```  
  
 Achten Sie darauf, die **InitYourExtDLL**\-Funktion zu exportieren.  Dazu können Sie **\_\_declspec\(dllexport\)** oder die DEF\-Datei der DLL verwenden, wie im Folgenden erläutert:  
  
```  
// YourExtDLL.Def:  
LIBRARY      YOUREXTDLL  
CODE         PRELOAD MOVEABLE DISCARDABLE  
DATA         PRELOAD SINGLE  
EXPORTS  
    InitYourExtDLL  
```  
  
 Fügen Sie einen Aufruf des `InitInstance`\-Members des von `CWinApp` abgeleiteten Objekts in jede reguläre DLL ein, die die Erweiterungs\-DLL verwendet:  
  
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
    TRACE0("YOUR regular DLL initializing\n");  
  
    // wire any extension DLLs into CDynLinkLibrary chain  
    InitYourExtDLL();  
  
    return TRUE;  
}  
```  
  
### Was möchten Sie tun?  
  
-   [Erweiterungs\-DLLs initialisieren](../build/initializing-extension-dlls.md)  
  
-   [Reguläre DLLs initialisieren](../build/initializing-regular-dlls.md)  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Erweiterungs\-DLLs](../build/extension-dlls.md)  
  
-   [Reguläre, statisch mit MFC verknüpfte DLLs](../build/regular-dlls-statically-linked-to-mfc.md)  
  
-   [Reguläre, dynamisch mit MFC verknüpfte DLLs](../build/regular-dlls-dynamically-linked-to-mfc.md)  
  
-   [Verwenden von MFC als Teil einer DLL](../mfc/tn011-using-mfc-as-part-of-a-dll.md)  
  
-   [DLL Version of MFC \(nur auf Englisch verfügbar\)](../mfc/tn033-dll-version-of-mfc.md)  
  
## Siehe auch  
 [Erweiterungs\-DLLs](../build/extension-dlls.md)