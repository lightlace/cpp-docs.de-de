---
title: Identifizieren die Elemente eines DHTML-Steuerelementprojekts | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 525ad4e073607064234641f6544a11901ded0096
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>Identifizieren die Elemente eines DHTML-Steuerelementprojekts
Die meisten DHTML-Steuerungscode ist genau für ATL-Steuerelement erstellt. Für einen grundlegenden Überblick des generischen Codes zu arbeiten, durch die [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md), und Lesen Sie die Abschnitte [Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md) und [Grundlagen von ATL-COM-Objekte](../atl/fundamentals-of-atl-com-objects.md).  
  
 DHTML-Steuerelements ähnelt jedes ATL-Steuerelement, mit Ausnahme von:  
  
-   Zusätzlich zu regulären Schnittstellen, die ein Steuerelement implementiert, implementiert er eine zusätzliche Schnittstelle, die für die Kommunikation zwischen der C++-Code und die HTML-Benutzeroberfläche (UI) verwendet wird. Die HTML-UI Aufrufe von C++-Code, die Verwendung dieser Schnittstelle ab.  
  
-   Erstellt eine HTML-Ressource für die UI-Steuerelement.  
  
-   Es ermöglicht den Zugriff auf das DHTML-Objektmodell über die Membervariable `m_spBrowser`, dies ist ein intelligenter Zeiger vom Typ [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx). Mit diesem Zeiger auf einen beliebigen Teil der DHTML-Objektmodell zugreifen können.  
  
 Die folgende Abbildung veranschaulicht die Beziehung zwischen der DLL, DHTML-Steuerelemente, Webbrowser und die HTML-Ressource.  
  
 ![Elemente eines DHTML-Steuerelementprojekts](../atl/media/vc52en1.gif "vc52en1")  
  
> [!NOTE]
>  Die Namen dieser Grafik sind Platzhalter. Die Namen von HTML-Ressource und die Schnittstellen verfügbar gemacht werden, auf das Steuerelement basieren auf den Namen, die Sie sie im ATL-Steuerelement-Assistenten zuweisen.  
  
 In dieser Abbildung sind die Elemente:  
  
-   **Meine DLL** die DLL, die mit dem ATL-Projekt-Assistenten erstellt.  
  
-   **DHTML-Steuerelemente** (`m_spBrowser`) der DHTML-Steuerelement mit der ATL-Objektassistenten erstellt. Dieses Steuerelement greift Webbrowserobjekts und seine Methoden über die Webbrowserobjekts-Schnittstelle auf **IWebBrowser2**. Das Steuerelement selbst macht die folgenden beiden Schnittstellen, zusätzlich zu anderen Standardschnittstellen, die für ein Steuerelement erforderlich.  
  
    -   **IDHCTL1** die Schnittstelle, die vom Steuerelement für die Verwendung nur durch den Container verfügbar gemacht.  
  
    -   **IDHCTLUI1** Dispatch-Schnittstelle für die Kommunikation zwischen der C++-Code und die HTML-Benutzeroberfläche. Der Webbrowser verwendet Dispatch-Schnittstelle des Steuerelements, um das Steuerelement anzuzeigen. Sie können verschiedene Methoden dieser Schnittstelle Verteilung über das Steuerelement-Benutzeroberfläche aufrufen, durch den Aufruf `window.external`, gefolgt von den Methodennamen für diese Dispatchschnittstelle, die Sie aufrufen möchten. Sie möchten den Zugriff auf `window.external` aus einem Skripttag in der HTML-Code, der die Benutzeroberfläche für das genannte Steuerelement bildet. Weitere Informationen zu externen Methodenaufrufe in der Ressourcendatei, finden Sie unter [Aufrufen von C++-Code aus DHTML](../atl/calling-cpp-code-from-dhtml.md).  
  
-   **IDR_CTL1** die Ressourcen-ID der HTML-Ressource. Der Dateiname ist in diesem Fall DHCTL1UI.htm. DHTML-Steuerelemente verwendet, eine HTML-Ressource, die standard-HTML-Tags und externen Fenster Dispatch-Befehle, die Sie bearbeiten können, indem den Text-Editor enthält.  
  
-   **Webbrowser** der Webbrowser zeigt das Steuerelement-Benutzeroberfläche, basierend auf den HTML-Code in der HTML-Ressource an. Ein Zeiger auf die Web-Browsers **IWebBrowser2** Schnittstelle ist im DHTML-Steuerelement, um Zugriff auf das DHTML-Objektmodell verfügbar.  
  
 ATL-Steuerelement-Assistent generiert ein Steuerelement mit Standardcode in der HTML-Ressource und die CPP-Datei. Kompilieren können und führen Sie das Steuerelement aus, wie vom Assistenten generiert und anschließend das Steuerelement in der Webbrowser oder der Testcontainer für ActiveX-Steuerelement anzeigen. Die folgende Abbildung zeigt die ATL-DHTML-Steuerelement mit drei Schaltflächen im Testcontainer angezeigt:  
  
 ![ATL-DHTML-Steuerelement](../atl/media/vc52en2.gif "vc52en2")  
  
 Finden Sie unter [Erstellen eines ATL-DHTML-Steuerelements](../atl/creating-an-atl-dhtml-control.md) für den Einstieg in das Erstellen eines DHTML-Steuerelements. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Testcontainer zugreifen.  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)

