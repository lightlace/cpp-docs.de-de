---
title: "&#196;ndern der Stile eines mit MFC erstellten Fensters | Microsoft Docs"
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
  - "CFrameWnd-Klasse, Fensterstile"
  - "Untergeordnete Fenster, Stile"
  - "CMainFrame-Klasse"
  - "CMDIChildWnd-Klasse, Ändern von Fensterstilen"
  - "CREATESTRUCT-Makro"
  - "Standardfensterstile"
  - "Standardwerte [C++], Fensterstil"
  - "MDI [C++], Fensterstile"
  - "MFC [C++], Fenster"
  - "Mehrfachdokument-Schnittstellenstil"
  - "PreCreateWindow-Methode, Ändern von Fensterstilen"
  - "PreCreateWindow-Methode, Fensterstile"
  - "Einzeldokumentoberfläche (SDI), Ändern von Fensterattributen"
  - "Einzeldokumentoberfläche (SDI), Stile"
  - "Stile, Fenster"
  - "Fensterstile [C++]"
  - "Fenster [C++], MFC"
  - "WS_OVERLAPPEDWINDOW-Makro"
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#196;ndern der Stile eines mit MFC erstellten Fensters
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In seiner Version der Funktion `WinMain`, registriert MFC einige Standardfensterklassen für Sie.  Da Sie normalerweise `WinMain` MFC bearbeiten, gibt diese Funktion Ihnen keine Möglichkeit, die MFC\-Standardfensterstile zu ändern.  Dieser Artikel wird beschrieben, wie die Formate einer solchen registrierten Fensterklasse in einer vorhandenen Anwendung ändern können.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Ändern von Stilen in eine neue MFC\-Anwendung  
 Wenn Sie Visual C\+\+ 2.0 oder höher verwenden, können Sie die Standardfensterstile im Anwendungs\-Assistenten ändern, wenn Sie die Anwendung erstellen.  In den die Benutzeroberflächen\-Funktionen Seite des Anwendungs\-Assistenten, können Sie Stile für das Hauptrahmenfenster und untergeordneten MDI\-Fenster ändern.  Für jeden Fenstertyp können Sie der Framestärke \(oder stark verdünnen\) und eines der folgenden Elemente angeben:  
  
-   Ob das Fenster Steuerelemente, zu minimieren hat zu maximieren.  
  
-   Ob das Fenster erstmals angezeigt wird minimiert, maximiert oder nicht.  
  
 Für Hauptrahmenfenster können Sie auch angeben, ob das Fenster ein Systemmenü hat.  Eine untergeordnete MDI\-Fenster können Sie angeben, ob das Fenster Splitterbereiche unterstützt.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a> Ändern von Stilen in einer vorhandenen Anwendung  
 Wenn Sie Fensterattribute in einer vorhandenen Anwendung ändern, befolgen Sie die Anweisungen im Rest dieses Artikels stattdessen.  
  
 Um die Standardfensterattribute zu ändern, die durch eine Framework\-Anwendung verwendet wurden erstellt mit dem Anwendungs\-Assistenten, überschreiben die virtuelle Memberfunktion [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md) des Fensters.  `PreCreateWindow` ermöglicht es einer Anwendung, auf den Erstellungsprozess zuzugreifen, der normalerweise intern durch die [CDocTemplate](../mfc/reference/cdoctemplate-class.md)\-Klasse verwaltet wird.  Das Framework ruft `PreCreateWindow` kurz vor dem Erstellen des Fensters auf.  Indem die [CREATESTRUCT](../mfc/reference/createstruct-structure.md)\-Struktur ändern, die an `PreCreateWindow` übergeben wird, kann die Anwendung die Attribute ändern, die verwendet werden, um das Fenster zu erstellen.  Beispielsweise um sicherzustellen, dass ein Fenster keine Beschriftung verwendet, verwenden Sie die folgende bitweise Operation:  
  
 [!CODE [NVC_MFCDocView#15](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#15)]  
  
 Die Beispielanwendung [CTRLBARS](../top/visual-cpp-samples.md) wird diese Technik für das Ändern von Fensterattributen.  Je nachdem, was Ihre Anwendung in `PreCreateWindow` geändert wird, ist möglicherweise notwendig, die Basisklassenimplementierung der Funktion aufzurufen.  
  
 In der folgenden Beschreibung werden der SDI\-Fall und [MDI\-Fall](#_core_the_mdi_case).  
  
##  <a name="_core_the_sdi_case"></a> Der SDI\-Fall  
 In einer Single Document Interface \(SDI\)\- Anwendung ist der Standardfensterstil im Framework eine Kombination aus **WS\_OVERLAPPEDWINDOW** und **FWS\_ADDTOTITLE** Stile.  **FWS\_ADDTOTITLE** ist ein MFC\-Besondereformat, das das Framework angewiesen wird, um dem Dokumenttitel der Titelleiste des Fensters hinzuzufügen.  Um die Fensterattribute in einer SDI\-Anwendung zu ändern, überschreiben Sie die `PreCreateWindow`\-Funktion in der Klasse, die von `CFrameWnd` abgeleitet ist \(der Anwendungs\-Assistent `CMainFrame` nennt\).  Beispiel:  
  
 [!CODE [NVC_MFCDocViewSDI#11](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocViewSDI#11)]  
  
 Dieser Code stellt ein Hauptrahmenfenster außen minimiert und maximiert Schaltflächen und ohne einen veränderbaren Kontext erstellt.  Das Fenster wird auf dem Bildschirm anfänglich zentriert.  
  
##  <a name="_core_the_mdi_case"></a> Der MDI\-Fall  
 Einigermaßen wird mehr Arbeit erfordert, den Fensterstil eines untergeordneten Fensters in einer MDI \(Multiple Document Interface \(MDI\)\- Anwendung zu ändern.  Standardmäßig verwendet eine MDI\-Anwendung, die mit dem Anwendungs\-Assistenten erstellt wird, die Standard [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)\-Klasse, die in MFC definiert wird.  Um den Fensterstil eines untergeordneten MDI\-Fensters zu ändern, müssen Sie eine neue Klasse von `CMDIChildWnd` ableiten und alle Verweise auf `CMDIChildWnd` in einem Projekt durch Verweise auf die neue Klasse ersetzen.  Höchstwahrscheinlich ist der einzige Verweis auf `CMDIChildWnd` in der Anwendung in `InitInstance`\-Memberfunktion der Anwendung.  
  
 Der Standardfensterstil, der in einer MDI\-Anwendung verwendet wird, ist eine Kombination aus der **WS\_CHILD**, **WS\_OVERLAPPEDWINDOW** und **FWS\_ADDTOTITLE** Stile.  Um die Fensterattribute der untergeordnete Fenster einer MDI\-Anwendung zu ändern, überschreiben Sie die [PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)\-Funktion in der Klasse, die von `CMDIChildWnd` abgeleitet wird.  Beispiel:  
  
 [!CODE [NVC_MFCDocView#16](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCDocView#16)]  
  
 Dieser Code stellt untergeordnete MDI\-Fenster ohne eine maximierensschaltfläche erstellt.  
  
### Worüber möchten Sie mehr erfahren?  
  
-   [Windows\-Formate](../mfc/reference/window-styles.md)  
  
-   [Rahmenfensterformate](../mfc/frame-window-styles-cpp.md)  
  
-   [\<caps:sentence id\="tgt44" sentenceid\="26254917059da4aba50f886a6c5db931" class\="tgtSentence"\>Fensterstile\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## Siehe auch  
 [Rahmenfensterstile](../mfc/frame-window-styles-cpp.md)