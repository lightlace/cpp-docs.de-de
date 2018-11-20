---
title: Identifizieren von Elementen des DHTML-Steuerelementprojekts
ms.date: 11/19/2018
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
ms.openlocfilehash: e38b94e200754ce9dd37df2bfb17dfaa32cafe49
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2018
ms.locfileid: "52175706"
---
# <a name="identifying-the-elements-of-the-dhtml-control-project"></a>Identifizieren von Elementen des DHTML-Steuerelementprojekts

Die meisten Code von DHTML-Steuerelements wird genau wie diese für alle ATL-Steuerelement erstellt. Für einen grundlegenden Überblick über den generischen Code zu arbeiten, durch die [ATL-Lernprogramm](../atl/active-template-library-atl-tutorial.md), und Lesen Sie die Abschnitte [Erstellen eines ATL-Projekts](../atl/reference/creating-an-atl-project.md) und [Grundlagen von ARL COM-Objekten](../atl/fundamentals-of-atl-com-objects.md).

DHTML-Steuerelements ähnelt alle ATL-Steuerelement, mit Ausnahme von:

- Zusätzlich zu den regulären Schnittstellen, die ein Steuerelement implementiert, implementiert er eine weitere Schnittstelle, die für die Kommunikation zwischen der C++-Code und die HTML-Benutzeroberfläche (UI) verwendet wird. Der HTML-Benutzeroberfläche ruft diese Schnittstelle mithilfe C++-Code.

- Erstellt eine HTML-Ressource für das UI-Steuerelement.

- Es ermöglicht den Zugriff auf das DHTML-Objektmodell über die Membervariable `m_spBrowser`, dies ist ein intelligenter Zeiger vom Typ [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx). Verwenden Sie diesen Zeiger auf einen beliebigen Teil der DHTML-Objektmodell zugreifen.

Die folgende Abbildung veranschaulicht die Beziehung zwischen der DLL, des DHTML-Steuerelements, Webbrowser und die HTML-Ressource.

![Elemente eines DHTML-Steuerelementprojekts](../atl/media/vc52en1.gif "Elemente eines DHTML-Steuerelementprojekts")

> [!NOTE]
>  Die Namen auf die folgende Grafik sind Platzhalter. Die Namen von HTML-Ressource und die Schnittstellen verfügbar gemacht werden, auf das Steuerelement basieren auf den Namen, die Sie sie in der ATL-Steuerelement-Assistent zuweisen.

In dieser Abbildung sind die Elemente:

- **Meine DLL** die DLL, die mit dem ATL-Projekt-Assistenten erstellt.

- **DHTML-Steuerelements** (`m_spBrowser`) die DHTML-Steuerelement mit ATL-Objektassistenten erstellt. Dieses Steuerelement greift auf das Webbrowser-Objekt und seine Methoden über die Schnittstelle des Webbrowserobjekts `IWebBrowser2`. Das Steuerelement selbst stellt die folgenden beiden Schnittstellen, zusätzlich zu der anderen Standardschnittstellen für ein Steuerelement benötigt.

   - `IDHCTL1` Die Schnittstelle, die vom Steuerelement für die Verwendung nur durch den Container verfügbar gemacht wird.

   - `IDHCTLUI1` Die Dispatchschnittstelle für die Kommunikation zwischen der C++-Code und die HTML-Benutzeroberfläche. Der Webbrowser mithilfe Dispatchschnittstelle des Steuerelements das Steuerelement angezeigt. Sie können verschiedene Methoden dieser Schnittstelle für die Verteilung über die Benutzeroberfläche des Steuerelements aufrufen, durch den Aufruf `window.external`, gefolgt von den Methodennamen für diese Dispatchschnittstelle, die Sie aufrufen möchten. Greifen Sie auf `window.external` aus einem Skripttag im HTML-Code, aus denen die Benutzeroberfläche für dieses Steuerelement besteht. Weitere Informationen zum Aufrufen externer Methoden in der Ressourcendatei finden Sie unter [Aufrufen von C++-Code aus DHTML](../atl/calling-cpp-code-from-dhtml.md).

- **IDR_CTL1** die Ressourcen-ID der HTML-Ressource. Der Dateiname, ist in diesem Fall DHCTL1UI.htm. Das DHTML-Steuerelement verwendet eine HTML-Ressource, die HTML-Standardtags und externen Fenster Dispatch-Befehle, die Sie bearbeiten können, mit dem Text-Editor enthält.

- **Webbrowser** der Webbrowser zeigt die Benutzeroberfläche des Steuerelements, basierend auf den HTML-Code in der HTML-Ressource. Ein Zeiger auf die Web-Browsers `IWebBrowser2` Schnittstelle finden Sie in das DHTML-Steuerelement, auf die DHTML-Objektmodell zugreifen können.

Der ATL-Steuerelement-Assistent generiert ein Steuerelement mit dem Standardcode in der HTML-Ressource und die CPP-Datei. Sie können zu kompilieren und führen Sie das Steuerelement, wie Sie vom Assistenten generiert und zeigen Sie dann das Steuerelement in einem Webbrowser oder den Testcontainer für ActiveX-Steuerelemente. Die folgende Abbildung zeigt die standardmäßige ATL-DHTML-Steuerelement mit drei Schaltflächen, die im Test-Container angezeigt:

![ATL-DHTML-Steuerelements](../atl/media/vc52en2.gif "ATL-DHTML-Steuerelement")

Finden Sie unter [Erstellen eines ATL-DHTML-Steuerelements](../atl/creating-an-atl-dhtml-control.md) für den Einstieg in das Erstellen eines DHTML-Steuerelements. Finden Sie unter [Testen von Eigenschaften und Ereignisse mit Test Container](../mfc/testing-properties-and-events-with-test-container.md) Informationen zum Zugriff auf Testcontainer.

## <a name="see-also"></a>Siehe auch

[Unterstützung für DHTML-Steuerelement](../atl/atl-support-for-dhtml-controls.md)

