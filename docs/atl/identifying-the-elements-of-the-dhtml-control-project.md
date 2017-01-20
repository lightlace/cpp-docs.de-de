---
title: "Identifying the Elements of the DHTML Control Project"
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
  - "DHTML controls, ATL-Unterstützung"
  - "HTML-Steuerelemente, ATL-Unterstützung"
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: 11
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Identifying the Elements of the DHTML Control Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Der häufigste DHTML\-Steuerungscode ist genau wie den, der für jedes ATL\-Steuerelement erstellt wird.  Ein grundlegendes Verständnis des generischen Codes, der Arbeit nach [ATL\-Lernprogramm](../atl/active-template-library-atl-tutorial.md) und Abschnitten [Erstellen eines ATL\-Projekts](../atl/reference/creating-an-atl-project.md) und [Grundlagen von ATL\-COM\-Objekten](../atl/fundamentals-of-atl-com-objects.md) gelesen.  
  
 DHTML\-Steuerelemente ist für jeden ATL\-Steuerelement, außer vergleichbar:  
  
-   Zusätzlich zu den regulären Schnittstellen implementiert ein Steuerelement, implementiert sie eine zusätzliche Schnittstelle, die verwendet wird, um zwischen dem C\+\+\-Code und der HTML\-Benutzeroberfläche \(Benutzeroberfläche\) zu kommunizieren.  Die Aufrufe HTML Benutzeroberfläche in C\+\+\-Code mithilfe dieser Schnittstelle.  
  
-   Sie erstellt eine HTML\-Ressource für das Steuerelement Benutzeroberfläche.  
  
-   Es ermöglicht den Zugriff auf den DHTML\-Objektmodell durch die Membervariable `m_spBrowser`, die ein intelligenter Zeiger des Typs [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx) ist.  Verwenden Sie diesen Zeiger, um auf einen Teil des DHTML\-Objektmodells zuzugreifen.  
  
 Die folgende Grafik zeigt die Beziehung zwischen der DLL, dem DHTML\-Steuerelement, dem Webbrowser und der HTML\-Ressource.  
  
 ![Elemente eines DHTML&#45;Steuerelementprojekts](../atl/media/vc52en1.png "vc52EN1")  
  
> [!NOTE]
>  Die Namen auf dieser Grafik sind Platzhalter.  Die Namen der HTML\-Ressource und Schnittstellen, die auf dem Steuerelement verfügbar gemacht werden, basieren auf den Namen, die Sie sie im ATL\-Steuerelement\-Assistenten zuweisen.  
  
 In dieser Grafik sind die Elemente:  
  
-   **My DLL** die DLL erstellt mit dem ATL\-Projekt\-Assistenten.  
  
-   **DHTML Control** \(`m_spBrowser`\) das DHTML\-Steuerelement, erstellt mithilfe des ATL\-Objekt\-Assistenten.  Dieses Steuerelement greift auf das Webbrowserobjekt und auf seine Methoden über die Schnittstelle des Webbrowserobjekts, **IWebBrowser2** zu.  Das Steuerelement selbst macht die folgenden zwei Schnittstellen, zusätzlich zu den anderen erforderlichen Standardschnittstellen für ein Steuerelement, verfügbar.  
  
    -   **IDHCTL1** die Schnittstelle verfügbar gemacht vom Steuerelement nur für die Verwendung durch den Container.  
  
    -   **IDHCTLUI1** die Dispatchschnittstelle für die Kommunikation zwischen dem C\+\+\-Code und der HTML\-Benutzeroberfläche.  Der Webbrowser verwendet die Dispatchschnittstelle des Steuerelements, um das Steuerelement anzuzeigen.  Sie können die verschiedenen Methoden dieser Dispatchschnittstelle von der Benutzeroberfläche des Steuerelements aufrufen, indem Sie `window.external` aufrufen, gefolgt vom Methodennamen auf dieser Dispatchschnittstelle, die Sie aufrufen möchten.  Sie könnten auf `window.external` von einem SKRIPTtag innerhalb des HTML zugreifen, die die Benutzeroberfläche für dieses Steuerelement bildet.  Weitere Informationen über das Aufrufen von externen Methoden in der Ressourcendatei, finden Sie unter [Aufrufen von C\+\+\-Code aus DHTML](../atl/calling-cpp-code-from-dhtml.md).  
  
-   **IDR\_CTL1** das Ressourcen\-ID der HTML\-Ressource.  Der Dateiname ist in diesem Fall DHCTL1UI.htm.  Das DHTML\-Steuerelement verwendet eine HTML\-Ressource, die Standardhtml \- tags enthält und externer Fensterdispatch Befehle, dass Sie mit den Text\-Editor bearbeiten können.  
  
-   **Web Browser** der Webbrowser zeigt die Benutzeroberfläche des Steuerelements, auf Grundlage des HTML in der HTML\-Ressource an.  Ein Zeiger auf die **IWebBrowser2**\-Schnittstelle des Webbrowsers ist verfügbar im DHTML\-Steuerelement, Zugriff auf das DHTML\-Objektmodell zuzulassen.  
  
 Der ATL\-Steuerelement\-Assistent generiert ein Steuerelement mit den Code in der HTML\-Ressource und in der CPP\-Datei.  Sie können das Steuerelement kompilieren und ausführen, wie vom Assistenten generiert und dann das Steuerelement entweder im Webbrowser oder im Testcontainer für ActiveX\-Steuerelemente an.  Das Bild unten zeigt das Steuerelement mit ATL DHTML mit drei Schaltflächen, die im Testcontainer angezeigt werden:  
  
 ![ATL&#45;DHTML&#45;Steuerelement](../atl/media/vc52en2.png "vc52EN2")  
  
 Siehe [Erstellen eines Steuerelements ATL DHTML](../atl/creating-an-atl-dhtml-control.md), um beginnen, ein DHTML\-Steuerelement.  Siehe [Tests\-Eigenschaften und Ereignisse mit Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) zu Informationen dazu, wie Sie auf Testcontainer zugreift.  
  
## Siehe auch  
 [Unterstützung für DHTML\-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)