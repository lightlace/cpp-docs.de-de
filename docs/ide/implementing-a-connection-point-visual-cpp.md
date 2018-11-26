---
title: Implementieren eines Verbindungspunkts
ms.date: 11/12/2018
f1_keywords:
- vc.codewiz.impl.cp.overview
helpviewer_keywords:
- connection points [C++], implementing
- implement connection point wizard [C++]
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
ms.openlocfilehash: 7afa61246c5251936967e281f7237dc37e5be045
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693281"
---
# <a name="implement-a-connection-point"></a>Implementieren eines Verbindungspunkts

Zum Implementieren eines Verbindungspunkts mithilfe des Assistenten zum Implementieren von Verbindungspunkten müssen Sie ein Projekt als eine ATL COM-Anwendung oder eine MFC-Anwendung, die ATL-Unterstützung umfasst, erstellt haben. Sie können den [ATL-Projekt-Assistenten](../atl/reference/atl-project-wizard.md) zum Erstellen einer ATL-Anwendung verwenden, oder [Ihrer MFC-Anwendung ein ATL-Objekt hinzufügen](../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL-Unterstützung in einer MFC-Anwendung zu implementieren.

> [!NOTE]
> Informationen zum Implementieren von Verbindungspunkten in ein MFC-Projekt finden Sie unter [Connection Points (Verbindungspunkte)](../mfc/connection-points.md).

Nachdem Sie das Projekt erstellt haben, müssen Sie zum Implementieren eines Verbindungspunkts zunächst ein ATL-Objekt hinzufügen. Eine Liste von Assistenten, die Ihrem ATL-Projekt Objekte hinzufügen, finden Sie unter [Adding Objects and Controls to an ATL Project (Hinzufügen von Objekten und Steuerelementen zu einem ATL-Projekt)](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).

> [!NOTE]
> Der Assistent unterstützt keine ATL-Dialogfelder, mit einem ATL-Server erstellte XML-Webdienste, Leistungsobjekte oder Leistungsindikatoren.

Ein verbindungsfähiges Objekt (d.h. eine Quelle) kann einen Verbindungspunkt für seine Ausgangsschnittstellen anzeigen. Jede Ausgangsschnittstelle kann von einem Client auf einem Objekt (d.h. eine Senke) implementiert werden. Weitere Informationen finden Sie unter [ATL Connection Points (ATL-Verbindungspunkte)](../atl/atl-connection-points.md).

**So implementieren Sie einen Verbindungspunkt:**

1. Klicken Sie in der Klassenansicht mit der rechten Maustaste auf den Klassennamen für das ATL-Objekt.

1. Klicken Sie erst im Kontextmenü auf **Hinzufügen** und dann auf **Verbindungspunkt hinzufügen**, um den [Assistenten zum Implementieren von Verbindungspunkten](#implement-connection-point-wizard) anzuzeigen.

1. Wählen Sie die zu implementierenden Verbindungspunktschnittstellen aus den entsprechenden Typbibliotheken aus, und klicken Sie auf **Fertig stellen**.

1. Überprüfen Sie in der Klassenansicht die Proxyklassen, die für jeden Verbindungspunkt erstellt wurden. Die Klassen werden als CProxy*Schnittstellenname*\<T> angezeigt und werden von [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) abgeleitet.

1. Doppelklicken Sie auf die Verbindungspunktklasse, um die Definition der Klasse des Verbindungspunkts anzuzeigen.

   - Wenn Sie einen Verbindungspunkt für die Schnittstelle Ihres eigenen Projekts implementieren, wird die folgende Definition angezeigt:

     ```cpp
     template< class T >
     class CProxyInterfaceName :
     public IConnectionPointImpl< T, &IID_InterfaceName >
     {
     public:
     };
     ```

   - Wenn Sie eine lokale Schnittstelle implementieren, werden Methoden und Eigenschaften im Klassentext angezeigt.

   - Wenn Sie einen Verbindungspunkt für eine andere Schnittstelle implementieren, enthält die Definition die Methoden der Schnittstelle, denen jeweils `Fire_` vorangestellt wurde.

## <a name="in-this-section"></a>In diesem Abschnitt

- [Assistent zum Implementieren von Verbindungspunkten](#implement-connection-point-wizard)

## <a name="implement-connection-point-wizard"></a>Assistent zum Implementieren von Verbindungspunkten

Dieser Assistent implementiert einen Verbindungspunkt für ein COM-Objekt. Ein verbindungsfähiges Objekt (d.h. eine Quelle) kann einen Verbindungspunkt für seine eigenen Schnittstellen oder für Ausgangsschnittstellen anzeigen. Visual C++ und Windows stellen Typbibliotheken bereit, die über Ausgangsschnittstellen verfügen. Jede Ausgangsschnittstelle kann von einem Client auf einem Objekt (d.h. eine Senke) implementiert werden.

Weitere Informationen finden Sie unter [ATL Connection Points (ATL-Verbindungspunkte)](../atl/atl-connection-points.md).

- **Verfügbare Typbibliotheken**

  Zeigt die verfügbaren Typbibliotheken an, die die Schnittstellendefinitionen enthalten, für die Sie Verbindungspunkte implementieren können. Klicken Sie auf die Schaltfläche mit den Auslassungspunkten, um eine Datei zu suchen, die die zu verwendende Typbibliothek enthält.

- **Position**

  Zeigt den Speicherort der Typbibliothek an, die in der Liste **Verfügbare Typbibliotheken** aktuell ausgewählt ist.

- **Schnittstellen**

  Zeigt die Schnittstellen an, deren Definitionen in der aktuell im Feld **Verfügbare Typbibliotheken** ausgewählten Typbibliothek enthalten sind.

  |Schaltfläche „Übertragen“|Beschreibung |
  |---------------------|-----------------|
  |**>**|Fügt den Namen der aktuell in der Liste **Schnittstellen** ausgewählten Schnittstelle der Liste **Verbindungspunkte implementieren** hinzu.|
  |**>>**|Fügt alle Namen der in der Liste **Schnittstellen** verfügbaren Schnittstellen der Liste **Verbindungspunkte implementieren** hinzu.|
  |**\<**|Entfernt den Namen der Schnittstelle, die aktuell in der Liste **Verbindungspunkte implementieren** ausgewählt ist.|
  |**\<\<**|Entfernt alle Namen der Schnittstellen, die aktuell in der Liste **Verbindungspunkte implementieren** aufgelistet sind.|

- **Verbindungspunkte implementieren**

  Zeigt den Namen der Schnittstellen an, für die Sie Verbindungspunkte implementieren, wenn Sie auf **Fertig stellen** klicken.
