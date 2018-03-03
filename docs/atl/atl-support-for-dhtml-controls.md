---
title: "ATL-Unterstützung für DHTML-Steuerelemente | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab796752cef10c48036966c2947d711a0e385032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="atl-support-for-dhtml-controls"></a>ATL-Unterstützung für DHTML-Steuerelemente
Verwendung von ATL, können Sie ein Steuerelement mit Dynamic HTML (DHTML)-Funktion erstellen. Ein ATL-DHTML-Steuerelement:  
  
-   Hostet das WebBrowser-Steuerelement.  
  
-   Gibt an, mit HTML-Code der Benutzeroberfläche (UI) des DHTML-Steuerelements.  
  
-   Greift auf das WebBrowser-Objekt und seine Methoden über die Schnittstelle [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx).  
  
-   Verwaltet die Kommunikation zwischen C++-Code und HTML.  
  
 DHTML-Steuerelements ähnelt jedem anderen ATL-Steuerelement, das DHTML-Steuerelement eine zusätzliche Dispatchschnittstelle enthält. Siehe Abbildung in [identifizieren die Elemente eines DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) eine Abbildung der Schnittstellen, die im Standardprojekt DHTML bereitgestellt.  
  
 Sie können das ATL-DHTML-Steuerelement in einem Webbrowser oder andere Container, z. B. den Testcontainer für ActiveX-Steuerelemente anzeigen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Identifizieren von Elementen des DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Beschreibt die Elemente eines DHTML-Steuerelementprojekts.  
  
 [Aufrufen von C++-Code aus DHTML](../atl/calling-cpp-code-from-dhtml.md)  
 Bietet ein Beispiel für das Aufrufen von C++-Code aus einem DHTML-Steuerelement.  
  
 [Erstellen eines ATL-DHTML-Steuerelements](../atl/creating-an-atl-dhtml-control.md)  
 Listet die Schritte zum Erstellen eines DHTML-Steuerelements.  
  
 [Prüfen des ATL-DHTML-Steuerelements](../atl/testing-the-atl-dhtml-control.md)  
 Veranschaulicht das Erstellen und testen die anfängliche DHTML-Steuerelementprojekts.  
  
 [Ändern des ATL-DHTML-Steuerelements](../atl/modifying-the-atl-dhtml-control.md)  
 Zeigt, wie das Steuerelement einige Funktionen hinzu.  
  
 [Testen die geänderte ATL-DHTML-Steuerelement](../atl/testing-the-modified-atl-dhtml-control.md)  
 Veranschaulicht das Erstellen und testen die Funktionalität des Steuerelements hinzugefügt.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Enthält Links zu konzeptionellen Themen über die Programmierung mit der Active Template Library.

