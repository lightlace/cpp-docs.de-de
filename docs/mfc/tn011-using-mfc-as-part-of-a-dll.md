---
title: 'TN011: Verwenden von MFC als Teil einer DLL | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.dll
dev_langs:
- C++
helpviewer_keywords:
- _USRDLL symbol
- USRDLLs, compiler switches
- TN011
- DLLs [MFC], linking
- MFC DLLs [MFC], linking regular MFC DLLs to MFC
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0d0ac05e314f3f8354ba289695afa672b1e28881
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="tn011-using-mfc-as-part-of-a-dll"></a>TN011: Verwenden von MFC als Teil einer DLL
In diesem Hinweis werden reguläre MFC-DLLs, die Ihnen ermöglichen, die MFC-Bibliothek als Teil einer Windows-Dynamic Link Library (DLL) zu verwenden. Es wird davon ausgegangen, dass Sie mit Windows-DLLs sowie von ihnen vertraut sind. Informationen über MFC-Erweiterungs-DLLs, mit denen Sie erstellen können Erweiterungen für die MFC-Bibliothek finden Sie unter [DLL-Version von MFC](../mfc/tn033-dll-version-of-mfc.md).  
  
## <a name="dll-interfaces"></a>DLL-Schnittstellen  
 reguläre MFC-DLLs wird davon ausgegangen, Schnittstellen zwischen der Anwendung und die DLL in C-ähnliche Funktionen oder explizit exportierten Klassen angegeben werden. MFC-Klassenschnittstellen können nicht exportiert werden.  
  
 Wenn eine DLL-Datei und einer Anwendung MFC verwenden möchten, haben beide eine Auswahl entweder die freigegebene Version von MFC-Bibliotheken verwenden oder statisch mit einer Kopie der Bibliotheken verknüpfen. Die Anwendung und die DLL kann sowohl eine standard-Versionen der MFC-Bibliothek verwenden.  
  
 reguläre MFC-DLLs haben mehrere Vorteile:  
  
-   Die Anwendung, die die DLL verwendet keine MFC verwendet und muss nicht in eine Visual C++-Anwendung sein.  
  
-   Mit regulären MFC-DLLs, die statisch mit MFC verknüpft sind, hängt von der Größe der DLL nur die MFC- und C-Laufzeitroutinen, die verwendet und verknüpft werden.  
  
-   Mit regulären MFC-DLLs, die dynamisch mit MFC verknüpfen, können die einsparungen im Arbeitsspeicher von der Verwendung der gemeinsam genutzten MFC-Version sehr deutlich sein. Sie müssen jedoch die gemeinsam genutzten DLLs, Mfc verteilen*\<Version >*DLL- und Msvvcrt*\<Version >*.dll, zusammen mit der DLL.  
  
-   Die DLL-Entwurf ist unabhängig von der Implementierung von Klassen. Entwurfs DLL exportiert nur für die APIs werden sollen. Wenn die Implementierung geändert wird, werden folglich reguläre MFC-DLLs noch gültig.  
  
-   Mit regulären MFC-DLLs, die statisch mit MFC verknüpfen, wenn sowohl DLL-als auch Anwendung MFC verwenden, treten keine Probleme mit der Anwendung, die eine andere Version von MFC als DLL oder umgekehrt werden sollen. Da die MFC-Bibliothek statisch in alle DLL- und EXE-Datei verknüpft ist, ist keine Frage, welche Version Sie haben.  
  
## <a name="api-limitations"></a>API-Einschränkungen  
 Einige MFC-Funktionen gilt nicht für die DLL-Version, entweder aufgrund von technischen Einschränkungen oder weil diese Dienste in der Regel von der Anwendung bereitgestellt werden. Mit der aktuellen Version von MFC, ist die einzige Funktion, die nicht anwendbar ist `CWinApp::SetDialogBkColor`.  
  
## <a name="building-your-dll"></a>Erstellen der DLL  
 Beim Kompilieren von regulären MFC-DLLs, die statisch mit MFC, die Symbole verknüpft `_USRDLL` und `_WINDLL` muss definiert werden. Die DLL-Code muss auch mit den folgenden Compilerschaltern kompiliert werden:  
  
- **/ D_WINDLL** gibt an, dass die Kompilierung für eine DLL  
  
- **/ D_USRDLL** gibt an, Sie erstellen eine reguläre MFC-DLL  
  
 Sie müssen auch diese Symbole zu definieren und diese Compilerschalter beim Kompilieren regulärer MFC-DLLs, die dynamisch mit MFC verknüpft. Darüber hinaus das Symbol `_AFXDLL` muss definiert sein und der DLL-Code mit kompiliert werden muss:  
  
