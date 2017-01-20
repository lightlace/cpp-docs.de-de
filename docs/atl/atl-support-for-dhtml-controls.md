---
title: "ATL-Unterst&#252;tzung f&#252;r DHTML-Steuerelemente"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHTML-Steuerelemente"
  - "DHTML-Steuerelemente, ATL-Unterstützung"
  - "HTML-Steuerelemente, ATL-Unterstützung"
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# ATL-Unterst&#252;tzung f&#252;r DHTML-Steuerelemente
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden von ATL können Sie ein Steuerelement mit Funktion des Dynamic HTML \(DHTML\) erstellen.  Ein Steuerelement ATL DHTML:  
  
-   Hostet das ActiveX\-Steuerelement browsersteuerelement.  
  
-   Gibt, mit HTML, die Benutzeroberfläche des DHTML\-Steuerelements an.  
  
-   Greift auf das ActiveX\-Steuerelement browserobjekt und auf seine Methoden über seine Schnittstelle, [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx) zu.  
  
-   Verwaltet Kommunikation zwischen C\+\+\-Code und HTML.  
  
 DHTML\-Steuerelemente ist für jeden anderen ATL\-Steuerelement vergleichbar, außer das DHTML\-Steuerelement eine zusätzliche Dispatchschnittstelle enthält.  Siehe die Abbildung in [Identifizieren der DHTML\-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) für eine Abbildung der Schnittstellen, die im standardmäßigen DHTML Bereitstellung zu projizieren.  
  
 Sie können das Steuerelement ATL DHTML in einem Webbrowser oder einem anderen Container, wie dem Testcontainer für ActiveX\-Steuerelemente anzeigen.  
  
## In diesem Abschnitt  
 [Identifizieren der DHTML\-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Beschreibt die Elemente eines DHTML\-Steuerelementprojekts.  
  
 [Aufrufen von C\+\+\-Code aus DHTML](../atl/calling-cpp-code-from-dhtml.md)  
 Enthält ein Beispiel des Aufrufens von C\+\+\-Code aus einem DHTML\-Steuerelement bereit.  
  
 [Erstellen eines Steuerelements ATL DHTML](../atl/creating-an-atl-dhtml-control.md)  
 Führt die Schritte zum Erstellen eines DHTML\-Steuerelements auf.  
  
 [Testen des Steuerelements ATL DHTML](../atl/testing-the-atl-dhtml-control.md)  
 Veranschaulicht, wie das Steuerelementprojekt der ursprüngliche DHTML erstellt und getestet werden.  
  
 [Ändern des Steuerelements ATL DHTML](../atl/modifying-the-atl-dhtml-control.md)  
 Zeigt, wie einige Funktionen zum \- Steuerelement hinzufügt.  
  
 [Testen des geänderten Steuerelements ATL DHTML](../atl/testing-the-modified-atl-dhtml-control.md)  
 Zeigt, wie die hinzugefügte Funktionalität des Steuerelements erstellt und getestet werden.  
  
## Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen darüber, wie mit Active Template Library Programmierung.