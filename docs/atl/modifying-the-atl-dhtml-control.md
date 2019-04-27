---
title: Ändern des ATL-DHTML-Steuerelements
ms.date: 11/04/2016
helpviewer_keywords:
- HTML controls, modifying
- DHTML controls
- DHTML controls, modifying
ms.assetid: c053f35f-8629-4600-9595-721f5956777a
ms.openlocfilehash: 6c8976c013d0114a3115d3b0bc38fa4bc6acb5b7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261656"
---
# <a name="modifying-the-atl-dhtml-control"></a>Ändern des ATL-DHTML-Steuerelements

Der ATL-Steuerelement-Assistent bietet Startcode, damit können Sie erstellen und führen Sie das Steuerelement, und Sie sehen, wie die Methoden in den Projektdateien geschrieben werden und wie für die DHTML in C++-Code des Steuerelements mithilfe der Dispatchmethoden aufruft. Sie können alle Dispatch-Methode der Schnittstelle hinzufügen. Anschließend können Sie die Methoden in der HTML-Ressource aufrufen.

## <a name="to-modify-the-atl-dhtml-control"></a>So ändern Sie das ATL-DHTML-Steuerelement

1. In **Klassenansicht**, erweitern Sie das Projekt.

   Beachten Sie, dass die Schnittstelle, die in der "UI" endet eine Methode, `OnClick`. Alle Methoden keinen für die Schnittstelle, die nicht in "Benutzeroberfläche" endet.

1. Fügen Sie eine Methode namens `MethodInvoked` auf die Schnittstelle, die nicht in "UI". endet

   Diese Methode wird der Schnittstelle hinzugefügt werden, die in der Steuerelement-Container für die Containerinteraktion, nicht auf die Schnittstelle, die vom DHTML verwendet werden, um die Interaktion mit dem Steuerelement verwendet wird. Nur der Container kann diese Methode aufrufen.

1. Suchen Sie die Stub-Out-Methode in der CPP-Datei, und fügen Sie Code aus, um das Anzeigen eines Meldungsfelds, z.B.:

   [!code-cpp[NVC_ATL_COM#5](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_1.cpp)]

1. Fügen Sie eine weitere Methode namens `HelloHTML`, nur dieses Mal fügen Sie es hinzu, auf die Schnittstelle, die Enden "UI". Suchen Sie die Stub-Out `HelloHTML` -Methode in der CPP-Datei, und fügen Sie Code, um das Anzeigen eines Meldungsfelds, z. B.:

   [!code-cpp[NVC_ATL_COM#6](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_2.cpp)]

1. Fügen Sie eine dritte Methode, `GoToURL`, auf die Schnittstelle, die nicht in "UI". endet Implementieren Sie diese Methode durch Aufrufen von [IWebBrowser2::Navigate](https://msdn.microsoft.com/library/aa752133.aspx)wie folgt:

   [!code-cpp[NVC_ATL_COM#7](../atl/codesnippet/cpp/modifying-the-atl-dhtml-control_3.cpp)]

   Sie können die `IWebBrowser2` Methoden da ATL einen Zeiger auf die Schnittstelle für die Sie in der h-Datei bereitstellt.

Als Nächstes ändern Sie die HTML-Ressource, um die Methoden aufzurufen, die Sie erstellt haben. Fügen Sie drei Schaltflächen zum Aufrufen dieser Methoden.

## <a name="to-modify-the-html-resource"></a>So ändern Sie die HTML-Ressource

1. In **Projektmappen-Explorer**, doppelklicken Sie auf die HTM-Datei, um die HTML-Ressource anzuzeigen.

   Überprüfen Sie den HTML-Code, insbesondere die Aufrufe an die externe Windows-Dispatch-Methoden. Der HTML-Code Aufrufe des Projekts `OnClick` -Methode, und die Parameter geben den Text des Steuerelements (`theBody`) und die Farbe zuweisen ("`red`"). Der Text nach dem Methodenaufruf ist die Bezeichnung, die auf die Schaltfläche angezeigt wird.

1. Fügen Sie ein weiteres `OnClick` -Methode, nur die Änderung der Farbe. Zum Beispiel:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.OnClick(theBody, "white");'>Refresh</BUTTON>
    ```

   Diese Methode erstellt eine Schaltfläche, mit der Bezeichnung **aktualisieren**, dass der Benutzer klicken kann, um das Steuerelement auf den ursprünglichen, weißen Hintergrund zurückzugeben.

1. Fügen Sie den Aufruf von der `HelloHTML` Methode, die Sie erstellt haben. Zum Beispiel:

    ```html
    <br>
    <br>
    <BUTTON onclick='window.external.HelloHTML();'>HelloHTML</BUTTON>
    ```

   Diese Methode erstellt eine Schaltfläche, mit der Bezeichnung **HelloHTML**, die der Benutzer klicken kann, zum Anzeigen der `HelloHTML` Meldungsfeld.

Sie können nun erstellen und [testen Sie das geänderte DHTML-Steuerelement](../atl/testing-the-modified-atl-dhtml-control.md).

## <a name="see-also"></a>Siehe auch

[Unterstützung für DHTML-Steuerelement](../atl/atl-support-for-dhtml-controls.md)
