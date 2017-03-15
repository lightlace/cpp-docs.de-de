---
title: "TN011: Verwenden von MFC als Teil einer DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_USRDLL-Symbol"
  - "DLLs [C++], Verknüpfen"
  - "MFC-DLLs [C++], Verknüpfen regulärer DLLs mit MFC"
  - "TN011"
  - "USRDLLs, Compilerschalter"
ms.assetid: 76753e9c-59dc-40f6-b6a7-f6bb9a7c4190
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 16
---
# TN011: Verwenden von MFC als Teil einer DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Hinweis beschreibt reguläre DLL, die es Ihnen ermöglichen, die MFC\-Bibliothek als Bestandteil einer Dynamic Link Library \(DLL\) verwenden.  Es wird vorausgesetzt, dass Sie mit DLL\-Dateien vertraut sind und wie sie erstellt.  Informationen zum MFC\-Erweiterungs\-DLLs, mit denen Sie Erweiterungen der MFC\-Bibliothek erstellen können, finden Sie unter [DLL Version of MFC](../mfc/tn033-dll-version-of-mfc.md).  
  
## DLL\-Schnittstellen  
 Reguläre DLL wird angenommen, dass Schnittstellen zwischen der Anwendung und der DLL in C ähnlichen Funktionen oder explizit in exportierten Klassen angegeben werden.  MFC\-Klassen\-Schnittstellen können nicht exportiert werden.  
  
 Wenn eine DLL und eine Anwendung, MFC verwenden möchten, können Sie eine Auswahl entweder zur Verwendung die freigegebene Version der MFC\-Bibliotheken oder zu statisch mit einer Kopie der Bibliotheken verknüpfen.  Die Anwendung und DLL beide verwenden möglicherweise eine der Standardversionen der MFC\-Bibliothek.  
  
 Reguläre DLLs haben mehrere Vorteile:  
  
-   Die Anwendung, die die DLL verwendet, muss MFC nicht verwenden und muss keine Visual C\+\+\-Anwendung sein.  
  
-   Mit regulären DLL, die statisch mit MFC verknüpfen, wird die Größe der DLL nur von MFC und den C\-Ablaufroutinen ab, die verwendet und verknüpft werden.  
  
-   Mit regulären DLL, die dynamisch mit MFC verknüpfen kann, die sich im Arbeitsspeicher von der Anwendung der gemeinsam genutzten MFC\-Version erheblich sein.  Sie müssen jedoch die gemeinsam genutzten DLLs, den Kraftstoffregler *\<version\>*.dll und das Msvvcrt *\<version\>*.dll verteilen, mit der DLL.  
  
-   Der DLL\-Entwurf ist unabhängig von, wie Klassen implementiert werden.  das DLL\-Entwurf exportiert nur in die APIs, werden.  Daher wird die Implementierung ändern, sind reguläre DLL noch gültig.  
  
-   Mit regulären DLL, die statisch mit MFC verknüpfen, wenn Anwendung und DLL MFC verwendet, gibt keine Probleme mit der Anwendung, die eine andere Version von MFC als DLL oder umgekehrt\).  Da die MFC\-Bibliothek statisch in jede DLL in EXE oder verknüpft ist, gibt es keine Fragen darüber, welche Version Sie haben.  
  
## API Einschränkungen  
 Einige MFC\-Funktionalität gilt nicht für die DLL\-Version, entweder aufgrund der technischen Einschränkungen zu oder, da diese Dienste normalerweise von der Anwendung bereitgestellt werden.  Mit der aktuellen Version von MFC, ist die einzige Funktion, die nicht angewendet ist, `CWinApp::SetDialogBkColor`.  
  
## Erstellen der DLL  
 Wenn muss das Kompilieren von regulären DLL, die statisch mit MFC, auf Symbole `_USRDLL` und `_WINDLL` verknüpfen, definiert werden.  Der DLL\-Code muss den folgenden Compilerschaltern auch kompiliert werden:  
  
-   **\/D\_WINDLL** gibt der Kompilierung ist für eine DLL an  
  
-   **\/D\_USRDLL** ermöglicht Ihnen erstellen eine reguläre DLL an  
  
 Diese Symbole müssen Sie auch definieren und diese Compilerschalter verwenden, wenn Sie reguläre DLL kompilieren, die dynamisch mit MFC verknüpfen.  Zudem muss das Symbol `_AFXDLL` definiert und der DLL\-Code muss mit kompiliert werden:  
  