- **/ D_AFXDLL** gibt an, dass Sie eine reguläre MFC-DLL erstellen, die dynamisch mit MFC verknüpft  
  
 Die Anwendungsprogrammierschnittstellen (APIs) zwischen der Anwendung und DLL müssen explizit exportiert werden. Es wird empfohlen, dass Sie die Schnittstellen definieren, um mit geringer Bandbreite werden und nur die C-Schnittstellen verwenden, wenn möglich. Direkte C-Schnittstellen sind einfacher zu verwalten als komplexere C++-Klassen.  
  
 Platzieren Sie Ihre APIs in einem separaten Header, der von C und C++-Dateien eingeschlossen werden kann. Finden Sie unter den Header ScreenCap.h im MFC Advanced Concepts-Beispiel [DLLScreenCap](../visual-cpp-samples.md) ein Beispiel. Um Funktionen zu exportieren, geben Sie in der `EXPORTS` Teil Ihrer Moduldefinitionsdatei (. "Def") oder `__declspec(dllexport)` auf Ihre Funktionsdefinitionen. Verwendung `__declspec(dllimport)` dieser Funktionen in die ausführbare Clientdatei importieren.  
  
 Sie müssen Hinzufügen der `AFX_MANAGE_STATE` Makro am Anfang der exportierten Funktionen in regulären MFC-DLLs, die dynamisch mit MFC verknüpft sind. Dieses Makro legt den aktuellen Zustand des Moduls mit der für die DLL. Um dieses Makro verwenden, fügen Sie die folgende Codezeile am Anfang des aus der DLL exportierten Funktionen hinzu:  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## <a name="winmain---dllmain"></a>WinMain-DllMain >  
 Die MFC-Bibliothek definiert die standard-Win32 `DllMain` Einstiegspunkt, der initialisiert die [CWinApp](../mfc/reference/cwinapp-class.md) abgeleitetes Objekt wie bei einer normalen MFC-Anwendung. Platzieren Sie alle DLL-spezifische Initialisierung in der [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) -Methode verwenden, wie eine typische MFC-Anwendung.  
  
 Beachten Sie, dass die [CWinApp:: Run](../mfc/reference/cwinapp-class.md#run) Mechanismus selbst gilt nicht für eine DLL, da die Anwendung die Haupt-Meldungsverteilschleife besitzt. Wenn Ihre DLL keine modalen Dialogfelder zeigt oder einem Hauptrahmenfenster eigene, Haupt-Meldungsverteilschleife für Ihre Anwendung muss eine DLL exportiert Routine aufrufen, die Aufrufe [PreTranslateMessage](../mfc/reference/cwinapp-class.md#pretranslatemessage).  
  
 Finden Sie im DLLScreenCap-Beispiel für die Verwendung dieser Funktion aus.  
  
 Die `DllMain` -Funktion, die MFC bietet aufrufen, wird die [CWinApp:: ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) -Methode einer Klasse, die abgeleitet ist `CWinApp` , bevor die DLL entladen wird.  
  
## <a name="linking-your-dll"></a>Verknüpfen einer DLL  
 Mit regulären MFC-DLLs, die statisch mit MFC verknüpft sind, müssen Sie die DLL mit Nafxcwd.lib oder Nafxcw.lib und die Version der C-Laufzeiten, mit dem Namen "LIBCMT.lib" verknüpfen. Diese Bibliotheken sind vorkonfigurierte und können durch Angabe beim Ausführen von Visual C++-Setup installiert werden.  
  
## <a name="sample-code"></a>Beispielcode  
 Finden Sie im MFC Advanced Concepts-Beispiel, die ein vollständiges Beispiel DLLScreenCap programmieren. Einige interessante Punkte zu beachten Sie in diesem Beispiel lauten wie folgt:  
  
-   Die Compilerflags der DLL und die von der Anwendung sind unterschiedlich.  
  
-   Die Link-Zeilen und. DEF-Dateien für die DLL als auch für die Anwendung unterscheiden.  
  
-   Die Anwendung, die die DLL verwendet, muss es sich nicht in c++ werden.  
  
-   Die Schnittstelle zwischen der Anwendung und die DLL ist eine API, die von C oder C++ verwendet werden kann und exportiert wird, wird mit DLLScreenCap.def.  
  
 Das folgende Beispiel veranschaulicht eine API, die in eine reguläre MFC-DLL definiert wird, die statisch mit MFC verknüpft wird. In diesem Beispiel wird die Deklaration eingeschlossen ein `extern "C" { }` Block für C++-Benutzer. Dies hat mehrere Vorteile. Zunächst ist es Ihre DLL-APIs verwendet werden kann von nicht-c++-Clientanwendungen. Zweitens es DLL wird der Aufwand reduziert, da die namenszerlegung für C++ in den exportierten Namen nicht angewendet werden. Abschließend wird es erleichtert es, explizit hinzufügen ein. "Def"-Datei (für den Export nach Ordnungszahl) ohne namenszerlegung kümmern.  
  
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
  
 Die von der API verwendeten Strukturen nicht von MFC-Klassen abgeleitet werden und in der API-Header definiert sind. Dadurch reduziert die Komplexität der Schnittstelle zwischen der DLL und der Anwendung und die DLL verwendet werden kann von C-Programmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Technische Hinweise – nach Anzahl](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

