---
title: "Calling C++ Code from DHTML"
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
  - "DHTML, calling C++ code from"
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: 12
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Calling C++ Code from DHTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DHTML\-Steuerelemente kann in einem Container, wie Testcontainer oder Internet Explorer gehostet werden.  Siehe [Tests\-Eigenschaften und Ereignisse mit Testcontainer](../mfc/testing-properties-and-events-with-test-container.md) zu Informationen dazu, wie Sie auf Testcontainer zugreift.  
  
 Der Container, der das Steuerelement hostet, ist das Steuerelement mit den normalen Antriebssteuerungen kommunizieren.  DHTML verwendet die Dispatchschnittstelle, die endet mit "Benutzeroberfläche", um sich mit dem C\+\+\-Code und der HTML\-Ressource zu kommunizieren.  In [Ändern des Steuerelements ATL DHTML](../atl/modifying-the-atl-dhtml-control.md) können Sie die verschiedenen, von dieser Schnittstellen aufgerufen werden Methoden zum üben.  
  
 Um ein Beispiel des Aufrufens von C\+\+ anzuzeigen codieren Sie von DHTML, [erstellen Sie ein DHTML\-Steuerelement](../atl/creating-an-atl-dhtml-control.md) mit dem ATL\-Steuerelement\-Assistenten und überprüfen Sie den Code in der Headerdatei und in der HTML\-Datei.  
  
## Deklarieren von ActiveX\-Steuerelement browsermethoden in der Headerdatei  
 Um C\+\+\-Methoden vom DHTML Benutzeroberfläche aufzurufen, müssen Sie Methoden das Benutzeroberfläche des Steuerelements hinzufügen.  Beispielsweise enthält die Headerdatei, die vom ATL\-Steuerelement\-Assistenten erstellt wird, die C\+\+\-Methode `OnClick`, die Mitglied der Benutzeroberfläche des vom Assistenten erstellten Steuerelements ist.  
  
 Überprüfen Sie `OnClick` in der H\-Datei des Steuerelements:  
  
 [!CODE [NVC_ATL_COM#4](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#4)]  
  
 Der erste Parameter, `pdispBody`, ist ein Zeiger auf die Dispatchschnittstelle des Textobjekts.  Der zweite Parameter, `varColor`, identifiziert die Farbe, um auf das Steuerelement anzuwenden.  
  
## Aufrufen von C\+\+\-Code in der HTML\-Datei  
 Sobald Sie die ActiveX\-Steuerelement browsermethoden in der Headerdatei deklariert haben, können Sie die Methoden in der HTML\-Datei aufrufen.  Begriff in der HTML\-Datei, dass die ATL\-Steuerelement\-Assistenten\-Einfügungen drei Windows\-Dispatchmethoden: `OnClick` drei Methoden, die Meldungen der, um die Hintergrundfarbe des Steuerelements ändern.  
  
 Überprüfen Sie eine der Methoden in der HTML\-Datei:  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 Im oben HTML\-Code, wird die externe Methoden des Fensters, `OnClick`, als Teil des Schaltflächentags aufgerufen.  Die Methode verfügt über zwei Parameter: `theBody`, das den Text des HTML\-Dokuments verweist, und `"red"`, das angibt, ob die Hintergrundfarbe des Steuerelements in Rot geändert wird, wenn auf die Schaltfläche geklickt wird.  `Red`, das dem Tag folgt, ist die Bezeichnung der Schaltfläche.  
  
 Siehe [Ändern des Steuerelements ATL DHTML](../atl/modifying-the-atl-dhtml-control.md) weitere Informationen über das Bereitstellen eigener Methoden.  Siehe [Identifizieren der DHTML\-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) weitere Informationen über die HTML\-Datei.  
  
## Siehe auch  
 [Unterstützung für DHTML\-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)