-   **\/D\_AFXDLL** gibt an, dass Sie eine reguläre DLL, die dynamisch mit MFC verknüpft  
  
 Die Schnittstellen \(APIs\) zwischen der Anwendung und der DLL müssen explizit exportiert werden.  Es wird empfohlen, die Schnittstellen definieren, um geringe Bandbreite zu sein, verwenden und nur C\-Schnittstellen, wenn Sie können.  Direkte C\-Schnittstellen sind einfacher als komplexere C\+\+\-Klassen zu warten.  
  
 Platzieren Sie die APIs in einer separaten Headerdatei, die von C\- als C\+\+\-Dateien enthalten sein kann.  Siehe die Header ScreenCap.h im MFC Advanced Konzeptbeispiel [DLLScreenCap](../top/visual-cpp-samples.md) als Beispiel.  Um die Funktionen zu exportieren, geben Sie diese im Abschnitt `EXPORTS` der Moduldefinitionsdatei \(.DEF\) oder schließen Sie `__declspec(dllexport)` auf den Funktionsdefinitionen ein.  Verwenden Sie `__declspec(dllimport)`, um diese Funktionen in die ausführbare Clientdatei zu importieren.  
  
 Sie müssen das `AFX_MANAGE_STATE`\-Makro zu allen exportierten Funktionen in reguläre DLL hinzufügen, die dynamisch mit MFC verknüpfen.  Dieses Makro legt den Zustand der DLL als aktuellen Modulzustand fest.  Um dieses Makro zu verwenden, fügen Sie die folgende Codezeile am Anfang von Funktionen hinzu, die aus der DLL exportiert werden:  
  
 `AFX_MANAGE_STATE(AfxGetStaticModuleState( ))`  
  
## DllMain WinMain \-\>  
 Die MFC\-Bibliothek definiert den Standard\-Einstiegspunkt Win32\- `DllMain`, der die [CWinApp](../mfc/reference/cwinapp-class.md) berechnetes Objekt wie in einer normalen MFC\-Anwendung initialisiert.  Fügen Sie alle DLL\-Besondereinitialisierung in der Methode wie [InitInstance](../Topic/CWinApp::InitInstance.md) in einer normalen MFC\-Anwendung.  
  
 Beachten Sie, dass der [CWinApp::Run](../Topic/CWinApp::Run.md)\-Mechanismus nicht auf eine DLL angewendet werden kann, da die Haupt\-Meldungsverteilschleife im Besitz der Anwendung ist.  Wenn die DLL nicht modale Dialogfelder anzeigt oder ein eigenes Hauptrahmenfenster hat, muss die Haupt\-Meldungsverteilschleife der Anwendung eine aus der DLL exportierte Routine aufrufen, die [CWinApp::PreTranslateMessage](../Topic/CWinApp::PreTranslateMessage.md).  
  
 Siehe das DLLScreenCap\-Beispiel für Verwendung dieser Funktion.  
  
 Die `DllMain`\-Funktion, die MFC bereitstellt, ruft die Methode [CWinApp::ExitInstance](../Topic/CWinApp::ExitInstance.md) der Klasse, die von `CWinApp`  abgeleitet wird, bevor die DLL entladen wird.  
  
## Verknüpfen der DLL  
 Mit regulären DLL, die statisch mit MFC verknüpfen, müssen Sie die DLL mit Nafxcwd.lib oder Nafxcw.lib und mit der Version der C\-Laufzeiten verknüpfen, die mit Libcmt.lib werden.  Diese Bibliotheken sind vordefiniert und installiert werden, indem sie angibt, wenn Sie Visual C\+\+ Setup erneut aus ausführen.  
  
## Beispielcode  
 Siehe MFC erweiterte Konzeptbeispielprogramm DLLScreenCap für ein vollständiges Beispiel.  Einige interessante in diesem Beispiel zu beachten Elemente, sind, wie folgt:  
  
-   Die Compilerflags der DLL und die der Anwendung sind unterschiedlich.  
  
-   Die Linkzeilen und DEF\-Dateien für die DLL und die für die Anwendung sind unterschiedlich.  
  
-   Die Anwendung, die die DLL verwendet, muss nicht in C\+\+ sein.  
  
-   Die Schnittstelle zwischen der Anwendung und der DLL ist eine API, die mit C oder C\+\+ verwendbar ist und mit DLLScreenCap.def exportiert wird.  
  
 Das folgende Beispiel veranschaulicht eine API, die in einem regulären DLL definiert wird, die statisch mit MFC verknüpft.  In diesem Beispiel wird die Deklaration in einem `extern "C" { }`\-Block für C\+\+\-Benutzer eingeschlossen.  Dies hat verschiedene Vorteile.  Zunächst ist die DLL damit auch für Nicht\-C\+\+\-Clientanwendungen verwendbar APIs.  wird der DLL\-Verarbeitungsaufwand reduziert, da die C\+\+\-Namensergänzung nicht auf den exportierten Namen angewendet wird.  Abschließend wird es einfacher, einer DEF\-Datei \(zum Exportieren nach Ordnungszahl\) ohne zu müssen explizit hinzuzufügen, um Namensergänzung verloren gehen.  
  
```  
#ifdef __cplusplus  
extern "C" {  
#endif  /* __cplusplus */  
  
struct TracerData  
{  
    BOOL    bEnabled;  
    UINT    flags;  
};  
  
BOOL PromptTraceFlags(TracerData FAR* lpData);  
  
#ifdef __cplusplus  
}  
#endif  
```  
  
 Strukturen, die von der API verwendet werden, werden nicht von MFC\-Klassen abgeleitet und werden in der APIkopfzeile definiert.  Dies reduziert die Komplexität der Schnittstelle zwischen der DLL und der Anwendung und führt die DLL verwendet von C\-Programme.  
  
## Siehe auch  
 [Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)   
 [Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)