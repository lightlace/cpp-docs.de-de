---
title: "Initialisieren von Erweiterungs-DLLs | Microsoft Docs"
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
  - "Erweiterungs-DLLs [C++], Initialisieren"
  - "Initialisieren von DLLs"
ms.assetid: 08ad0381-3808-4bea-a93c-c9ba62496543
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# Initialisieren von Erweiterungs-DLLs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Da Erweiterungs\-DLLs \(im Unterschied zu regulären DLLs\) kein von `CWinApp` abgeleitetes Objekt besitzen, sollte der Initialisierungs\- und Terminierungscode der `DllMain`\-Funktion hinzugefügt werden, die vom MFC\-DLL\-Assistenten generiert wird.  
  
 Der Assistent stellt den folgenden Code für Erweiterungs\-DLLs bereit.  Im folgenden Code ist `PROJNAME` ein Platzhalter für den Namen Ihres Projekts.  
  
```  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // Extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
 Durch das Erstellen eines neuen **CDynLinkLibrary**\-Objekts während der Initialisierung wird die Erweiterungs\-DLL in die Lage versetzt, `CRuntimeClass`\-Objekte oder \-Ressourcen in die Clientanwendung zu exportieren.  
  
 Wenn Sie die Erweiterungs\-DLL in einer oder mehreren regulären DLLs verwenden, müssen Sie eine Initialisierungsfunktion exportieren, durch die ein **CDynLinkLibrary**\-Objekt erstellt wird.  Diese Funktion muss von jeder regulären DLL aufgerufen werden, die die Erweiterungs\-DLL verwendet.  Eine geeignete Stelle zum Aufrufen dieser Initialisierungsfunktion ist die Memberfunktion `InitInstance` des von `CWinApp` abgeleiteten Objekts der regulären DLL, und zwar bevor eine der exportierten Klassen oder Funktionen der Erweiterungs\-DLL verwendet wird.  
  
 In der vom MFC\-DLL\-Assistenten erzeugten `DllMain`\-Funktion werden durch den Aufruf von `AfxInitExtensionModule` die Laufzeitklassen \(`CRuntimeClass`\-Strukturen\) des Moduls sowie seine Object Factories \(`COleObjectFactory`\-Objekte\) abgefangen, die beim Erstellen des **CDynLinkLibrary**\-Objekts verwendet werden.  Prüfen Sie den Rückgabewert von `AfxInitExtensionModule`. Wenn von `AfxInitExtensionModule` ein NULL\-Wert zurückgegeben wird, geben Sie auch Null aus der `DllMain`\-Funktion zurück.  
  
 Wenn die Erweiterungs\-DLL explizit mit einer ausführbaren Datei verknüpft werden soll \(d. h., die ausführbare Datei ruft `AfxLoadLibrary` auf, um die DLL zu verknüpfen\), sollten Sie **DLL\_PROCESS\_DETACH** einen Aufruf von `AfxTermExtensionModule` hinzufügen.  Mit dieser Funktion kann MFC die Erweiterungs\-DLL bereinigen, sobald ein Prozess von der Erweiterungs\-DLL getrennt wird \(das geschieht, wenn der Prozess beendet wird oder wenn die DLL aufgrund eines `AfxFreeLibrary`\-Aufrufs entladen wird\).  Wenn die Erweiterungs\-DLL implizit mit der Anwendung verknüpft werden soll, ist der Aufruf von `AfxTermExtensionModule` nicht nötig.  
  
 Anwendungen, die explizit mit Erweiterungs\-DLLs verknüpft werden, müssen `AfxTermExtensionModule` aufrufen, wenn die DLL entfernt wird.  Sie sollten auch `AfxLoadLibrary` und `AfxFreeLibrary` \(anstelle der Win32\-Funktionen **LoadLibrary** und **FreeLibrary**\) aufrufen, wenn die Anwendung mehrere Threads verwendet.  Die Verwendung von `AfxLoadLibrary` und `AfxFreeLibrary` stellt sicher, dass der Code für das Starten und Beenden, der beim Laden und beim Entladen der Erweiterungs\-DLL ausgeführt wird, den globalen MFC\-Zustand nicht beschädigt.  
  
 Da MFCx0.dll zum Zeitpunkt des Aufrufs von `DllMain` bereits vollständig initialisiert ist, können Sie in `DllMain` \(im Unterschied zur 16\-Bit\-Version von MFC\) Speicher belegen und MFC\-Funktionen aufrufen.  
  
 Durch Verarbeiten der Fälle **DLL\_THREAD\_ATTACH** und **DLL\_THREAD\_DETACH** in der `DllMain`\-Funktion können Erweiterungs\-DLLs das Multithreading verwalten.  Diese Fälle werden an `DllMain` übergeben, wenn Threads an die DLL angehängt bzw. von ihr getrennt werden.  Wenn beim Anfügen an eine DLL [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) aufgerufen wird, kann die DLL für jeden Thread, der an die DLL angefügt wird, Indizes für lokalen Threadspeicher \(Thread Local Storage, TLS\) verwalten.  
  
 Beachten Sie, dass die Headerdatei Afxdllx.h spezielle Definitionen für Strukturen enthält, die in Erweiterungs\-DLLs verwendet werden, z. B. die Definitionen für `AFX_EXTENSION_MODULE` und **CDynLinkLibrary**.  Sie sollten diese Headerdatei in die Erweiterungs\-DLL aufnehmen.  
  
> [!NOTE]
>  Es ist wichtig, dass Sie keines der \_AFX\_NO\_XXX\-Makros in Stdafx.h definieren bzw. deren Definition außer Kraft setzen.  Weitere Informationen finden Sie im Artikel "PRB: Problems Occur When Defining \_AFX\_NO\_XXX" \(Q140751, nur auf Englisch verfügbar\) in der Microsoft Knowledge Base.  Knowledge Base\-Artikel finden Sie in der MSDN Library oder an [http:\/\/search.support.microsoft.com\/](http://search.support.microsoft.com/) suchen.  
  
 Ein Beispiel für eine Initialisierungsfunktion, die Multithreading behandelt, finden Sie unter [Using Thread Local Storage in a Dynamic\-Link Library](http://msdn.microsoft.com/library/windows/desktop/ms686997) im [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  Das Beispiel enthält eine Einsstiegspunktfunktion mit dem Namen **LibMain**, die jedoch in `DllMain` umbenannt werden sollte, damit diese Funktion mit den Laufzeitbibliotheken von MFC und C einwandfrei zusammenwirkt.  
  
 Das MFC\-Beispiel [DLLHUSK](assetId:///dfcaa6ff-b8e2-4efd-8100-ee3650071f90) veranschaulicht die Verwendung von Initialisierungsfunktionen.  
  
## Was möchten Sie tun?  
  
-   [Reguläre DLLs initialisieren](../build/initializing-regular-dlls.md)  
  
-   [MFC\-fremde DLLs initialisieren](../build/initializing-non-mfc-dlls.md)  
  
## Worüber möchten Sie mehr erfahren?  
  
-   [Das Verhalten der C\-Laufzeitbibliothek und \_DllMainCRTStartup](../build/run-time-library-behavior.md)  
  
-   [Verwenden von Datenbank\-, OLE\- und Sockets\-Erweiterungs\-DLLs in regulären DLLs](../build/using-database-ole-and-sockets-extension-dlls-in-regular-dlls.md)  
  
-   [\<caps:sentence id\="tgt34" sentenceid\="58bb7328659bda9ffb73a1dcd39da06b" class\="tgtSentence"\>Die Funktionsspezifikation für DllMain \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682583)  
  
-   [\<caps:sentence id\="tgt35" sentenceid\="f29344705c59343b34b642944921cbdf" class\="tgtSentence"\>Dynamic Link Library\-Einstiegspunktfunktion \(Windows SDK\)\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms682596)  
  
## Siehe auch  
 [Initialisieren einer DLL](../build/initializing-a-dll.md)