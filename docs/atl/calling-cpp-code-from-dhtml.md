---
title: Aufrufen von C++-Code von DHTML | Microsoft Docs
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
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8e2d0da431249ef886ceca1e2b7f6cbfc99418dd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="calling-c-code-from-dhtml"></a>Aufrufen von C++-Code aus DHTML
DHTML-Steuerelemente kann in einem Container, z. B. Testcontainer oder Internet Explorer gehostet werden. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Testcontainer zugreifen.  
  
 Der Container, der das Steuerelement kommuniziert mit dem Steuerelement über die normalen Steuerelement-Schnittstellen. DHTML verwendet die Dispatchschnittstelle, die mit "UI" für die Kommunikation mit C++-Code und die HTML-Ressource endet. In [ändern das ATL-DHTML-Steuerelement](../atl/modifying-the-atl-dhtml-control.md), können Sie üben, Hinzufügen von Methoden, die von diesen verschiedenen Schnittstellen aufgerufen werden.  
  
 Um ein Beispiel für das Aufrufen von C++-Code aus DHTML, finden Sie unter [Erstellen eines DHTML-Steuerelements](../atl/creating-an-atl-dhtml-control.md) mithilfe des ATL-Steuerelement-Assistenten, und überprüfen Sie den Code in der Headerdatei und der HTML-Datei.  
  
## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Deklarieren von WebBrowser-Methoden in der Headerdatei  
 Zum Aufrufen von C++-Methoden aus der DHTML-UI müssen Sie Methoden des Steuerelements Benutzeroberfläche hinzufügen. Beispielsweise enthält die Header-Datei, die durch die ATL-Steuerelement-Assistent erstellt die C++-Methode `OnClick`, also ein Mitglied der Benutzeroberfläche des Assistenten generierte-Steuerelements.  
  
 Untersuchen Sie `OnClick` in das Steuerelement .h-Datei:  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]  
  
 Der erste Parameter `pdispBody`, ist ein Zeiger auf Dispatch-Schnittstelle für das Body-Objekt. Der zweite Parameter `varColor`, identifiziert die Farbe an, auf das Steuerelement angewendet.  
  
## <a name="calling-c-code-in-the-html-file"></a>Aufrufen von C++-Code in der HTML-Datei  
 Nachdem Sie die WebBrowser-Methoden in der Headerdatei deklariert haben, können Sie die Methoden aus der HTML-Datei aufrufen. Beachten Sie, dass die HTML-Datei, die ATL-Steuerelement-Assistent fügt drei Methoden der Windows-Verteilung ein: drei `OnClick` Methoden, mit denen Nachrichten so ändern Sie die Hintergrundfarbe des Steuerelements zu verteilen.  
  
 Überprüfen Sie eine der Methoden in der HTML-Datei:  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 In der HTML-Code über die externe Methode Fenster `OnClick`, als Teil des Tags Schaltfläche aufgerufen wird. Die Methode verfügt über zwei Parameter: `theBody`, das auf den Text des HTML-Dokuments verweist und `"red"`, was bedeutet, dass die Hintergrundfarbe des Steuerelements in Rot geändert wird, wenn auf die Schaltfläche geklickt wird. Die `Red` befolgen das Tag ist die Bezeichnung der Schaltfläche.  
  
 Finden Sie unter [ändern das ATL-DHTML-Steuerelement](../atl/modifying-the-atl-dhtml-control.md) für Weitere Informationen zum Bereitstellen Ihrer eigenen Methoden. Finden Sie unter [identifizieren die Elemente eines DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) für Weitere Informationen über die HTML-Datei.  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)

