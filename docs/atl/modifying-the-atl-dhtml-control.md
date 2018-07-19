---
title: Ändern das ATL-DHTML-Steuerelement | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3810236aca4661a6cdcd8399294cdb73e97948fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356494"
---
# <a name="modifying-the-atl-dhtml-control"></a>Ändern das ATL-DHTML-Steuerelement
ATL-Steuerelement-Assistent bietet Startcode zu erstellen und führen Sie das Steuerelement, und damit Sie sehen können, wie die Methoden in den Projektdateien geschrieben sind und wie die DHTML in C++-Code des Steuerelements mithilfe der Dispatchmethoden aufruft. Sie können alle Dispatch-Methode der Schnittstelle hinzufügen. Anschließend können Sie die Methoden in der HTML-Ressource aufrufen.  
  
#### <a name="to-modify-the-atl-dhtml-control"></a>So ändern Sie das ATL-DHTML-Steuerelement  
  
1.  Erweitern Sie in der Klassenansicht das Projekt aus.  
  
     Beachten Sie, dass die Schnittstelle, die mit "UI" endet eine Methode verfügt über `OnClick`. Alle Methoden keinen für die Schnittstelle, die nicht in "UI" endet.  
  
2.  Fügen Sie eine Methode namens `MethodInvoked` auf die Schnittstelle, die nicht in "UI". endet  
  
     Diese Methode wird die Schnittstelle hinzugefügt werden, die in dem Steuerelementcontainer für die Containerinteraktion, nicht auf die Schnittstelle, die von DHTML verwendet, um die Interaktion mit dem Steuerelement verwendet wird. Nur der Container kann diese Methode aufrufen.  
  
3.  Suchen Sie die Stub-Out-Methode in der CPP-Datei, und fügen Sie Code aus, um z. B. ein Meldungsfeld anzeigen:  
  
 [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]  
  
4.  Fügen Sie eine andere Methode mit dem Namen `HelloHTML`und wird nur dieses Mal hinzufügen die Schnittstelle, die Endung "UI". Suchen Sie die Stub-Out `HelloHTML` Methode in der CPP-Datei und Code hinzufügen, um z. B. ein Meldungsfeld angezeigt:  
  
 [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]  
  
5.  Fügen Sie eine dritte Methode `GoToURL`, um die Schnittstelle, die nicht in "UI". endet Implementieren Sie diese Methode durch Aufrufen von [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)wie folgt:  
  
 [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]  
  
     Sie können die **IWebBrowser2** Methoden da ATL einen Zeiger auf diese Schnittstelle für die Sie in Ihrem .h-Datei bereitstellt.  
  
 Im nächsten Schritt ändern Sie die HTML-Ressource, um die Methoden aufrufen, die Sie erstellt haben. Fügen Sie drei Schaltflächen zum Aufrufen dieser Methoden.  
  
#### <a name="to-modify-the-html-resource"></a>So ändern Sie die HTML-Ressource  
  
1.  Doppelklicken Sie im Projektmappen-Explorer auf die HTM-Datei, um die HTML-Ressource anzuzeigen.  
  
     Überprüfen Sie den HTML-Code, insbesondere die Aufrufe an die externe Windows-Dispatch-Methode. Der HTML-Code aufruft, des Projekts `OnClick` -Methode und die Parameter anzugeben, die den Text des Steuerelements (`theBody`) und die Farbe zuweisen ("`red`"). Der Text nach dem Aufruf der Methode ist die Bezeichnung, die auf die Schaltfläche angezeigt wird.  
  
2.  Fügen Sie eine andere `OnClick` -Methode, nur durch Ändern der Farbe. Zum Beispiel:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>  
 ```  
  
     Diese Methode erstellt eine Schaltfläche, mit der Bezeichnung **aktualisieren**, dass der Benutzer klicken kann, um das Steuerelement auf den ursprünglichen, weißen Hintergrund zurückzugeben.  
  
3.  Fügen Sie den Aufruf an die `HelloHTML` Methode, die Sie erstellt haben. Zum Beispiel:  
  
 ```  
 <br>  
 <br>  
 <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>  
 ```  
  
     Diese Methode erstellt eine Schaltfläche, mit der Bezeichnung **HelloHTML**, die der Benutzer klicken kann, zum Anzeigen der `HelloHTML` Meldungsfeld.  
  
 Sie können jetzt erstellen und [testen Sie das geänderte DHTML-Steuerelement](../atl/testing-the-modified-atl-dhtml-control.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Unterstützung für DHTML-Steuerelemente](../atl/atl-support-for-dhtml-controls.md)

