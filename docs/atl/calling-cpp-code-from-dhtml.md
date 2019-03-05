---
title: Aufrufen von C++-Code aus DHTML
ms.date: 11/04/2016
helpviewer_keywords:
- DHTML, calling C++ code from
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
ms.openlocfilehash: fb63f8671770f57972a4c789d983bdf9658d5ecb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270175"
---
# <a name="calling-c-code-from-dhtml"></a>Aufrufen von C++-Code aus DHTML

DHTML-Steuerelements kann in einem Container, z. B. Testcontainer oder Internet Explorer gehostet werden. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Zugriff auf Testcontainer.

Der Container, der das Steuerelement kommuniziert mit dem Steuerelement, das über die normalen-Steuerelement-Schnittstellen. DHTML verwendet die Dispatchschnittstelle, die mit "UI" für die Kommunikation mit Ihren C++-Code und HTML-Ressource endet. In [Ändern des ATL-DHTML-Steuerelements](../atl/modifying-the-atl-dhtml-control.md), üben Sie die Methoden, die von diesen verschiedenen Schnittstellen aufgerufen werden.

Finden Sie ein Beispiel von Aufrufen von C++-Code aus DHTML, [Erstellen eines DHTML-Steuerelements](../atl/creating-an-atl-dhtml-control.md) mithilfe des ATL-Steuerelement-Assistenten, und überprüfen Sie den Code in der Headerdatei und der HTML-Datei.

## <a name="declaring-webbrowser-methods-in-the-header-file"></a>Deklarieren von WebBrowser-Methoden in der Headerdatei

Um C++-Methoden aus dem DHTML-UI aufzurufen, müssen Sie Methoden auf der Benutzeroberfläche des Steuerelements hinzufügen. Beispielsweise enthält die Header-Datei, die von der ATL-Steuerelement-Assistent erstellt die C++-Methode `OnClick`, die die Benutzeroberfläche des Steuerelements vom Assistenten generierte angehört.

Untersuchen Sie `OnClick` in dem Steuerelement-h-Datei:

[!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/cpp/calling-cpp-code-from-dhtml_1.h)]

Der erste Parameter, *PdispBody*, ist ein Zeiger auf die Dispatchschnittstelle für das Body-Objekt. Der zweite Parameter, *VarColor*, gibt die Farbe an, auf das Steuerelement angewendet.

## <a name="calling-c-code-in-the-html-file"></a>Aufrufen von C++-Code in die HTML-Datei

Nachdem Sie die WebBrowser-Methoden in der Headerdatei deklariert haben, können Sie die Methoden aus der HTML-Datei aufrufen. Beachten Sie, dass die HTML-Datei, dass der ATL-Steuerelement-Assistent fügt dem drei Methoden der Windows-Verteilung ein: drei `OnClick` Methoden, die Nachrichten an die Hintergrundfarbe des Steuerelements ändern zu senden.

Überprüfen Sie eine der Methoden in der HTML-Datei:

`<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`

In der HTML-Code über die externe Methode Fenster `OnClick`, als Teil des Tags Schaltfläche aufgerufen wird. Die Methode verfügt über zwei Parameter: `theBody`, das den Text der HTML-Dokument, verweist und `"red"`, was bedeutet, dass die Hintergrundfarbe des Steuerelements in Rot geändert wird, wenn die Schaltfläche geklickt wird. Die `Red` das Tag folgt die Beschriftung der Schaltfläche.

Finden Sie unter [Ändern des ATL-DHTML-Steuerelements](../atl/modifying-the-atl-dhtml-control.md) für Weitere Informationen zum Bereitstellen von Ihren eigenen Methoden. Finden Sie unter [Identifizieren von Elementen des DHTML-Steuerelementprojekts](../atl/identifying-the-elements-of-the-dhtml-control-project.md) für Weitere Informationen zu der HTML-Datei.

## <a name="see-also"></a>Siehe auch

[Unterstützung für DHTML-Steuerelement](../atl/atl-support-for-dhtml-controls.md)
